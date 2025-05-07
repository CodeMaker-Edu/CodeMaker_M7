**Ejercicio 1: detección básica de obstáculo**

Codey avanza por la mesa a velocidad 50 (sin tiempo) y al detectar un obstáculo, gira y se da media vuelta (es decir, vuelve por donde ha venido).

**Ejercicio 2: el robot que nunca cae**

Codey se mueve aleatoriamente por la mesa pero nunca se cae (el sensor de obstáculos debe detectar la mesa, en vez de detectar obstáculos delante).

**Ejercicio 3: el robot que detecta colores**

Codey está quieto y si el alumno le acerca tarjetas rojas, verdes y azules, las detecta y reacciona encendiendo el led de la cabeza y mostrando en pantalla el color que ha detectado.

**Ejercicio 4: el circuito de colores**

Codey avanza en línea recta mientras detecte el suelo blanco. Cuando detecte color, realizará las siguientes maniobras:
- Al detectar rojo, gira 90 grados a la izquierda.
- Al detectar verde, gira 90 grados a la derecha.
- Al detectar amarillo, retrocede durante 1 segundo.
- Al detectar negro, sigue avanzando hasta detectar morado y se detiene ahí durante 10 segundos (ojo, si detecta morado sin haber detectado negro antes, lo ignora).

**Ejercicio 5: El robot crafteador**

Codey Rocky se ha convertido en un robot recolector dentro del mundo de Minecraft. Su misión es explorar y recoger bloques (representados por colores) para luego usarlos en una mesa de crafteo automática. Al juntar ciertos bloques, podrá crear herramientas, objetos o materiales nuevos.

Codey se desplaza por el suelo y frente a él tendrá 3 tarjetas de colores, que representarán un bloque de minecraft cada una. Para detectar bien los bloques deberá avanzar hasta que se encuentre uno, ahí detenerse un momento para ver qué color es, guardarlo en su memoria y después avanzar hasta el siguiente.

Los bloques son:
| Color detectado | Bloque u objeto relacionado en Minecraft |
|-----------------|------------------------------------------|
| `red`           | Redstone                                 |
| `green`         | Bloque de esmeralda                      |
| `blue`          | Lapislázuli                              |
| `yellow`        | Lingote de oro                           |
| `cyan`          | Prismarina                               |
| `purple`        | Amatista                                 |
| `black`         | Carbón                                   |
| `white`         | Bloque de hueso                          |

Cuando el robot haya detectado los 3 bloques, avanzará durante 3 segundos y mostrará en pantalla el objeto que ha podido craftear con ellos. Las posibilidades son:

| Combinación de colores               | Objeto crafteado         |
|--------------------------------------|--------------------------|
| red + green + blue                   | Espada mágica            |
| red + yellow + black                 | Dinamita (TNT)           |
| blue + white + black                 | Pico de diamante         |
| green + green + yellow               | Arco                     |
| cyan + blue + white                  | Tridente                 |
| red + purple + black                 | Poción de invisibilidad  |
| yellow + red + blue                  | Portal al Nether         |
| green + white + white                | Armadura de cuero        |
| purple + cyan + black                | Cañón de Ender           |
| white + black + red                  | Escudo                   |
