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
Para la elaboración del codigo hay que conocer cada una de las librerias que van a ser requeridas para que el programa se ejecute correctamente:
 
#### - librosa: nos permite procesar los datos de los archivos de audio
#### - numpy: hacer operaciones matemáticas
#### - butter: operación de filtro butterworth
#### - Audio y Display: colocar un reproductor de audio, y poder reproducir el sonido

Para poner los audios que se necesiten procesar sin que el código se tenga que modificar a gran medida, unicamente se suben al colab por medio de archivos tu audio, y reemplazar el nombre que tenga tu audio en "audio_file = 'nombre del audio' ", y así, compilar.

<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/audiosub.png?raw=true" width="40%" />

Posteriormente, se grafica la amplitud en cuanto a las ondas del audio con respecto del tiempo que se capturó al momento de que se realizo "la fiesta del coctel" con las dos personas pertenecientes a esta entrega de laboratorio, esto se realizo con los dos microfonos y observar el como se comporta el sonido:

<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/1.png?raw=true" width="40%" />
<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/2.png?raw=true" width="40%" />

Se graficó despues, utilizando la transformada de Forourier mostrando la incidencia de frecuencias y su intensidad esto ayuda a pasar la primera gráfica que está en el dominio del tiempo al de la frecuencia, se puede ver en una escala de menor a mayor las magnitudes de estas.

<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/1audio.png?raw=true" width="40%" />
<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/2audi.png?raw=true" width="40%" />

Aquí tenemos dos formas de hacer el filtrado de la señal, a través de ayuda de librerías y con transformada de fourier a secas. En este método es donde más parámetros se pueden configurar, la frecuencia de nyquist, que se define como la mitad de la frecuencia de muestreo, el orden del filtro, los parámetros de frecuencias del filtro, y ya estaría para realizar el filtrado.

<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/audiosconfltro.png?raw=true" width="40%" />

Como último realizamos la ecuación de SNR para comprobar la legibilidad del audio grabado con respecto al ruido ambiente captado, dando un data positivo y alto, en caso de ser cercano a cero o negativo se recomienda regrabar los audio o realizar las tomas en un lugar más silencioso, ya que la calidad del audio seria de muy mala calidad, los Display(Audio() que nos sirvieron para poder generar un ventana la cual reproducir los audios filtrados como los que no.

<img src="https://github.com/Mida2304/LABORATORIO3/blob/main/snr.png?raw=true" width="40%" />


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
