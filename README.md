# Apuntes-Sistemas-Dinamicos

 
# 7/feb/2025


  # Sistema
  Un sistema es una combinación de componentes que actúan conjuntamente para alcanzar un objetivo específico. La combinación de componentes se puede representar por medio de reglas      
  principios que relacionan salidas con las entradas.

  # Sistema dinámico
  • Un sistema se llama dinámico si su salida en el presente                                     
  depende de una entrada en el pasado
  
  • Si su salida en curso depende solamente de la entrada en
  curso, el sistema se conoce como estático.                                                ![image](https://github.com/user-attachments/assets/39d28d0a-cb47-4d66-8025-0e9be5be53bf)


  # Como lucen los modelos de ecuaciones diferenciales…
  Son combinaciones lineales de derivadas de diferente orden:


  $$
  a_1 \frac{d^2 F}{dt^2} + a_2 \frac{dF}{dt} + a_3 F = u(t)
  $$

  
  ![image](https://github.com/user-attachments/assets/54057239-3757-426a-b4f3-2e6480e5c151)

  # Transformada de LaPlace
  La transformada de Laplace es una herramienta matemática que se utiliza para analizar sistemas dinámicos, resolver ecuaciones diferenciales y modelar fenómenos en ingeniería y física. Esta transformada convierte señales del dominio del tiempo a una forma más fácil de analizar, lo que ayuda a identificar componentes clave como las exponenciales y las ondas sinusoidales. Estas componentes son esenciales para entender el comportamiento de una señal o sistema en diferentes situaciones.
  Se define como una integral  de la siguiente manera:
   ![image](https://github.com/user-attachments/assets/7f33218d-6722-438f-87a7-32ee78d290fd)

Ejemplo : Queremos calcular la transformada de laplace de la siguiente función:

$$
( f(t) = e^{3t} \)
$$


  - Aplicamos la definición:

$$
( F(s) = \int_{0}^{\infty} e^{-st} e^{3t} dt \)
$$


- Simplificamos el exponente:

$$
( F(s) = \int_{0}^{\infty} e^{(3-s)t} dt \)
$$


- Calculamos la integral:

$$
( F(s) = \left[ \frac{e^{(3-s)t}}{3-s} \right]_{0}^{\infty} \)
$$



- Evaluamos los limites:


$$
Cuando \( t \to \infty \), si \( s > 3 \), el término \( e^{(3-s)t} \to 0 \)
$$

$$
Cuando \( t = 0 \), el término es \( \frac{1}{s-3} \) para \( s > 3 \)
$$


![image](https://github.com/user-attachments/assets/1996cdbc-f7d6-4561-9ad9-3d33b8146c9b)


- Entonces el resultado final quedaria de la siguiente forma:

$$
( F(s) = \frac{1}{s-3}, \quad \text{para\ } s > 3 \)
$$



# 10/feb/2025

  # Transformada inversa de Laplace

  Ejemplo:
  
  $$
\frac{s+1}{s^2(s+2)}
$$


  Descomposición en Fracciones Parciales*
  Descomponemos \(F(s)\) en fracciones parciales para obtener términos más simples.  La forma general de la descomposición es:

$$
\frac{s+1}{s^2(s+2)} = \frac{A}{s} + \frac{B}{s^2} + \frac{c}{s+2}
$$

  Donde A, B y C son constantes que debemos determinar.

  Para encontrar A, B y C, multiplicamos ambos lados de la ecuación por
  
  $$
  \{s^2(s+2)}
  $$
  
  y resolvemos el sistema de ecuaciones resultante.  Por ejemplo, haciendo
  s = 0 encontramos B; haciendo s = -2 Encontramos C y finalmente igualando coeficientes de s encontramos A.

  Una vez que hemos encontrado A, B y C 
  
  $$
  \frac{s+1}{s^2(s+2)} = \frac{3}{4s} + \frac{1}{2s^2} + \frac{-3}{4(s+2)}
  $$
  
, podemos aplicar la transformada inversa de Laplace a cada término por separado.  
  Recordemos que: 
  
  $$
  \mathcal{L}^{-1} \frac{1}{s} = 1 \mathcal{L}^{-1} \frac{1}{s^2} = t \mathcal{L}^{-1} \frac{1}{s + a} = e^{-at}
  $$

  Aplicando la transformada inversa a cada término en la descomposición en fracciones parciales:


  $$
f(t) = \mathcal{L}^{-1} \{ F(s) \} = \mathcal{L}^{-1} \left( \frac{3}{4s} + \frac{1}{2s^2} - \frac{3}{4(s+2)} \right) = \frac{3}{4} + \frac{1}{2}t - \frac{3}{4}e^{-2t}
$$




  La transformada inversa es: 


  $$
F(s) = \frac{s+1}{s^2(s+2)} \quad \mathbf{es}
$$

$$
f(t) = \frac{3}{4} + \frac{1}{2}t - \frac{3}{4}e^{-2t}
$$


# 14/feb/2025

  # Transformada inversa de Laplace



# 17/feb/2025

# Transformada inversa (Método resumido)
Cuando se hace la división en fracciones parciales, hay que factorizar las raíces del polinomio de arriba. Esto ayuda a ver qué valores de S
hacen que algunos términos desaparezcan, lo que simplifica el sistema de ecuaciones que hay que resolver.

  # Caso 1: Raíces reales diferentes
  
Las raíces reales diferentes son simplemente los valores de una ecuación en los que la función toca o cruza el eje y la incognita y que no se repita.

![image](https://github.com/user-attachments/assets/342f9510-d63b-4b5e-bc95-304f22a33564)

# Ejemplo: 

![image](https://github.com/user-attachments/assets/90e0435b-413c-44c1-8664-1dc27f487eb8)

Descomponemos en fracciones parciales: 

![image](https://github.com/user-attachments/assets/57de157e-d312-4d86-9a84-9520ea94e142)

Luego multiplicamos por ambos lados:

![image](https://github.com/user-attachments/assets/f2af4794-295f-4885-95a8-0191ea22a0c0)

Para encontrar A, decimos que s = -1

![image](https://github.com/user-attachments/assets/5950387f-2869-4338-91c1-7c2b8672f40b)

Para encontrar B, decimos que s = -3

![image](https://github.com/user-attachments/assets/d9d0d55c-424b-4da5-8c15-ca57478a34f8)

Al remplazar en las fracciones parciales decimos que, 

![image](https://github.com/user-attachments/assets/a11d46c6-f42c-4adb-a42d-043df07b2422)

Teniendo en cuenta lo anteriormente mencionado podemos encontrar la transformada inversa de cada termino:

Según la tabla de transformadas inversas de Laplace ![image](https://github.com/user-attachments/assets/c3df4d4e-cfdc-4f32-8873-c993c6e113fc)  es   ![image](https://github.com/user-attachments/assets/c0762ae0-98b9-481a-bcc5-ec7f9d6b2bb1)


Por ende la transformada inversa de ![image](https://github.com/user-attachments/assets/819e490a-d25e-4475-a0f3-27d2d116058e)  es ![image](https://github.com/user-attachments/assets/9f2e6d56-4390-47d0-97ed-72657bff3208).

y, la transformada inversa de ![image](https://github.com/user-attachments/assets/70f6fa13-4e7b-4e6f-b3d8-1b1acf16ff63)
es   ![image](https://github.com/user-attachments/assets/2bddae17-dd00-44e3-952b-f2635d03a58d)

Por lo tanto el resultado final o la transformada inversa es:

![image](https://github.com/user-attachments/assets/b938e787-afe6-4e64-8b7a-6c2e36327a5c)

  # Caso 2: Raíces reales iguales


# 21/feb/2025

# Caso 3: Raíces complejas conjugadas


















  


   
  



   
