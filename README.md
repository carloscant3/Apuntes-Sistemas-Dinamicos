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
  



  # Transformada inversa de Laplace

  Ejemplo:

  ![image](https://github.com/user-attachments/assets/17b0d6c9-6015-44c3-805a-382422a8164c)

  Descomposición en Fracciones Parciales*
  Descomponemos \(F(s)\) en fracciones parciales para obtener términos más simples.  La forma general de la descomposición es:

  ![image](https://github.com/user-attachments/assets/0505596d-ff46-4c63-a67c-58f9002c6d6f)

  Donde A, B y C son constantes que debemos determinar.

  Para encontrar A, B y C, multiplicamos ambos lados de la ecuación por 

  ![image](https://github.com/user-attachments/assets/c7cfffcc-8d79-4742-9a98-721474939615)  y resolvemos el sistema de ecuaciones resultante.  Por ejemplo, haciendo
  s = 0 encontramos B; haciendo s = -2 Encontramos C y finalmente igualando coeficientes de s encontramos A.

  Una vez que hemos encontrado A, B y C (A=3/4, B=1/2 y C=-3/4), podemos aplicar la transformada inversa de Laplace a cada término por separado.  
  Recordemos que: 

  ![image](https://github.com/user-attachments/assets/18e0b9a1-1177-4930-af3d-5a09bfce3b7d)

  Aplicando la transformada inversa a cada término en la descomposición en fracciones parciales:
  ![image](https://github.com/user-attachments/assets/1d6d0994-6e21-45ea-9781-8c5c63e942a4)

  La transformada inversa es: 

  ![image](https://github.com/user-attachments/assets/69a287c5-59cf-4d9f-851e-0d136cfde8c3)



  


   
  



   
