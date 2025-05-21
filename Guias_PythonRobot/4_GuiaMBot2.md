## Importar extensiones necesarias

Para programar a mBot2 debemos importar múltiples extensiones, desde la de cyberpi, tiempo, detección de pulsaciones en botones, movimientos del mbot y sensores de distancia y siguielíneas. En general, podemos importarlo todo con la siguiente línea:

```python
import event, time, cyberpi, mbot2, mbuild
```

## Movimientos

**Avanzar:**

Utilizando las mismas funciones podemos avanzar `forward` o retroceder `backward`. También se puede avanzar por centímetros con `straight`.
```python
mbot2.forward(50, 1) #velocidad 50, 1 segundo
mbot2.forward(50)    #velocidad 50, indefinidamente
mbot2.straight(100)  #avanzar un número de centímetros exactos
```

**Giros:**

Existen varias formas de programar giros.
```python
mbot2.turn_left(50, 1) #girar a velocidad 50, 1 segundo
mbot2.turn_right(50)   #girar a velocidad 50, indefinidamente
mbot2.turn(-90)        #girar 90 grados
```

**Detener robot:**

Aunque puede detenerse al robot indicando que avance a velocidad 0, existen otras funciones más adecuadas:
```python
mbot2.EM_stop("ALL")  #Parar todos los motores (ambas ruedas)
mbot2.EM_stop("EM1")  #Parar rueda conectada a motor EM1
mbot2.EM_stop("EM2")  #Parar rueda conectada a motor EM2
```

## Ultrasonic Sensor (detector de obstáculos)

Podemos comprobar la distancia a la que el sensor de ultrasonidos detecta un obstáculo gracias al mbloque `ultrasonic2`, comparando con los símbolos `<`, `>`, `==`, `>=`, `<=` y la distancia deseada. Recordar que el sensor detecta correctamente distancias mayores a 5cm y menos a 200cm.

```python
if mbuild.ultrasonic2.get(1) < 50:
  # Programación a realizar
```

## Quad RGB Sensor (sensor siguelíneas)

Para utilizar el sensor siguelíneas de mBot2 usaremos el bloque `quad_rgb_sensor`, con la siguiente programación:
```python
if mbuild.quad_rgb_sensor.get_line_sta("middle", 1) == 1:
```
El estado tiene diferentes números, que significan:
|Estado|Significado|
|------|-----------|
|`== 0`| Los 2 sensores detectan blanco |
|`== 1`| Izquierda detecta blanco, derecha detecta negro |
|`== 2`| Izquierda detecta negro, derecha detecta blanco |
|`== 3`| Los 2 sensores detectan negro |

Veámoslo más claro en una imagen:
![image](https://github.com/user-attachments/assets/39c763df-835b-4a85-befe-d813fa136b41)

