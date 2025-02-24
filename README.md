# Apuntes-Sistemas-Dinamicos

  # Sistema
  Un sistema es una combinación de componentes que actúan conjuntamente para alcanzar un objetivo específico. La combinación de componentes se puede representar por medio de reglas      
  principios que relacionan salidas con las entradas.

  # Sistema dinámico
  • Un sistema se llama dinámico si su salida en el presente
  depende de una entrada en el pasado
  • Si su salida en curso depende solamente de la entrada en
  curso, el sistema se conoce como estático.

  # Como lucen los modelos de ecuaciones diferenciales…
  Son combinaciones lineales de derivadas de diferente orden:
  
  ![image](https://github.com/user-attachments/assets/54057239-3757-426a-b4f3-2e6480e5c151)

  # Transformada de LaPlace
  La Transformada de Laplace es una herramienta matemática que se utiliza para analizar sistemas dinámicos, resolver ecuaciones diferenciales y modelar fenómenos en ingeniería y física.    Se define como una integral impropia de la siguiente manera:
   ![image](https://github.com/user-attachments/assets/7f33218d-6722-438f-87a7-32ee78d290fd)

  Ejemplo: 
  
$f(t) = e^{-at}$*


Vamos a calcular la transformada de Laplace de la función exponencial $f(t) = e^{-at}$:

$\mathcal{L}\{e^{-at}\} = \int_0^{\infty} e^{-st} e^{-at} dt = \int_0^{\infty} e^{-(s+a)t} dt$

Resolviendo la integral:

$= \left[ -\frac{1}{s+a} e^{-(s+a)t} \right]_0^{\infty} = \frac{1}{s+a}$


  # Transformada inversa de Laplace
  
   
  



   
