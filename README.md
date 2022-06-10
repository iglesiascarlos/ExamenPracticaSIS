# ExamenPracticaSIS

Carlos iglesias Ferriol

## Paso 1
El primer paso para hacer el despliegue de la aplicación en docker será extraer el .war del proyecto a desplegar en mi caso voy a utilizar el .war del proyecto aportado por maximo en su github, extrayendo el .war del GitHub del proyecto, estos archivos los meteremos en la carpetra de nuestro proyecto y dentro de una carpeta llamada target.

<img width="489" alt="Captura de Pantalla 2022-06-10 a las 16 48 08" src="https://user-images.githubusercontent.com/91618773/173091472-c3c47813-6586-4616-a3eb-5f23d0597f32.png">

## Paso 2
Una vez tenemos el .war lo que haremos es crear los archivos Dockerfile y el archivo docker-compose.yml estos dos archivos son creados dentro de la carpeta que vamos a usar para el proyecto y para el despliegue

<img width="481" alt="Captura de Pantalla 2022-06-10 a las 16 49 48" src="https://user-images.githubusercontent.com/91618773/173091780-8bea7f16-f084-4df3-bf66-8f401dda36de.png">

1. Dockerfile. En este archivo introduciremos las siguientes lienas de código:

<img width="387" alt="Captura de Pantalla 2022-06-10 a las 16 53 36" src="https://user-images.githubusercontent.com/91618773/173092537-037d2df9-3784-4eec-9223-4bf891062ce8.png">


Una vez introducidas las lineas de código respectivas haremos un "Build Image" para construi la imagen

<img width="161" alt="Captura de Pantalla 2022-06-10 a las 16 56 58" src="https://user-images.githubusercontent.com/91618773/173093208-855c8b30-c873-48e3-8000-77f22f91ae6e.png">

Introducimos el nombre que queremos a la imagen

<img width="276" alt="Captura de Pantalla 2022-06-10 a las 16 59 46" src="https://user-images.githubusercontent.com/91618773/173093758-4db710bd-1559-40b4-924c-a493b5c2a316.png">

<img width="468" alt="Captura de Pantalla 2022-06-10 a las 17 01 53" src="https://user-images.githubusercontent.com/91618773/173094180-7c136437-83be-4e57-9f5b-40e0abda4ce0.png">


2. docker-compose. En este otro introduciremos las siguientes lineas de código para que se creen las 3 máquinas dockerizadas donde tenemos que revisar muy bien y lo cual suele dar bastante problemas es que no se pisen los puertos y asignar unos que vyaan a funcionar, en mi casa uso los puertos 3306 para mysql 8081 para phpmyadmin y 8082 para la parte de tomcat. (Hay que tener en cuenta que no tengas por ejemplo XAMPP porque si lo usas para base de datos tambien pisa el puerto 3306 y da error al estar ya usado ese puerto)

<img width="419" alt="Captura de Pantalla 2022-06-10 a las 16 54 56" src="https://user-images.githubusercontent.com/91618773/173092785-84ed4d53-5838-4931-9c68-3610be7fa0dd.png">

Una vez tenemos este archivo lo que haremos es dar click derecho en el visual studio le damos a compose up para hacer el compose de las 3 máquinas, phpmyadmin, mysql, tomcat

<img width="226" alt="Captura de Pantalla 2022-06-10 a las 17 06 12" src="https://user-images.githubusercontent.com/91618773/173095142-ab4a0784-28a8-4da7-bc24-9cde4af3751f.png">

Una vez le damos nos saldrá despues de todo un mensaje parecido a este y será la confirmación de que se ha hecho el compose up bien, también podremos comprobarlo con el docker desktop 

<img width="462" alt="Captura de Pantalla 2022-06-10 a las 17 07 57" src="https://user-images.githubusercontent.com/91618773/173095416-c13cbc46-57b5-420f-aace-54321ea305be.png">

<img width="709" alt="Captura de Pantalla 2022-06-10 a las 17 09 24" src="https://user-images.githubusercontent.com/91618773/173095681-31881c3a-ca37-4417-9472-84c6c333c225.png">

Con este paso de compose up se nos genera la carpeta mysql-dumb

<img width="502" alt="Captura de Pantalla 2022-06-10 a las 18 00 47" src="https://user-images.githubusercontent.com/91618773/173105734-2685f83c-4602-4a02-82d7-da50eb63c870.png">


Una vez hemos hecho esto lo siguiente es ir a la carpeta mysql-dumb y crear el archivo USER.sql con el siguiente código:

<img width="122" alt="Captura de Pantalla 2022-06-10 a las 18 02 20" src="https://user-images.githubusercontent.com/91618773/173105974-f7333d79-b32b-4e3c-ba01-6f70f07b6f17.png">

<img width="425" alt="Captura de Pantalla 2022-06-10 a las 18 02 07" src="https://user-images.githubusercontent.com/91618773/173105943-00800006-b6c6-4574-9643-5e98d7231c3f.png">

