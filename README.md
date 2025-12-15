#Actividad 1 (Modificar y explicar un estado)

-Modifiqué el estado typeFilter, cambiando su valor inicial de "all" a "cow".
Visualmente, al cargar la aplicación el filtro de tipo ya está seleccionado y la lista muestra solo animales de ese tipo. Esto se debe a que el estado se usa para filtrar los datos antes del renderizado, por lo que React renderiza únicamente los elementos que cumplen la condición desde el primer render.