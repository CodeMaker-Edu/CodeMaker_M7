## Programación de Cyberpi con Python

Para poder programar la Cyberpi en Python, necesitamos lo primero importar la librería necesaria:

```python
import cyberpi
```

Veamos ahora cómo programar los diferentes componentes de Cyberpi, como su joystick, botones, tira de LEDs, pantalla, etc. Recuerda que deberás combinar las funciones que se explican aquí con tus conceptos generales sobre Python (variables, bucles, condicionales...).

---

### Audio

**Emitir audio:**
```python
cyberpi.audio.play('hi')
```
Opciones disponibles: `hi`, `bye`, `ring`, `score`, `heartbeat`, etc.

**Emitir nota musical:**
```python
cyberpi.audio.play_music(60, 0.25)
```

---

### Tira de LEDs

**Animaciones de la tira de LED:**
```python
cyberpi.led.play('rainbow')
```
Opciones disponibles: `rainbow`, `meteor_blue`, `flash_red`, etc.

**Personalizar el color de cada uno de los LEDs de la tira:**
```python
cyberpi.led.show('red orange yellow green cyan')
```

**Encender un LED específico de la tira (r, g, b, numLed):**
```python
cyberpi.led.on(255, 0, 0, 1)
```

---

### Pantalla

**Mostrar texto básico en pantalla:**
```python
cyberpi.console.println("makeblock")
```

**Mostrar texto avanzado, especificando el tamaño y la posición del texto en pantalla:**
```python
cyberpi.display.show_label("codemaker", 12, "center", 0) //especificando posición
cyberpi.display.show_label("codemaker", 12, 0, 0, 0) //especificando coordenadas
```
Los datos que se deben poner son:
- Texto a mostrar
- Tamaño del texto
- Posición:
  - Posición relativa: especificando `center`, `top_mid`, `top_left`, `top_right`, `mid_left`, `mid_right`, `bottom_mid`, `bottom_left`, `bottom_right`.
  - Posición por coordenadas: `x` e `y` teniendo en cuenta que la coordenada `[0,0]` es la esquina superior izquierda, y que la pantalla es cuadrada y tiene 128 pixeles de lado. 
- Número del texto: si solo se quiere mostrar un texto en pantalla, se pondrá `0`, si se quieren mostrar dos textos, a uno se le pondrá `0` y al otro `1`, etc.

**Borrar pantalla:**
```python
cyberpi.console.clear()
```

**Mostrar icono en pantalla:**
```python
icono = cyberpi.sprite() #Se crea una variable icono antes de los bucles y condicionales
icono.draw_pixel("Image")
```
Iconos disponibles: `Image`, `Play`, `Light`, `Music`, `Clock`, `Motion`, `Home`, `Shut_down`, `Rocket`, `Fire`, `Color`, etc.

---

### Pulsación de botones y joystick:

**Joystick:**
```python
while True:
  if cyberpi.controller.is_press('middle'):
```
Opciones disponibles:  `middle`, `up`, `down`, `left`, `right`.

**Botones:**
```python
while True:
  if cyberpi.controller.is_press('a'):
```
Opciones disponibles: `a`, `b`.

---

### Sensores

**Inclinación de la placa:**
```python
while True:
  if cyberpi.is_tiltforward():
```
Opciones disponibles: `tiltforward`, `tiltbackward`, `tiltleft`, `tiltright`, `faceup`, `facedown`.

**Intensidad de la luz:**
```python
while True:
  if cyberpi.get_bri() == 50:
```
 Se deben comparar con `==`, `<`, `>` (el sensor da valores entre 0-100).
      

