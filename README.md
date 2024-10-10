# Como-ser-ub-buen-Ingeniero
## Link del repositorio
https://github.com/PabloAlcoleaSesse/Como-ser-ub-buen-Ingeniero-/blob/main/README.md

## Resolución 

Según el enunciado del problema, dependiendo de la posición inicial, el caballo podrá realizar cero, dos o tres posibles movimientos en "L". Por lo tanto, podemos verificar las diferentes opciones según el número de inicio: desde el 0 puede ir al 4 o al 6 (dos opciones); desde el 1 puede ir al 6 o al 8 (dos opciones); desde el 2 puede ir al 7 o al 9 (dos opciones); desde el 3 puede ir al 4 o al 8 (dos opciones); desde el 4 puede ir al 3, al 9 o al 0 (tres opciones); desde el 5 no tiene movimientos posibles (cero opciones); desde el 6 puede ir al 1, al 7 o al 0 (tres opciones); desde el 7 puede ir al 2 o al 6 (dos opciones); desde el 8 puede ir al 1 o al 3 (dos opciones); y, por último, desde el 9 puede ir al 2 o al 4 (dos opciones).

De manera esquemática, esto se puede representar así:

C(0) = (4, 6)
C(1) = (6, 8)
C(2) = (7, 9)
C(3) = (4, 8)
C(4) = (3, 9, 0)
C(5) = (0)
C(6) = (1, 7, 0)
C(7) = (2, 6)
C(8) = (1, 3)
C(9) = (2, 4)

Si sumamos todos los posibles caminos desde cada número, obtenemos el número de movimientos posibles con un único movimiento: 2 + 2 + 2 + 2 + 3 + 0 + 3 + 2 + 2 + 2 = 20, lo cual coincide con la información proporcionada en el enunciado.

Después de calcular los movimientos posibles con un solo movimiento, pasamos a calcular las posibilidades con dos movimientos. Imaginemos que tenemos un conjunto de posibilidades 𝑀, que representa la posición inicial 𝑛 y el número de movimientos restantes 𝑁. Por ejemplo, las posibilidades desde el 0 con dos movimientos serían:

M(0,2)=M(4,1)+M(6,1)=3 posibilidades+3 posibilidades=6 posibilidades.

El número de caminos desde el 1 con dos movimientos sería:
M(1,2)=M(6,1)+M(8,1)=3 caminos+2 caminos=5 caminos.

De esta forma, se puede calcular el número de posibilidades con dos movimientos para el resto de los números. Al sumar todos los resultados, obtenemos un total de 46 posibilidades para dos movimientos, lo cual coincide con los datos proporcionados en el enunciado.

Siguiendo el mismo razonamiento, podemos expresar la fórmula que usamos para calcular los caminos posibles de la siguiente manera:

𝑀(𝑢,𝑛)=∑𝑖=0𝑘(1+𝑀(𝑠𝑖𝑔𝑢𝑖𝑒𝑛𝑡𝑒_𝑚𝑜𝑣𝑖𝑚𝑖𝑒𝑛𝑡𝑜[𝑖],𝑛−1))


Con este algoritmo, podemos calcular los resultados de los movimientos dados en la tabla y completar la misma. Por ejemplo:

| Nº pasos | Simulacion        |
|----------|-------------------|
| 1        | 20                |
| 2        | 46                |
| 3        | 104               |
| 5        | 544               |
| 8        | 6576              |
| 10       | 34432             |
| 15       | 2140672           |
| 18       | 25881088          |
| 21       | 307302400         |
| 23       | 1609056256        |
| 32       | 2792668987392     |
