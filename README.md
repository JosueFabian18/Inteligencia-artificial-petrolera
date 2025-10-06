# Inteligencia-artificial-petrolera
Este es un repositorio enfocado en crear herramientas de inteligencia artificial con una aplicación en la ingeniera petrolera y su industria 

# Neurona artificial 
El código define una Neurona Artificial básica, que es el componente fundamental de las Redes Neuronales Artificiales. Funciona imitando, muy simplificadamente, la forma en que una neurona biológica procesa la información.
Aquí está el desglose de sus partes:
1. Librería Importada
import numpy as np: Se importa la librería NumPy, que es esencial en Python para el cálculo numérico eficiente. Se usa para manejar los arreglos y realizar operaciones matemáticas vectoriales, como la multiplicación de matrices (o el producto punto, np.dot).
2. La Clase ArtificialNeuron
Esta clase define la estructura y el comportamiento de la neurona.
__init__(self, n_inputs, activation= 'logistic'): Este es el constructor.
n_inputs: Especifica cuántas entradas o señales recibirá la neurona.
self.weights: Es un arreglo de números aleatorios (np.random.randn(n_inputs)) del tamaño de n_inputs. Cada entrada se multiplica por un peso para determinar su importancia.
self.bias: Es un número aleatorio único (np.random.randn()) que se suma al resultado de la suma ponderada. Permite a la neurona ajustar la función de activación, haciendo que se active incluso si todas las entradas son cero.
self.activation: Define la función de activación que se aplicará. Por defecto es la Logística (o Sigmoide).
__call__(self, x): Este método permite que el objeto neurona sea llamado como una función (de ahí el neuron(x) en el ejemplo). Es la parte que realiza el cálculo central.
Cálculo de la Suma Ponderada (z):
z = (x \cdot \mathbf{w}) + b
z = np.dot(x, self.weights) + self.bias: Se calcula el producto punto entre el vector de entrada x y el vector de pesos (self.weights), y luego se le suma el sesgo (self.bias).
Función de Activación: Aplica una función no lineal al resultado z. Esto es clave para que la red neuronal pueda aprender relaciones complejas.
logistic (Sigmoide): f(z) = \frac{1}{1 + e^{-z}} La salida se comprime entre 0 y 1. Se usa comúnmente en problemas de clasificación (probabilidades).
relu (Rectified Linear Unit): f(z) = \max(0, z) La salida es z si es positiva, y 0 si es negativa. Es muy popular en redes neuronales profundas.
else (Lineal): f(z) = z Simplemente devuelve el valor z.
3. Ejemplo de Uso
Se crea una neurona que espera 3 entradas (n_inputs=3).
Se define un vector de entrada x.
Se calcula la salida y aplicando la entrada a la neurona (neuron(x)).
Aplicación en la Industria Petrolera
Una neurona artificial, aunque sea la unidad más simple, es la base de modelos de Aprendizaje Profundo (Deep Learning) que tienen múltiples aplicaciones en la industria petrolera (Oil & Gas).
Ejemplos:
1. Predicción de Propiedades de Yacimientos (Clasificación/Regresión)
El Problema
Los geólogos e ingenieros necesitan estimar propiedades del yacimiento, como la permeabilidad, la porosidad o la saturación de fluidos, a partir de los datos registrados por herramientas de pozo (registros de logging).
​2. Detección de Fallas en Equipos (Clasificación)
​El Problema
​Prevenir fallas costosas en equipos críticos como bombas sumergibles eléctricas (BSE) o válvulas de seguridad en plataformas.
​Aplicación
​Una neurona se puede usar para clasificar el estado operativo como "Normal" o "Alerta de Falla" (un problema de clasificación binaria).
Función de Activación: Se usaría la función Logística para obtener una probabilidad de falla (un valor entre 0 y 1).
Ventaja: Permite implementar un sistema de mantenimiento predictivo que alerta a los operadores antes de que ocurra una avería, ahorrando tiempo y dinero.
