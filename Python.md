### Guía de Python para Robótica

Esta guía cubre los conceptos fundamentales de Python que necesitarás para empezar a programar tus robots Makeblock con Python.

#### 1. Variables

Una variable es como una caja donde puedes guardar información. Le das un nombre a la caja y luego puedes poner o sacar cosas de ella. En programación, esa "información" pueden ser números, texto, valores lógicos (verdadero/falso), etc.En Python, creas una variable simplemente dándole un nombre y asignándole un valor con el signo =.# Creamos una variable llamada 'velocidad' y le asignamos el número 100

```python
velocidad = 100
mensaje = "¡Hola, robot!"
encendido = True
```

Puedes imprimir el valor de una variable
```python
print(velocidad)
print(mensaje)
print(encendido)
```
Reglas para los nombres de variables:
- Deben empezar con una letra o un guion bajo (_).
- Pueden contener letras, números y guiones bajos.
- Son sensibles a mayúsculas y minúsculas (velocidad es diferente de Velocidad).
- No pueden ser palabras reservadas de Python (como if, for, while, print, etc.).

#### 2. Condicionales (if, elif, else)

Los condicionales te permiten tomar decisiones en tu programa. Le dices al robot: "Si pasa ESTO, haz ESTO otro; si no, haz AQUELLO". 

La estructura básica es if. Puedes añadir elif (abreviatura de "else if", "si no, si...") para comprobar otras condiciones si la primera no se cumple, y else ("si no") para especificar qué hacer si ninguna de las condiciones anteriores se cumple.

```python
distancia = 30

# Si la distancia es menor que 20, el robot se detiene
if distancia < 20:
    print("Obstáculo detectado, deteniendo robot.")
    # Aquí iría el código para detener el robot
elif distancia < 50:
    # Si no es menor que 20, pero sí es menor que 50, reduce la velocidad
    print("Obstáculo cercano, reduciendo velocidad.")
    # Aquí iría el código para reducir velocidad
else:
    # Si no se cumple ninguna de las condiciones anteriores, sigue adelante
    print("Camino libre, avanzando.")
    # Aquí iría el código para avanzar
```
Puntos clave:
- La condición después de if o elif debe ser algo que pueda ser Verdadero (True) o Falso (False).
- Se utilizan dos puntos (:) al final de la línea if, elif, y else.
- El código que pertenece a cada bloque (if, elif, else) debe estar indentado (con espacios o tabulaciones) respecto a la línea anterior.
- La indentación (el espacio al principio de las líneas con tabulador) es crucial en Python.

#### 3. Bucles (for, while)

Los bucles te permiten repetir un bloque de código varias veces. Esto es muy útil para tareas repetitivas.

**Bucle for**

El bucle for se usa a menudo para iterar sobre una secuencia (como una lista de números o caracteres) o para repetir algo un número específico de veces. La función range() es muy común con for para repetir un número de veces. range(n) genera una secuencia de números desde 0 hasta n-1.

Repetir una acción 5 veces
```python
for i in range(5):
    print(f"Repetición número: {i}") # f-string permite incluir el valor de la variable i
```

Iterar sobre una lista de colores
```python
colores = ["rojo", "verde", "azul"]
for color in colores:
    print("El color actual es: ", color)
```

**Bucle while**

El bucle while repite un bloque de código mientras una condición sea verdadera. Es útil cuando no sabes de antemano cuántas veces necesitas repetir algo, sino que dependes de que se cumpla o deje de cumplirse una condición.

Ejemplo: Mover el robot mientras un sensor no detecte luz

```python
# Mientras el nivel de luz sea mayor que 50, sigue moviendo el robot
while nivel_luz > 50:
    print("Nivel de luz: ", nivel_luz, ". Moviendo robot...")
    # Aquí iría el código para mover el robot
    # En un robot real, leerías el sensor de luz aquí: nivel_luz = sensor_luz.read()
```

print("Nivel de luz bajo, deteniendo bucle.")

Puntos clave:
- En el bucle while, asegúrate de que la condición eventualmente se vuelva falsa para evitar bucles infinitos.
- Usa break para salir de un bucle prematuramente.
- Usa continue para saltar el resto del código en la iteración actual y pasar a la siguiente.
