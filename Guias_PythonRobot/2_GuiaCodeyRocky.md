### Guia de programación de Codey Rocky en Python

Para usar estas funciones, necesitarás importar los módulos correspondientes al inicio de tu script. Para Codey Rocky, los objetos principales suelen ser codey (para la unidad principal Codey) y rocky (para el chasis Rocky).
```python
import codey
import rocky
import time #Solo si necesitas esperas en segundos
```
---

#### 1. Movimiento del Chasis Rocky

**Avanzar y retroceder**

El `rocky` controla los motores del chasis. La velocidad se suele expresar en un rango de -100 a 100.

```python
rocky.forward(speed, t)
```
- `speed`: Velocidad (-100 a 100). Positivo para adelante.
- `t`: Tiempo en segundos (opcional). Si no se especifica, se mueve continuamente.

También puedes indicar solo la velocidad y después añadir una espera de tiempo y por último detener al robot.
```python
rocky.forward(30)
time.sleep(1.5) # Esperar 1.5 segundos
rocky.stop()    # Luego detener
```

**Girar por tiempo**

```python
rocky.turn_left(speed, t): Gira el robot hacia la izquierda.
rocky.turn_right(speed, t): Gira el robot hacia la izquierda.
```
- `speed`: Velocidad de giro (-100 a 100). Positivo para girar a la izquierda.
- `t`: Tiempo en segundos (opcional).

También se puede poner el robot a girar sin tiempo, después esperar y por último detenerlo.
```python
rocky.turn_right(40)
time.sleep(1)
rocky.stop()
```

**Girar por grados**

Codey también permite girar un determinado numero de grados, en lugar de girar por tiempo:

```python
    rocky.turn_left_by_degree(90)
    rocky.turn_right_by_degree(90)
```

--- 

#### 2. Luces (LEDs)

Codey Rocky tiene LEDs RGB tanto en la unidad Codey como en el chasis Rocky.

**Luces en el LED Codey (cabeza):**

```python
codey.led.show(255, 0, 0, t)
```
- Valor RGB (rojo, verde, azul)
- `t`: tiempo (opcional). Si no se pone, se queda el LED encendido y habría que apagarlo con `codey.led.off()`

**Luces en el LED de Rocky (cuerpo):**
```python
rocky.color_ir_sensor.set_led_color(color)
```
- `color`: Nombre de color en inglés ("red", "green", "blue", etc.) o código hexadecimal. Apagarlo sería ponerlo "black".

---

#### 3. Matriz de LEDs (Face Panel)

La matriz de LEDs en la unidad Codey (codey.display) te permite mostrar texto, números e imágenes simples.

**Mostrar texto:**

El siguiente código muestra un texto:

```python
codey.display.show("hola")
```

**Borrar pantalla:**

El siguiente código borra la pantalla:

```python
codey.display.clear()
```

**Encender un led de la pantalla:**

El siguiente código encendería el LED colocado en la posición  x=0, y=0 (esquina superior izquierda).

```python
    codey.display.set_pixel(0, 0, True)
```

---

#### 4. Sonido (Altavoz)
El altavoz integrado en Codey (codey.speaker) permite reproducir sonidos y tonos.

**Reproducir sonidos pregrabados:**
```python
codey.speaker.play_melody(file_name)
```
- `file_name`: Nombre del archivo (ej: "hello.wav", "hi.wav", "yeah.wav", etc.).

**Reproducir tonos:**
```python
codey.speaker.play_tone(frequency, time=None)
```
- `frequency`: Frecuencia en Hertz (Hz). Un rango común es 0 a 5000.
- `time`: Duración en milisegundos (ms) (opcional). Si no se especifica, suena continuamente hasta stop_sounds().

#### 5. Detección de pulsación en botones

Para que Codey detecte que se ha presionado un botón, debe estar en bucle infinito (`while True`) comprobando si se presiona mediante un `if`.

```python
while True:
    if codey.button_a.is_pressed():
        #Codigo a realizar
```

Los eventos de cada botón son:
- Botón A: `codey.button_a.is_pressed()`
- Botón B: `codey.button_b.is_pressed()`
- Botón C: `codey.button_c.is_pressed()`

#### 6. Sensores

Codey Rocky puede detectar obstáculos, colores, luz, etc. gracias a sus sensores. Se deben programación siempre en un `if` que comprueba el sensor, que debe estar siempre dentro de un `while True` para que esté siempre comprobando.

Comprobar si hay un obstáculo delante.
```python
while True:
    if rocky.color_ir_sensor.is_obstacle_ahead():
        # Tareas a realizar
```

Comprobar si se ha detectado un determinado color (funciona con los colores `'red'`, `'green'`, `'blue`, `'yellow'`, `'cyan'`, `'purple'`, `'black'` y `'white'`:
```python
while True:
    if rocky.color_ir_sensor.is_color('red'):
        # Tareas a realizar
```

> [!WARNING]
> En tu programa solo puede haber un único bucle `while True`, por lo que si usas varios sensores o botones, tendrás que colocar todos los `if` dentro del mismo bucle.
