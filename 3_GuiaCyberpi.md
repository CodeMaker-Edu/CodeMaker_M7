## Programación de Cyberpi con Python

Para poder programar la Cyberpi en Python, necesitamos lo primero importar la librería necesaria:

```python
import cyberpi
```

Veamos ahora cómo programar los diferentes componentes de Cyberpi, como su joystick, botones, tira de LEDs, pantalla, etc. Recuerda que deberás combinar las funciones que se explican aquí con tus conceptos generales sobre Python (variables, bucles, condicionales...).

---

### Audio

Emitir audio `hi`, `bye`, `ring`, `score`, `heartbeat`, etc.:
```python
cyberpi.audio.play('hi')
```

Emitir nota musical:
```python
cyberpi.audio.play_music(60, 0.25)
```

---

### Tira de LEDs

Animaciones de la tira de LED `rainbow`, `meteor_blue`, `flash_red`, etc.:
```python
cyberpi.led.play('rainbow')
```

Personalizar el color de cada uno de los LEDs de la tira:
```python
cyberpi.led.show('red orange yellow green cyan')
```

Encender un LED específico de la tira (r, g, b, numLed):
```python
cyberpi.led.on(255, 0, 0, 1)
```

---

### Pantalla

Mostrar texto en pantalla:
```python
cyberpi.console.println("makeblock")
```

Borrar pantalla:
```python
cyberpi.console.clear()
```

Mostrar icono en pantalla `Image`, `Play`, `Light`, `Music`, `Clock`, `Motion`, `Home`, `Shut_down`, `Rocket`, `Fire`, `Color`...:
```python
icono = cyberpi.sprite() #Se crea una variable icono antes de los bucles y condicionales
icono.draw_pixel("Image")
```
---

### Pulsación de botones y joystick:

Joystick `middle`, `up`, `down`, `left`, `right`:
```python
while True:
  if cyberpi.controller.is_press('middle'):
```

Botones `a`, `b`:
```python
while True:
  if cyberpi.controller.is_press('a'):
```

---

### Sensores

Inclinación de la placa `tiltforward`, `tiltbackward`, `tiltleft`, `tiltright`, `faceup`, `facedown`:
```python
while True:
  if cyberpi.is_tiltforward():
```

Intensidad de la luz (comparamos con `==`, `<`, `>`) (valores 0-100):
```python
while True:
  if cyberpi.get_bri() == 50:
```
      

