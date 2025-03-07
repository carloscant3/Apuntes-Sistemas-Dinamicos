# Apuntes sistemas dinamicos
**José Manuel Ortiz Soler - 121769**/
**Nicolas Cortes Triana - 120883**/
**Carlos Andrés Cante Saavedra - 122248**
 
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


  # Transformada de LaPlace
  La transformada de Laplace es una herramienta matemática que se utiliza para analizar sistemas dinámicos, resolver ecuaciones diferenciales y modelar fenómenos en ingeniería y física. Esta transformada convierte señales del dominio del tiempo a una forma más fácil de analizar, lo que ayuda a identificar componentes clave como las exponenciales y las ondas sinusoidales. Estas componentes son esenciales para entender el comportamiento de una señal o sistema en diferentes situaciones.
  Se define como una integral  de la siguiente manera:


  $$
  \mathcal{L} \{ f(t) \} = F(s) = \int_{0}^{\infty} e^{-st} f(t) \, dt
  $$


**Ejemplo : Queremos calcular la transformada de laplace de la siguiente función:**

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


- Entonces el resultado final quedaria de la siguiente forma:

$$
( F(s) = \frac{1}{s-3}, \quad \text{para\ } s > 3 \)
$$



# 10/feb/2025

  # Transformada inversa de Laplace

 # Ejemplo 1
  
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

# Ejemplo 2:

**Encuentra la transformada inversa de Laplace de:**

$$
F(s) = \frac{2s + 7}{s^2 + 6s + 13}
$$

### Factorizamos el denominador**
El denominador es:

$$
s^2 + 6s + 13
$$

Completamos el cuadrado:

$$
s^2 + 6s + 9 + 4 = (s+3)^2 + 4
$$

Por lo tanto:

$$
s^2 + 6s + 13 = (s+3)^2 + 2^2
$$


### **Separamos el numerador para operar**
El numerador es \( 2s + 7 \). Lo reescribimos en términos de \( (s+3) \):

$$
2s + 7 = 2(s+3) + 1
$$

Reescribimos \( F(s) \):

$$
F(s) = \frac{2(s+3) + 1}{(s+3)^2 + 2^2}
$$

Separamos en dos fracciones:

$$
F(s) = \frac{2(s+3)}{(s+3)^2 + 2^2} + \frac{1}{(s+3)^2 + 2^2}
$$

### **Aplicamos las transformadas inversas**
Sabemos que:

$$
\mathcal{L}^{-1} \left( \frac{s-a}{(s-a)^2 + b^2} \right) = e^{at} \cos(bt)
$$

$$
\mathcal{L}^{-1} \left( \frac{b}{(s-a)^2 + b^2} \right) = e^{at} \sin(bt)
$$

Comparando con nuestras fracciones:

- Para la primera fracción, \( a = -3 \), \( b = 2 \), y el numerador tiene un \( 2 \), por lo que corresponde a \( e^{-3t} \cos(2t) \).
- Para la segunda fracción, necesitamos un \( 2 \) en el numerador, así que multiplicamos y dividimos por \( 2 \):

$$
\frac{1}{(s+3)^2 + 2^2} = \frac{1}{2} \cdot \frac{2}{(s+3)^2 + 2^2}
$$

Esto corresponde a \( \frac{1}{2} e^{-3t} \sin(2t) \).

### **Solución final**

$$
f(t) = 2e^{-3t} \cos(2t) + \frac{1}{2} e^{-3t} \sin(2t)
$$









# 14/feb/2025

  # Transformada inversa de Laplace

# Ejemplo 2


$$
F(s) = \frac{3s + 5}{s^2 + 4s + 13}
$$


Factorizamos el denominador


$$
s = \frac{-4 \pm \sqrt{16 - 52}}{2} = \frac{-4 \pm \sqrt{-36}}{2} = \frac{-4 \pm 6i}{2} = -2 \pm 3i
$$

Completar el cuadrado en el denominador

$$
\begin{align*}
s^2 + 4s + 13 = (s^2 + 4s + 4) + 9 = (s + 2)^2 + 9
\end{align*}
$$

Ahora expresamo a F(s)


$$
F(s) = \frac{3s + 5}{(s + 2)^2 + 9}
$$


Separamos en dos terminos:


$$
F(s) = \frac{3(s+2)}{(s+2)^2+9} - \frac{1}{(s+2)^2+9}
$$


Para el primer termino: 

$$
\frac{3(s+2)}{(s+2)^2+9}
$$


$$
\begin{align*}
\mathcal{L}^{-1} \left( \frac{3(s+2)}{(s+2)^2+9} \right) = 3 e^{-2t} \cos(3t)
\end{align*}
$$

