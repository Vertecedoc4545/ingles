# Parámetros de control de aceleración/desaceleran
| #7   | #6   | #5   | #4   | #3   | #2   | #1   | #0   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|      |      | NCI  | RTO  |      | OVB  |      |      |
|      |      | NCI  | RTO  |      |      |      |      |

[Tipo de datos] Bit

 OVB:  Solapamiento de bloque de la alimentación de corte
   0: Los bloques no están solapados en la alimentación de corte
   1: Los bloques están solapados en la alimentación de corte
   El solapamiento de bloques saca los pulsos restantes en el final de la distribucion de pulsos con la distribucion de pulsos del bloque siguiente.
   Eliminando los cambios en las tazas de alimentacion entre bloques.

   El solapamiento de bloques esta habilitado cuando contienen G01,G02 o G03 y esta consecutivamente especificado en el modo G64. Sin embargo si los bloques de minutos estan especificados consecutivamente, el solapamiento podria no ser aplicado.
   Los pulsos siguientes en el bloque F2 son añadidos a los pulsos restantes en el final de la distribucion en el bloque F1
> 
$$(Numero\space de\space pulsos\space a\space ser\space a\tilde{n}adidos) = F2 \times \frac{(Numero\space de\space pulsos\space requeridos\space en\space el\space final\space del\space bloque\space F1)}{F1}$$
> 
  RTO Solapamiento de bloques en marcha rapida
  0: bloques no estan en solapados en marcha rapida
  1: bloques no estan en solapados en marcha rapida
> **NOTA**
> > Ve la descripcion del parametro No.1722

NCI Control de imposición en la desaceleración
0: Aplicado
1: No aplicado 

---------

61

---
﻿﻿﻿

|1620|
| :- |

|Constante de tiempo T o T1 utilizada para la aceleración/deceleración lineal o en forma de campana aceleración/desaceleración en marcha rápida para cada eje|
| :- |

[Tipo de datos] Palabra eje

[Unidad de datos] ms

[Rango de datos válido] 0 a 4000

Especifique una constante de tiempo utilizada para la aceleración/desaceleración en el avance rápido. verso. Cuando se proporciona la función opcional de aceleración/deceleración en forma de campana en deceleración en marcha rápida, la aceleración/desaceleración en forma de campana se en forma de campana. Si no se ha previsto la función, se aplica la aceleración/desaceleración lineal en la marcha rápida. se aplica la aceleración/desaceleración lineal.

1. Cuando se proporciona la función, ajuste este parámetro a la constante de tiempo T1 utilizada en la aceleración/deceleración en forma de campana en la marcha rápida, y ajuste el parámetro No.1621 a la constante de tiempo T2.
1. Cuando no se proporciona la función, especifique una constante de tiempo utilizada en la aceleración/desaceleración lineal.



**NOTA**
<p></p><p>1. Cuando el parámetro nº 1621 (constante de tiempo T2 utilizada para la aceleración/desaceleración en forma de campana en la marcha rápida) se ajusta a 0, la aceleración/desaceleración lineal se aplica en la marcha rápida incluso si la función está prevista. rápida, incluso si la función está prevista. En este caso, este parámetro representa una constante de tiempo utilizada en la en la aceleración/desaceleración lineal en la marcha rápida.</p><p>2. Dependiendo del valor de ajuste de la constante de tiempo, la velocidad ligeramente inferior a la velocidad de avance rápido puede aplicarse durante un tiempo determinado mientras se alcanza la velocidad de desplazamiento rápido después de la aceleración. Para solucionar este problema, establezca un múltiplo de 8 como constante de tiempo.</p>

---

64

---

|1622 |
| :- |


Ajuste el valor cuando la velocidad de desplazamiento rápido es del 100%. Si es inferior al 100%, el tiempo total se reduce. (Método de aceleración constante)

El valor de T1 se determina a partir del par del motor. Por lo general, ajuste el valor de T2 a 24 ms o 32 ms.


|1621 |
| :- |

|Constante de tiempo t T2 utilizada para la aceleración/desaceleración en forma de campana en marcha rápida para cada eje|
| :- |


[Tipo de datos] Palabra eje

[Unidad de datos] ms

[Rango de datos válido] 0 a 512

Especifique la constante de tiempo T2 utilizada para la aceleración/deceleración en forma de campana en marcha rápida para cada eje.

**NOTA**

<p>1. Este parámetro es efectivo cuando la función de aceleración/deceleración en forma de campana en forma de campana en la marcha rápida. Ajuste el parámetro parámetro nº 1620 a la constante de tiempo T1 utilizada para aceleración/desaceleración en forma de campana en la marcha rápida, y ajuste este parámetro a la constante de tiempo T2.</p><p>Para los detalles de las constantes de tiempo T1 y T2, véase la descripción del parámetro No.1620.</p><p>2. Cuando este parámetro se ajusta a 0, la aceleración/desaceleración lineal se aplica en la marcha rápida. Desaceleración se aplica en la marcha rápida. El ajuste en el parámetro nº 1620 se utiliza como constante de tiempo en la aceleración/desaceleración lineal. aceleración/desaceleración lineal.</p><p></p> 



|1622|
| :- |

|Constante de tiempo de la aceleración/deceleración exponencial o de la aceleración/deceleración en forma de campana tras la interpolación, o de la aceleración/deceleración lineal tras la interpolación en el avance de corte para cada eje|
| :- |


---

65

---

[Tipo de datos] Eje Word

[Unidad de datos] ms

[Rango de datos] 0 a 4000 (aceleración/deceleración exponencial en el avance de corte) 0 a 512 (aceleración/deceleración lineal después de la interpolación en el avance de corte)

Ajuste la constante de tiempo utilizada para la aceleración/deceleración exponencial en el avance de corte o la aceleración/deceleración lineal después de la interpolación en el avance de corte para cada eje. El tipo a seleccionar depende de los ajustes del parámetro CTLx (bit 0 del nº 1610). Salvo en aplicaciones especiales, debe ajustarse la misma constante de tiempo para todos los ejes en este parámetro. Si las constantes de tiempo ajustadas para los ejes difieren entre sí, no se pueden obtener líneas rectas y no se pueden obtener líneas rectas y arcos adecuados.

Este parámetro es válido para el roscado, independientemente del tipo de aceleración/deceleración. Para los ciclos de roscado G76 y G92 (G78 en el sistema de código G B o C), este parámetro es válido para las operaciones que no sean la aceleración/deceleración exponencial. (Serie T)


|1623|
| :- |

|Velocidad FL de aceleración/deceleración exponencial en el avance de corte para cada eje|
| :- |


[Data type] Word axis

[Unit of data]

[Valid data range]


|Sistema de incrementos |Unidad de datos|rango de datos válido|
| :- | :- | :- |
|||IS-A, IS-B|IS-C|
|Máquina de milímetros|1 mm/min|0,6 a 15000|0,6 a 12000|
|Máquina de pulgadas|0.1 inch/min|0,6 a 6000|0,6 a 4800|
|Eje de rotación|1 deg/min|0,6 a 15000|0,6 a 12000|

Establezca el límite inferior (tasa FL) de la aceleración/deceleración exponencial en el avance de corte para cada eje.


**NOTA**
<p>Salvo en aplicaciones especiales, este parámetro debe ajustarse a 0 para todos los ejes. Si se especifica un valor distinto de 0, no se pueden obtener líneas y arcos rectos adecuados.</p>

---

66

---