Ahora lo siguiente es comprobar que todo se ha desplegado correctamente y para ello comprobamos lo siguiente
1. localhost:8081 (phpmyadmin)
  
  <img width="745" alt="Captura de Pantalla 2022-06-10 a las 18 03 50" src="https://user-images.githubusercontent.com/91618773/173106211-28642961-c273-4f66-af6b-d7d0a8e079d3.png">
  
  En el apartado de phpmyadmin tendremos que realizar un pequeño cambio debido a un fallo del proyecto que estamos usando este será el siguiente:  iremos a "testdb1", luego "USER", "Columnas" y "Nueva". Aquí crearemos una nueva columna llamada "regdit" con un valor/lognitud "20".
  
  <img width="304" alt="Captura de Pantalla 2022-06-10 a las 18 06 27" src="https://user-images.githubusercontent.com/91618773/173106738-7a633533-572b-4c1b-9bc3-473a2461a800.png">

<img width="292" alt="Captura de Pantalla 2022-06-10 a las 18 13 18" src="https://user-images.githubusercontent.com/91618773/173107908-565e2a1b-99be-4d7c-bb26-820eeebe6e3f.png">

Una vez hecho todo esto podemos comprobar que nos podemos registrar en el siguiente enlace:

2. http://localhost:8082/LoginWebApp/
  
  <img width="660" alt="Captura de Pantalla 2022-06-10 a las 18 04 36" src="https://user-images.githubusercontent.com/91618773/173106323-83e7b7fc-627d-49d3-aeea-0db0ecaa8409.png">

Aqui vamos a comprobar que nos podemos registrar:

<img width="430" alt="Captura de Pantalla 2022-06-10 a las 18 14 35" src="https://user-images.githubusercontent.com/91618773/173108142-49285562-d126-464f-bf26-7a8dcd58ac41.png">

<img width="289" alt="Captura de Pantalla 2022-06-10 a las 18 15 14" src="https://user-images.githubusercontent.com/91618773/173108261-3a89aa01-c327-4413-8184-78543b29d7c2.png">

Podemos comprobar que la cuenta se ha creado correctamente consultando la direccioon localhost:8081 (phpmyadmin) y mirando en testdb1 la tabla USERS los usuarios creados que hay:

<img width="371" alt="Captura de Pantalla 2022-06-10 a las 18 16 38" src="https://user-images.githubusercontent.com/91618773/173108480-b529ce7b-db08-489f-b672-38f4cf4c4c73.png">

Teniendo tambien la informacion de cuando se esta realizando la practica por la tabla regdate (register date)


Ahora como ultimo paso haremos un push para docker y que las imagenes esten subidas a docker hub para que se puedan descargar por otras personas, estas no se van a poder subir de forma conjunta con el compose asi que vamos a realizar 3 push de cada imagen independiente (phpmyadmin, mysql y tomcat).

<img width="200" alt="Captura de Pantalla 2022-06-10 a las 18 19 38" src="https://user-images.githubusercontent.com/91618773/173108988-d7f41b4d-e94c-4a97-b844-8670fe3fa54d.png">

A continuación nos preguntará con que usuarios queremos realizar el push, como ya hemos iniciado sesion posteriormente a la hora de entregar la practica nos sale de esta manera ya usando mi usuario iglesiascarlos (cuenta de docker hub) para hacer los 3 push:

<img width="107" alt="Captura de Pantalla 2022-06-10 a las 18 21 44" src="https://user-images.githubusercontent.com/91618773/173109329-076b9c2b-b2f4-4e3e-b8e0-53d091f0833d.png">

<img width="190" alt="Captura de Pantalla 2022-06-10 a las 18 21 25" src="https://user-images.githubusercontent.com/91618773/173109267-5c234032-ac67-4071-a34c-fc6063157fd2.png">

Y por ultimo nos enseña por consola como se realiza el push:

<img width="461" alt="Captura de Pantalla 2022-06-10 a las 18 22 23" src="https://user-images.githubusercontent.com/91618773/173109505-569dfee3-809c-4bc1-9b2c-da08c78583e5.png">

Link docker hub mysql push:
https://hub.docker.com/r/iglesiascarlos/mysql

<img width="485" alt="Captura de Pantalla 2022-06-10 a las 18 28 45" src="https://user-images.githubusercontent.com/91618773/173110536-b8edc414-7a28-4739-8e2b-5db14a914109.png">

Link docker hub tomcat push:
https://hub.docker.com/r/iglesiascarlos/tomcat

<img width="502" alt="Captura de Pantalla 2022-06-10 a las 18 29 09" src="https://user-images.githubusercontent.com/91618773/173110609-4d5b3eda-3cba-4304-93dc-79cce462072d.png">



Link docker hub phpmyadmin push:
https://hub.docker.com/r/iglesiascarlos/phpmyadmin

<img width="688" alt="Captura de Pantalla 2022-06-10 a las 18 28 20" src="https://user-images.githubusercontent.com/91618773/173110465-4cce207a-76b6-4c78-a75c-627805bda4a8.png">
