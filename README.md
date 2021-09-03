## EXPLORACION Y CURACIÓN DE DATOS 2021

Estos archivos corresponden al Entregable 2 de la materia Exploración y Curación de Datos:
- Entregable_2_Parte_1.ipynb, inicia leyendo un dataset dado y finaliza guardando localmente en la PC del usuario el dataset resultante (puede aparecer la ventana del navegador para descargar el archivo)
- Entregable_2_Parte_2.ipynb, inicia leyendo ese dataset resultante (Entregable_2_Parte_1) que fue previamente subido a este proyecto

Respecto de los **criterios aplicados para la exclusión de ejemplos**, señalamos que no se excluyó ninguna fila del dataset original; se consideraron todos los datos.

Acerca de las **características categóricas** del dataset, identificamos lo siguientes valores posibles en estos campos de interés:
  1. campo Suburb: suburbio donde está ubicada la propiedad.  314 valores posibles  
  2. campo Regionname: región geográfica donde está la propiedad:  8 valores posibles  
  3. campo CouncilArea: área geográfica donde está la propiedad:  33 valores posibles  

Las características categóricas fueron codificadas con un método OneHotEncoding, utilizando como máximo los siguientes umbrales de valores frecuentes:  
  para Suburb: un mínimo de 100 valores más frecuentes  
  para Regionname: un mínimo de 70 valores frecuentes  
  para CouncilArea: un mínimo de 70valores frecuentes  
 
Acerca de las **características numéricas** del dataset, encontramos que:
  1. campo Rooms: cantidad de habitaciones de la propiedad.  9 valores posibles  
  2. campo Landsize: tamaño del terreno de la propiedad:  1448 valores  
 
Las características categóricas fueron codificadas con un método OneHotEncoding, utilizando como máximo los siguientes umbrales de valores frecuentes:
. para Rooms: un mínimo de 70 valores frecuentes  
. para Landsize: se clasificaron los valores de este campo Landsize en rangos, de acuerdo a los siguientes rangos de valores de ese campo, y se consideraron todas las categorías    

Valor de Landsize  
| (desde - hasta) | Frecuencia absoluta |
|:----------------|:--------------------|
|     0 -   1   |     2     |
|     1 -  100  |   326     |
|   100 -  200  |  1548     |
|   200 -  300  |  1454     |
|   300 -  400  |  1179     |
|   400 -  500  |   957     |
|   500 -  600  |  1701     |
|   600 -  700  |  2041     |
|   700 -  800  |  1065     |
|   800 -  900  |   476     |
|   900 - 1000  |   226     |
|  1000 - 2000  |   428     |
|  2000 - 3000  |   103     |

Todas las características numéricas fueron estandarizadas, utilizando IterativeImputer, con KNN-KNeighborsRegressor.
 
Respecto de datos aumentados, se agregan las 5 primeras columnas obtenidas a través del método de PCA, aplicado sobre el conjunto de datos totalmente procesado.