Para el segundo termino:

$$
\frac{1}{(s+2)^2+9}
$$


$$
\begin{align*}
{\cal L}^{-1} \left( \frac{1}{(s+2)^2+9} \right) = \frac{1}{3} e^{-2t} \sin(3t)
\end{align*}
$$


Sumamos las transformadas inversas de cada término:


$$
f(t) = e^{-2t} \left( 3 \cos(3t) - \frac{1}{3} \sin(3t) \right)
$$


# 17/feb/2025

# Transformada inversa (Método resumido)
Cuando se hace la división en fracciones parciales, hay que factorizar las raíces del polinomio de arriba. Esto ayuda a ver qué valores de S
hacen que algunos términos desaparezcan, lo que simplifica el sistema de ecuaciones que hay que resolver.

  # Caso 1: Raíces reales diferentes
  
Las raíces reales diferentes son simplemente los valores de una ecuación en los que la función toca o cruza el eje y la incognita y que no se repita.

![image](https://github.com/user-attachments/assets/342f9510-d63b-4b5e-bc95-304f22a33564)

# Ejemplo 1: 

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



# Ejemplo 2

$$
\frac{s + 7}{(s + 2)(s + 4)}
$$

Multiplicamos por ambos lados:

$$
\frac{s + 7}{(s + 2)(s + 4)} = \frac{A}{s + 2} + \frac{B}{s + 4}
$$

Multiplicamos por \((s + 2)(s + 4)\):

$$
s + 7 = A(s + 4) + B(s + 2)
$$

Para encontrar \( A \), hacemos \( s = -2 \):

$$
-2 + 7 = A(-2 + 4) + B(0)
$$

$$
5 = 2A
$$

$$
A = \frac{5}{2}
$$

Para encontrar \( B \), hacemos \( s = -4 \):

$$
-4 + 7 = A(0) + B(-4 + 2)
$$

$$
3 = -2B
$$

$$
B = -\frac{3}{2}
$$

Sustituyendo en la fracción original:

$$
F(s) = \frac{5}{2} \frac{1}{s + 2} - \frac{3}{2} \frac{1}{s + 4}
$$

Aplicando la transformada inversa de Laplace:

La transformada inversa de  

$$
\frac{5}{2} \cdot \frac{1}{s + 2}
$$

es:

$$
\frac{5}{2} e^{-2t}
$$

Y la transformada inversa de  

$$
\frac{3}{2} \cdot \frac{1}{s + 4}
$$

es:  

$$
\frac{3}{2} e^{-4t}
$$

Por lo tanto, el resultado final o la transformada inversa es:  

$$
f(t) = \frac{5}{2} e^{-2t} - \frac{3}{2} e^{-4t}
$$

  # Caso 2: Raíces reales iguales
  
  # Ejemplo 1
  
$$
F(s) = \frac{s + 3}{(s + 1)(s + 2)^2}
$$

La descomposición en fracciones parciales es de la forma:

$$
\frac{s + 3}{(s + 1)(s + 2)^2} = \frac{A}{s + 1} + \frac{B}{s + 2} + \frac{C}{(s + 2)^2}
$$

Para encontrar \( A \), multiplicamos ambos lados por \((s+1)\) y evaluamos en \( s=-1 \):

$$
A = \frac{s+3}{(s+2)^2} \bigg|_{s=-1}
$$

Sustituimos \( s=-1 \):

$$
A = \frac{-1+3}{(-1+2)^2} = \frac{2}{1} = 2
$$

Coeficiente \( C \) (polo repetido en \( s = -2 \)):

Para encontrar \( C \), multiplicamos ambos lados por \( (s + 2)^2 \) y evaluamos en \( s = -2 \):

$$
C = \left. \frac{s + 3}{s + 1} \right|_{s=-2}
$$

Sustituimos \( s = -2 \):

$$
C = \left. \frac{-2 + 3}{-2 + 1} \right|_{s=-2} = \frac{1}{-1}
$$

**Coeficiente \( B \) ( repetido en \( s = -2 \)):**

Para encontrar \( B \), multiplicamos ambos lados por \( (s + 2)^2 \), derivamos con respecto a \( s \), y luego evaluamos en \( s = -2 \):

1. Multiplicamos por \( (s + 2)^2 \):

$$
\frac{s + 3}{s + 1} = A(s + 2)^2 \cdot \frac{1}{s + 1} + B(s + 2) + C
$$

2. Derivamos ambos lados con respecto a \( s \):

$$
\begin{align*}
\frac{d}{ds} \left( \frac{s+3}{s+1} \right) = \frac{d}{ds} \left( A(s+2)^2 \cdot \frac{1}{s+1} + B(s+2) + C \right)
\end{align*}
$$

3. Simplificamos la derivada del lado izquierdo:

$$
\frac{(1)(s+1)-(s+3)(1)}{(s+1)^2} = \frac{s+1-s-3}{(s+1)^2} = \frac{-2}{(s+1)^2}
$$

4. Derivada del lado derecho:

$$
\frac{d}{ds} \left( A(s+2)^2 \cdot \frac{1}{s+1} \right) + \frac{d}{ds} \left( B(s+2) \right) + \frac{d}{ds} \left( C \right)
$$

- El término \( C \) es una constante, su derivada es 0.
- El término ![image](https://github.com/user-attachments/assets/7f8f10f9-ce99-477d-8421-94bf6bf1b391)


  tiene derivada (B).
- El término ![image](https://github.com/user-attachments/assets/1677babf-e74a-446c-bec2-a603ee70a068) se deriva usando la regla del producto, pero no es necesario calcularlo porque solo nos interesa evaluar en ![image](https://github.com/user-attachments/assets/d398bf49-2488-4b68-873d-327a00606990).

  

5. Evaluamos en \( s = -2 \):

$$
\frac{-2}{(-2 + 1)^2} = B
$$

$$
\frac{-2}{1} = B \implies B = -2
$$

Sustituimos los valores de \( A, B \) y \( C \):

$$
F(s) = \frac{2}{s+1} - \frac{2}{s+2} - \frac{1}{(s+2)^2}
$$


$$
Para \(\frac{2}{s+1}\):
$$


$$
\begin{align*}
\mathcal{L}^{-1} \{ \frac{2}{s+1} \} = 2e^{-t}
\end{align*}
$$


$$
Para \(\frac{-2}{s+2}\):
$$


$$
{\cal L}^{-1} \left( \frac{-2}{s+2} \right) = -2e^{-2t}
$$



$$
Para \(\frac{-1}{(s+2)^2}\):
$$


$$
{\cal L}^{-1} \left( \frac{-1}{(s+2)^2} \right) = -t e^{-2t}
$$




Sumamos las transformadas inversas de cada término:


$$
f(t) = 2e^{-t} - 2e^{-2t} - te^{-2t}
$$



# Ejemplo 2

**Dada la función:** 

$$
F(s) = \frac{5s + 4}{(s+2)^2}
$$

**Descomposición en fracciones parciales:**
Se busca expresar \( F(s) \) en la forma:

$$
\frac{5s + 4}{(s+2)^2} = \frac{A}{s+2} + \frac{B}{(s+2)^2}
$$

**Multiplicamos ambos lados por \( (s+2)^2 \) y resolvemos para \( A \) y \( B \):**

$$
5s + 4 = A(s+2) + B
$$

**Sustituyendo \( s = -2 \) para encontrar \( B \):**

$$
5(-2) + 4 = A(0) + B
$$

$$
-10 + 4 = B
$$

$$
B = -6
$$

**Para encontrar \( A \), derivamos ambos lados y evaluamos en \( s = -2 \):**

Derivamos:

$$
5 = A
$$

Entonces \( A = 5 \).

**Sustituyendo los valores en la fracción parcial:**

$$
F(s) = \frac{5}{s+2} - \frac{6}{(s+2)^2}
$$

**Aplicamos la transformada inversa de Laplace:**

Usando la tabla de transformadas inversas:

$$
\mathcal{L}^{-1} \left( \frac{5}{s+2} \right) = 5 e^{-2t}
$$

$$
\mathcal{L}^{-1} \left( \frac{6}{(s+2)^2} \right) = 6t e^{-2t}
$$

**Resultado final:**  

$$
f(t) = 5e^{-2t} - 6t e^{-2t}
$$


# 21/feb/2025

# Caso 3: Raíces complejas conjugadas



# Ejemplo 1



$$
F(s) = \frac{s + 1}{s^2 + 4s + 13}
$$

Factorizar el denominador

$$
s = \frac{-4 \pm \sqrt{16 - 52}}{2} = \frac{-4 \pm \sqrt{-36}}{2} = \frac{-4 \pm 6i}{2} = -2 \pm 3i
$$

Expresar F (s) en terminos de las raices complejas

$$
F(s) = \frac{s + 1}{(s + 2 - 3i)(s + 2 + 3i)}
$$

Completamos el cuadrado en el denominador

$$
s^2 + 4s + 13 = (s^2 + 4s + 4) + 9 = (s + 2)^2 + 9
$$

Reescribimos F(s)

$$
F(s) = \frac{s+1}{(s+2)^2+9}
$$

Para que el numerador coincida con la forma estándar de la transformada inversa de Laplace, lo reescribimos como:

$$
F(s) = \frac{(s+2)-1}{(s+2)^2+9}
$$

Separamos en dos términos:

$$
F(s) = \frac{s + 2}{(s + 2)^2 + 9} - \frac{1}{(s + 2)^2 + 9}
$$

Ahora aplicamos la transformada inversa a cada término

Para el primer termino: 

$$
\frac{s+2}{(s+2)^2+9}
$$


$$
\mathcal{L}^{-1} \left( \frac{s+2}{(s+2)^2 + 9} \right) = e^{-2t} \cos(3t)
$$


Para el segundo término:

$$
\frac{1}{(s+2)^2+9}
$$

$$
{\cal L}^{-1} \left( \frac{1}{(s+2)^2+9} \right) = \frac{1}{3} e^{-2t} \sin(3t)
$$


Sumamos las transformadas inversas de cada término:

$$
f(t) = e^{-2t} \cos(3t) - \frac{1}{3} e^{-2t} \sin(3t)
$$


# Ejemplo 2

**Encuentra la transformada inversa de Laplace de:**

$$
F(s) = \frac{s + 5}{s^2 + 2s + 10}
$$

**Factorizamos el denominador**
La ecuación cuadrática en el denominador es:

$$
s^2 + 2s + 10
$$

Completamos el cuadrado:

$$
s^2 + 2s + 1 + 9 = (s+1)^2 + 9
$$

Por lo tanto:

$$
s^2 + 2s + 10 = (s+1)^2 + 3^2
$$

**Tenemos que encontrar las raíces del denominador**

Resolvemos la ecuación cuadrática:

$$
s^2 + 2s + 10 = 0
$$

Usamos la fórmula general:

$$
s = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

Sustituyamos los valores \( a = 1 \), \( b = 2 \), \( c = 10 \):

$$
s = \frac{-2 \pm \sqrt{2^2 - 4(1)(10)}}{2(1)}
$$

$$
s = \frac{-2 \pm \sqrt{4 - 40}}{2}
$$

$$
s = \frac{-2 \pm \sqrt{-36}}{2}
$$

$$
s = \frac{-2 \pm 6i}{2}
$$

$$
s = -1 \pm 3i
$$

Las raíces del denominador son \( s = -1 + 3i \) y \( s = -1 - 3i \), que son **conjugadas complejas**.

---

### **Expresar la fracción en términos de una forma reconocida**
Descomponemos el numerador:

$$
s + 5 = (s+1) + 4
$$

Reescribimos \( F(s) \):

$$
F(s) = \frac{(s+1) + 4}{(s+1)^2 + 9}
$$

Separamos en dos fracciones:

$$
F(s) = \frac{s+1}{(s+1)^2 + 9} + \frac{4}{(s+1)^2 + 9}
$$

### **Identificamos las transformadas inversas**
De la tabla de transformadas de Laplace, sabemos que:

$$
\mathcal{L}^{-1} \left( \frac{s-a}{(s-a)^2 + b^2} \right) = e^{at} \cos(bt)
$$

$$
\mathcal{L}^{-1} \left( \frac{b}{(s-a)^2 + b^2} \right) = e^{at} \sin(bt)
$$

Comparando con nuestras fracciones:

- Para la primera fracción, \( a = -1 \), \( b = 3 \).
- Para la segunda fracción, necesitamos un \( 3 \) en el numerador, así que factorizamos:

$$
\frac{4}{(s+1)^2 + 9} = \frac{4}{3} \cdot \frac{3}{(s+1)^2 + 9}
$$

Aplicamos las transformadas inversas:

$$
\mathcal{L}^{-1} \left( \frac{s+1}{(s+1)^2 + 9} \right) = e^{-t} \cos(3t)
$$

$$
\mathcal{L}^{-1} \left( \frac{3}{(s+1)^2 + 9} \right) = e^{-t} \sin(3t)
$$

Multiplicamos la segunda ecuación por \( \frac{4}{3} \):

$$
\mathcal{L}^{-1} \left( \frac{4}{(s+1)^2 + 9} \right) = \frac{4}{3} e^{-t} \sin(3t)
$$

### **Solución final**
Sumando los términos:

$$
f(t) = e^{-t} \cos(3t) + \frac{4}{3} e^{-t} \sin(3t)
$$

### **Conclusión**
Hemos encontrado la transformada inversa de Laplace:

$$
F(s) = \frac{s + 5}{s^2 + 2s + 10} \quad \longrightarrow \quad f(t) = e^{-t} \cos(3t) + \frac{4}{3} e^{-t} \sin(3t)
$$








  


   
  



   
