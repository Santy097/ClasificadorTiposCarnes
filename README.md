# ClasificadorTiposCarnes
Clasificador de tipos de carnes mediante redes neuronales.

INTRODUCCIÓN
El propósito del proyecto es identificar un tipo de carne (8 clases) mediante imágenes.

PREPARACIÓN DEL DATASET
Existen 2 dataset, el primero se utilizará para el entrenamiento y el segundo para las pruebas.
Los dataset están formado como se muestra a continuación:

TRAIN
	CLASE 	      CANTIDAD DE DATOS
	CLASE 01      	0
	CLASE 02	      62
	CLASE 03	      213
	CLASE 04	      105
	CLASE 05	      949
	CLASE 06	      37
	CLASE 07	      204
	CLASE 08	      63

TEST	
  CLASE 01	      1
	CLASE 02	      48
	CLASE 03	      97
	CLASE 04      	45
	CLASE 05	      459
	CLASE 06	      19
	CLASE 07	      114
	CLASE 08       	27

Se utilizaron las siguientes técnicas
•	Conversión a escala de grises.
•	Conversión de BGR (azul, verde, rojo) a RGB (rojo, verde, azul).
•	Reducción de ruido.
•	Cambiar el tamaño de las imágenes.
•	Normalización de pixeles.

Se aplicaron varias combinaciones de estas técnicas. La combinación de técnicas que permitió obtener el mayour porcentaje de accuracy es:
•	Conversión de BGR (azul, verde, rojo) a RGB (rojo, verde, azul).
•	Cambiar el tamaño de las imágenes.

ARQUITECTURA DEL MODELO
El modelo tiene una arquitectura CNN con capas convolucionales, capas de pooling y capas totalmente conectadas, lo que lo hace apto para clasificación de imágenes.

Consta de las siguientes capas:
1) Capa Conv2D (Convolutional): 32 filtros, esta capa convolucional realiza convoluciones en la imagen de entrada. Los filtros aprenden patrones locales en la imagen utilizando ventanas de 3x3 píxeles y aplicando la función de activación ReLU.
2) Capa MaxPooling2D: (2, 2). Esta capa de pooling reduce la dimensionalidad de la salida de la capa convolucional, tomando el valor máximo en una ventana de 2x2 píxeles. Esto ayuda a reducir el costo computacional y a extraer características importantes.
3) Capa Conv2D: 64 filtros, esto ayuda al modelo a aprender patrones más complejos en la imagen.
4) Capa MaxPooling2D: (2, 2). Ayuda a reducir la dimensionalidad.
5) Capa Conv2D: 128 filtros.
6) Capa MaxPooling2D: (2, 2). reduce la dimensionalidad.
7) Capa Flatten: Esta capa aplana la salida de la capa anterior, convirtiendo los mapas de características 2D en un vector unidimensional.
8) Capa Dense (totalmente conectada): 128 neuronas
9) Capa Dense (salida): num_classes neuronas. La capa de salida, que tiene tantas unidades como clases en tu conjunto de datos.

RESULTADOS
Para los datos de training el accuracy fue de 1,00
Para los datos de test el accuracy máximo obtenido fue de 0,89

Resultados Training
![image](https://github.com/Santy097/ClasificadorTiposCarnes/assets/58237041/4c0f2c2b-0b0e-4d94-93d8-a50a5d55e824)

Resultados Test
![image](https://github.com/Santy097/ClasificadorTiposCarnes/assets/58237041/77b1e874-ff05-4856-a995-62d8d417bd79)








