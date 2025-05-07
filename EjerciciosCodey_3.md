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

**Ejercicio 5: zonas contaminadas**

Codey Rocky va avanzando tranquilamente por la mesa, y cuando detecta una zona roja o morada significa que es una zona contaminada. En ese caso, debe emitir un sonido de alarma, mostrar algo para alertar en pantalla, encender su led (de Codey) de color rojo o morado, y hacer una maniobra para esquivar la zona y seguir en la misma dirección en la que iba.

Además, mientras continua hacia adelante después de esquivar la zona peligrosa, mostrará en pantalla cuántas zonas peligrosas ha detectado ya.

**Ejercicio 6: El robot crafteador**

Codey Rocky se ha convertido en un robot recolector dentro del mundo de Minecraft. Su misión es explorar y recoger bloques (representados por colores) para luego usarlos en una mesa de crafteo automática. Al juntar ciertos bloques, podrá crear herramientas, objetos o materiales nuevos.

Codey estará quieto y pasarás frente a él 3 tarjetas de colores, una después de otra, que representarán un bloque de minecraft cada una. Codey guardará en memoria los colores que está detectando.

Los bloques son:

| Color detectado | Bloque u objeto relacionado en Minecraft |
|-----------------|------------------------------------------|
| `red`           | Redstone                                 |
| `green`         | Bloque de esmeralda                      |
| `blue`          | Lapislázuli                              |
| `yellow`        | Lingote de oro                           |
| `cyan`          | Diamante                                 |
| `purple`        | Amatista                                 |
| `black`         | Carbón                                   |

Cuando el robot haya detectado los 3 bloques, mostrará en pantalla el objeto que ha podido craftear con ellos. Las posibilidades son (deben darse en ese orden):

| Combinación de colores               | Objeto crafteado         |
|--------------------------------------|--------------------------|
| red + green + blue                   | Espada mágica            |
| red + yellow + black                 | Dinamita (TNT)           |
| green + green + yellow               | Arco                     |
| red + purple + black                 | Poción de invisibilidad  |
| yellow + red + blue                  | Portal al Nether         |
| purple + cyan + black                | Cañón de Ender           |
