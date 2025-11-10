# Intro
Hola a todos, 
Antes de empezar me gustaría darles un poco de contexto.
Soy un estudiante de magister de computer science y esta es mi tercera semana trabajando en incendios forestales, así que mi investigación esta en una fase muy temprana.

Mi plan es optimizar un modelo de computational fluid dynamics y combinar eso con algún dataset para entrenar PINN que es el área que más me llama la atencion.

# Modelo 

- Así que actualmente me encuentro en el primer paso, para lo cual estuve estudiando el modelo del doctor Daniel San Martin, 

- el cual es un modelo de incendios forestales con un domino vertical 2D con interacción atmosfera fuego donde hay una retroalimentación bidireccional entre fuego y atmosfera. 

- ademas se considera un bajo numero de mach, lo cual permite desacoplar presión y densidad. 
- Las equaciones governantes son:
- Conservación de momento que proviene de Navier-Stokes
- Conservación de energia que es la ecuación de temperatura
- Ecuacion de consumo de combustible basada en Arrhenius
- Ecuación de Divergencia de velocidad
- Para la turbulencia se una Large Eddy Simulation para modelar efectos de sub malla
- La radiación se simplifica en el término de difusión.
- La validacion se compara con el experimento CSIRO Case F19 con resultados de FDS.


Bueno y la parte donde entro yo es resolver la ecuación de presión la cual se deriva de la ecuación de momento y divergencia la cual es el principal cuello de botella de la simulación.

Actualmente esto se resuelve con diferencias finitas mezcladas con metodos espectrales, es decir, los gradientes con finitas y el laplaciano con espectrales, lo cual genera un sistema tridiagonal que se resuelve con el algoritmo de Thomas en esta iteración de punto fijo, l cual suena y es costoso computacionalmente.


Así que en estas 2 semanas de trabajo he estado leyendo literatura y probando distintos enfoques.

parti por definir unos campos de Temperatura, Densidad y Pressión los cuales son sinteticos y parti desde la temperatura intentando simular una pluma y agregue ruido y gradientes, luego para la densidad use la relacion densidad es igual a presion sobre consante del gas y temperatura y para la presión la ecuación de hidroestatica así que se integra para obtener la presión.


===


# Intro

Hi everyone. Before I begin, a little context: I am a master's student in Computer Science, and I've been working on wildfires for three weeks now, so my research is still in a very early stage.

My goal is to optimize a Computational Fluid Dynamics (CFD) model and then combine it with data to train Physics-Informed Neural Networks (PINNs), which is my main area of interest.

# Model

I am currently on the first step, studying Dr. Daniel San Martín's model.

- It is a wildfire model in a 2D vertical domain that considers a two-way interaction between fire and atmosphere.
    
- It assumes a low Mach number, which decouples pressure from density.
    
- The governing equations include: momentum conservation (Navier-Stokes), energy conservation (temperature), fuel consumption (Arrhenius), and velocity divergence.
    
- It uses Large Eddy Simulation (LES) for turbulence and simplifies radiation as a diffusion term.
    
- Validation is done by comparing it with the CSIRO Case F19 experiment and FDS results.
    

My work focuses on solving the **pressure equation**, derived from the momentum and divergence equations, which is the current simulation bottleneck. It is currently solved using a hybrid method: finite differences for gradients and spectral methods for the Laplacian. This generates a tridiagonal system solved with the Thomas algorithm within a fixed-point iteration, which is computationally expensive.

Over these past two weeks, I’ve been reviewing literature and testing different approaches. I started by defining synthetic fields for temperature (simulating a plume with noise), density (using the ideal gas law), and pressure (integrating the hydrostatic equation) to create a controlled testbed.