# resaltado-rojo-imagen
resaltado-rojo-imagen


lower_red1 = np.array([0, 20, 20])
upper_red1 = np.array([4, 255, 255])

lower_red2 = np.array([170, 50, 50])
upper_red2 = np.array([180, 255, 255])

El color rojo en HSV se localiza en dos rangos de tonalidad (H):
Primer rango: cerca del 0°.
Segundo rango: cerca del 180° (al final del círculo de color HSV).

En la parte inferior del rojo (0 a 4 grados de tonalidad), se permiten valores bajos de saturación y valor ([20, 20]). Esto incluye rojos muy suaves, apagados, pasteles, e incluso ligeramente marrones o anaranjados.

En la parte superior del rojo (170 a 180 grados), se dejaron valores más altos de saturación y valor ([50, 50]), lo que filtra colores más intensos, vivos, brillantes.


Al usar saturación baja (S=20) y valor bajo (V=20) en el rango inferior (0-4), capturas una gama más amplia de tonos rojos sutiles, lo que incluye algunos tonos cercanos al rojo que podrías haber omitido antes.
En el rango superior (170-180), mantuviste un umbral más estricto (S=50, V=50), por lo que ahí excluiste colores pastel o más suaves, lo que evita que piel rosada o cabellos claros entren dentro de la máscara.
