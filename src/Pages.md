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
   > $$ (Numero\space de\space pulsos\spoce a\space ser\space añadidos) = F2 \times \frac{(Numero\space de\space pulsos\space requeridos\space en\space el\space final\space del\space bloque\space F1)}{F1}$$
   > 


​    

