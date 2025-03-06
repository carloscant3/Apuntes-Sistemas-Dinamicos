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
  a_1 \frac{d^2 F}{da} + a_2 \frac{dF}{da} + a_3 F = u(a)
  $$

  
  ![image](https://github.com/user-attachments/assets/54057239-3757-426a-b4f3-2e6480e5c151)

  # Transformada de LaPlace
  La transformada de Laplace es una herramienta matemática que se utiliza para analizar sistemas dinámicos, resolver ecuaciones diferenciales y modelar fenómenos en ingeniería y física. Esta transformada convierte señales del dominio del tiempo a una forma más fácil de analizar, lo que ayuda a identificar componentes clave como las exponenciales y las ondas sinusoidales. Estas componentes son esenciales para entender el comportamiento de una señal o sistema en diferentes situaciones.
  Se define como una integral  de la siguiente manera:


  $$
  \mathcal{L} \{ f(t) \} = F(s) = \int_{0}^{\infty} e^{-st} f(t) \, dt
  $$

  
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

$$
\frac{s+5}{(s+1)(s+3)}
$$

Descomponemos en fracciones parciales: 

$$
\frac{s+5}{(s+1)(s+3)} = \frac{A}{s+1} + \frac{B}{s+3}
$$

Luego multiplicamos por ambos lados:

$$
s + 5 = A(s + 3) + B(s + 1)
$$

Para encontrar A, decimos que s = -1

$$
-1 + 5 = A(-1 + 3) + B(-1 + 1)
$$

$$
4 = 2A
$$

$$
A = 2
$$

Para encontrar B, decimos que s = -3

$$
-3 + 5 = A(-3 + 3) + B(-3 + 1)
$$

$$
2 = -2B
$$

$$
B = -1
$$

Al remplazar en las fracciones parciales decimos que, 

$$
F(s) = \frac{2}{s+1} - \frac{1}{s+3}
$$

Teniendo en cuenta lo anteriormente mencionado podemos encontrar la transformada inversa de cada termino:

Según la tabla de transformadas inversas de Laplace 

$$
\frac{2}{s+1} \quad \text{es} \quad 2e^{-t}
$$


Por ende la transformada inversa de 

$$
\frac{2}{s+1} \quad \text{es} \quad 2e^{-t}
$$

y, la transformada inversa de  

$$
\frac{1}{s+3}
$$  
es  
$$
e^{-3t}
$$

Por lo tanto el resultado final o la transformada inversa es:

$$
f(t) = 2e^{-t} - e^{-3t}
$$

  # Caso 2: Raíces reales iguales
  
  # Ejemplo:
  
$$
F(s) = \frac{s + 3}{(s + 1)(s + 2)^2}
$$

La descomposición en fracciones parciales es de la forma:

$$
\frac{s + 3}{(s + 1)(s + 2)^2} = \frac{A}{s + 1} + \frac{B}{s + 2} + \frac{C}{(s + 2)^2}
$$


# 21/feb/2025

# Caso 3: Raíces complejas conjugadas


















  


   
  



   
