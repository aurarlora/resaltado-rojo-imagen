# resaltado-rojo-imagen
resaltado-rojo-imagen

Se aplicó una segmentación por umbral en el espacio HSV para aislar los tonos rojos. Debido a que el color rojo abarca dos regiones opuestas del eje de tono (Hue), se definieron dos rangos: uno cercano a 0° y otro cercano a 180°, combinados mediante máscaras binarias. Cada rango se definió con pares mínimo-máximo que controlan el tono, la saturación y el valor, permitiendo filtrar los colores deseados con mayor precisión.

Estos pares indican:
Hue: qué color es (0–180 en OpenCV, donde 0 y 180 son rojo).
Saturation: qué tan puro es el color (0 es gris, 255 es color intenso).
Value: qué tan claro u oscuro es (0 es negro, 255 es brillo máximo).

lower_red1 = np.array([0, 20, 20])
upper_red1 = np.array([4, 255, 255])

El color rojo en HSV se localiza en dos rangos de tonalidad (H):
Primer rango: cerca del 0°.
Segundo rango: cerca del 180° (al final del círculo de color HSV).

En la parte inferior del rojo (0 a 4 grados de tonalidad), se permiten valores bajos de saturación y valor ([20, 20]). Esto incluye rojos muy suaves, apagados, pasteles, e incluso ligeramente marrones o anaranjados.

En la parte superior del rojo (170 a 180 grados), se dejaron valores más altos de saturación y valor ([50, 50]), lo que filtra colores más intensos, vivos, brillantes.


Al usar saturación baja (S=20) y valor bajo (V=20) en el rango inferior (0-4), capturas una gama más amplia de tonos rojos sutiles, lo que incluye algunos tonos cercanos al rojo que podrías haber omitido antes.
En el rango superior (170-180), mantuviste un umbral más estricto (S=50, V=50), por lo que ahí excluiste colores pastel o más suaves, lo que evita que piel rosada o cabellos claros entren dentro de la máscara.
