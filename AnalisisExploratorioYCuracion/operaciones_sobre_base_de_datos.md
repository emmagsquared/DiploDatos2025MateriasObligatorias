## Criterios de exclusion de ejemplos
    1. Registro con 10 habitaciones (Rooms  = 10)
    2. Registros con Bathroom > Rooms
    3. Registro con Landsize mayor a 10.000
    4. Registros con BuildingArea mayor que Landsize
    5. Registros con años de construccion anteriores a 1800
    6. Registros con precios mayores a 5.000.000.

## Caracteristicas seleccionadas
### Caracteristicas categoricas
1. Type: tipo de propiedad. 3 valores posibles
2. Suburb: Suburbio donde se encuentra la propiedad.
Todas las caracteristicas categoricas fueron codificadas con un
metodo OneHotEncoding utilizando como maximo sus 20 valores mas
frecuentes.

### Caracteristicas numericas
1. Rooms: Cantidad de habitaciones
2. Bathroom: Numero de baños en la propiedad
3. Car: Numero de espacios disponibles para estacionamiento de automoviles.
4. Landsize: Tamaño del terreno (en metros cuadrados)
5. Distance: Distancia al centro de la ciudad
6. Price: Precio de venta
7. BuildingArea: Área construida de la propiedad (en metros cuadrados) -tamaño habitable o edificado de la casa-
8. YearBuilt: Año de construccion de la propiedad
9. airbnb_mean_price: Se agrega el precio promedio diario de
    publicaciones de la plataforma AirBnB en el mismo codigo
    postal. [Link al repositorio con datos externos].

### Transformaciones:
1. Las columnas YearBuilt y BuildingArea fueron imputadas utilizando un algoritmo de imputacion multiple con predictor KNN con k=1, habiendo sido previamente escaladas en el intervalo [-1,1]. Luego fueron restablecidas a su rango original antes de ejecutar la siguiente transformacion.
2. Todas las caracteristicas numericas fueron estandarizadas restando la media y escalando los datos de acuerdo al intervalo intercuartil (rango entre el primer y tercer cuartil).

### Datos aumentados
1. Se agregan las 2 primeras columnas obtenidas a traves del
    metodo de PCA, aplicado sobre el conjunto de datos
    totalmente procesado.
