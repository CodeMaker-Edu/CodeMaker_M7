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

**Girar**

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

--- 

#### 2. Luces (LEDs)

Codey Rocky tiene LEDs RGB tanto en la unidad Codey como en el chasis Rocky.

**Luces en el LED Codey (cabeza):**

```python
codey.led.show(255, 0, 0, t)
```

- `255,0,0`: código RGB del color.
- `t`: Tiempo en segundos (opcional).

**Luces en el LED de Rocky (cuerpo):**
```python
rocky.color_ir_sensor.set_led_color(color)
```
- `color`: Nombre de color en inglés ("red", "green", "blue", etc.) o código hexadecimal.

---

#### 3. Matriz de LEDs (Face Panel)

La matriz de LEDs en la unidad Codey (codey.display) te permite mostrar texto, números e imágenes simples.

**Mostrar texto:**
```python
codey.display.show(text)
```

**Borrar pantalla:**
```python
codey.display.clear()
```

**Mostrar una imagen de las predefinidas:**
```python
codey.display.show_image(image_name)
```
- `image_name`: Nombre de la imagen (ej: "smile", "sad", "heart", "arrow_right", etc.). Consulta la documentación específica de Makeblock para la lista completa.

**Mostrar una imagen propia:**
Puedes dibujar tus propias imágenes en la matriz de LEDs definiéndolas como una matriz de números binarios (0 y 1). La matriz debe ser de 16x8 ya que son los píxeles que tiene la pantalla (1 para encendido, 0 para apagado).
```python
corazon = [
    "0000000000000000",
    "0011001100000000",
    "0111101111000000",
    "0111111111000000",
    "0011111110000000",
    "0001111100000000",
    "0000111000000000",
    "0000010000000000"
]

codey.display.show(corazon)
time.sleep(3)
codey.display.clear()
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


