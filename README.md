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



## Paso 3
En el archivo Dockerfile importante que tenga la D mayuscula y la f minuscula (fallo muy común) lo que introduciremos en el es lo siguiente

## Paso 4

## Paso 5

## Paso 6

## Paso 7

## Paso 8

## Paso 9
