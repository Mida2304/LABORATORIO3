<h1 align="center"> LABORATORIO 3. PROBLEMA DEL COCTEL </h1>

Autores: Midalys Vanessa Aux y Manuela Martinez

# Introducción
Como solemos divisar en la actualidad, alrededor del mundo se suelen realizar muchos eventos llamados Fiestas de cóctel. Por si no lo sabias, esta es un evento social dónde se sirven estas famosas bebidas alcohólicas (los cócteles), y a menudo también algunos aperitivos ligeros como bocadillos, canapés, entre otros. 

Este ambiente suele ser uno de tipo informal y relajado a comparación de otros tipos de eventos formales como galas; sin embargo, el foco más importante es que como tal no hay foco principal, esto quiere decir que, a pesar de que se puede celebrar una ocasión especial como reuniones de negocios o aniversarios, usualmente los invitados hablan de diversidad de temas entre ellos, no hay uno especifico, lo que fomenta un ambiente mucho más interactivo.

Ahora, probablemente te estarás preguntando "Esto que tiene que ver con el área de Procesamiento de Señales", y tranquilo, aquí te lo explico. Esta práctica de laboratorio es denominada "Problema deL cóctel", donde se busca "aplicar el análisis en frecuencia de señales de voz en un problema de captura de señales mezcladas"; es decir, "el problema de la "Fiesta de cóctel" se refiere a la capacidad de un sistema para concentrarse en una sola fuente sonora mientras filtra las demás en un entorno con múltiples emisores de sonido".


### Procedimiento:
Gracias a lo anteriormente mencionado, el procedimiento a realizar será el siguiente: 
##### • Configuración del sistema: En primera instancia, se van a conectar dos micrófonos al sistema de adquisición de datos, estos deben estar ubicados de manera que cada uno capture distintas combinaciones de las señales provenientes de las dos fuentes (en este caso, el número fuentes y micrófonos va a depender de cuantas personas sean quienes integren el grupo, en este caso fueron dos micrófonos y dos fuentes puesto que el grupo esta conformado por dos personas). Así mismo, las personas deben estar posicionadas de forma fija dentro de un espacio escogido a distancias y orientaciones distintas para poder simular un entorno de "Fiesta de cóctel".

##### • Captura de la señal: Posteriormente, se debe generar la señal mediante la voz de cada uno de las personas que se encuentren en la prueba durante un tiempo de captura de la señal. Se deben obtener las señales durante cierto tiempo determinado, unicamente que al principio se debe dejar un espacio de tiempo determinado con ruido blanco para poder medir el SNR de este (se debe repetir la medición en caso de que el SNR de alguna de las señales no sea suficiente. Argumentar las razones). 

##### • Procesamiento de la señal: Gracias a lo anterior, teniendo las señales establecidas, se debe realizar un análisis temporal y espectral de las señales capturadas por cada micrófono, identificando las características principales de cada fuente sonora. Para ello, es necesario utilizar la trasnformada de Fourier discreta (DFT) o la transformada rápida de Fourier (FFT), describiendo la información que se puede obtener con cada una de ellas. De igual forma, se deben investigar los métodos de separación de fuentes, como el Análisis de Componentes Independientes (ICA), el Beamforming, entre otros, para aislar la señal de interés a partir de las señales capturadas por los micrófonos. 

##### • Por último, se procede a evaluar los resultados comparando la señal aislada con la señal original usando métricas de calidad como la relación señal/ruido para así, de esta forma, cualificar el desempeño de la separación.

### Conceptos para tener en cuenta:
##### • Transformada de Fourier: 
[^1^] La transformada de Fourier descompone una señal en sus componentes de frecuencia. En otras palabras, convierte una señal en el dominio del tiempo en una representación que permite divisar la distribución de sus frecuencias. 
[^1^]: FFT. MathWorks. (n.d.). https://la.mathworks.com/help/matlab/math/fourier-transforms.html 

Esto es de gran utilidad puesto que muchas señales complejas pueden analizarse de manera más fácil cuando se descomponen en componentes de frecuecia simples (funciones de senos y de cosenos). Esta herramienta es fundamental en el análisis espectral puesto que muestra las frecuencuas que están presentes en una señal y cómo estas se distribuyen.

##### • SNR:
[^2^]“In science and engineering, the signal-to-noise ratio (SNR) is a measure that compares the level of a desired signal to the level of background noise”. - Welvaert M, Rosseel Y (2013)
[^2^]: Welvaert M, Rosseel Y (2013) On the Definition of Signal-To-Noise Ratio and Contrast-To-Noise Ratio for fMRI Data. PLoS ONE 8(11): e77089. https://doi.org/10.1371/journal.pone.0077089

El SNR, o mejor conocido por sus siglas en inglés Signal-to-Noise Ratio, o Relación Señal-Ruido, es una medida que se usa en el campo del procesamiento de señales para describir la proporción entre la potencia de la señal útil (lo que se quiere medir o transmitir), y la potencia del ruido, o como la conocemos, las interferencias o distorsiones no deseadas.

# Análisis

#### - librosa: nos permite procesar los datos de los archivos de audio
#### - numpy: hacer operaciones matemáticas
#### - butter: operación de filtro butterworth
####  - Audio y Display: colocar un reproductor de audio, y poder reproducir el sonido

# Instrucciones
*1.Creación del entorno Python:*
- Utilizando las librerias enunciadas en la introducción se inicializa el entorno.
- Se establecen los distintos parametros que se utilizará para la extracción de audio
- Se crean las variables para el filtrado, agregar SNR, y utilizar la transformada de Fourier.
  
*2. Extracción de datos:*
- Apartir de los audios grabados en los dos microfonos, se obtienen los dialogos y ruido blanco con el que se calculara el SNR.
- Se se seleccionan los archivos de audio desde el escritorio y se suben a Colab.


*3. Proceso de análisis:*
-La señales obtenidas de los audios se procesan en Colab
-Todo el análisis se realiza mediante código, lo que permitió evaluar los datos de manera precisa.

# Requisitos
- Contar con Python 3.9.0 instalado  y utilizar Google Colab (o cualquier compilador compatible)..
- Contar con señal internet.
- Instalar las librerías necesarias instaladas para ejecutar el código correctamente.
- Contar con conocimiento sobre programacion en Python y compilador Colab de google.
  
# Usar
Por favor, cite este articulo de la siguiente manera:

Aux, M.; Martinez, M.;  LABORATORIO 1. Análisis estadístico de la señal. 6 de febrero de 2025.

# Información de contacto

est.manuela.martin@unimilitar.edu.co y est.midalys.aux@unimilitar.edu.co
