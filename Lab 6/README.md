# Lab. #6 - Monitoreo con APM en OCI

En este paso, creará un ambiente de desarrollo, con el servicio **APM**, que permitira la visualizacion de diferentes metricas sobre nuestras aplicaciones

 ## <a name="Paso1"></a> Paso 1: Aprendiendo sobre APM

 1. En el🍔menú de hamburguesas, vaya a: **Observability & Management** → **Application Perfomance Monitoring** → **Home**.

![imagen](https://user-images.githubusercontent.com/59672915/201534619-24826bd7-28b0-4092-853f-3ffc35963590.png)

 2. En caso de no estar seleccionado un **Compartment** o un **APM Domain** los seleccionamos y tambien configuramos a gusto el filtro de **Tiempo**

![imagen](https://user-images.githubusercontent.com/59672915/201535413-6521ff43-e5b5-47aa-af8e-00cb9ef60169.png)

 3. Veremos como se despliegan diferentes componentes para analizar metricas
  
![imagen](https://user-images.githubusercontent.com/59672915/201535457-45c43f4f-9fc5-4782-b9fb-b0e28becafe9.png)

 4. Podemos ir a la esquina superior izquierda y seleccionar desde el menu desplegable **Administration**
 
 ![imagen](https://user-images.githubusercontent.com/59672915/201535530-c549de0d-ddf6-46c6-a959-a3f9841eaa6b.png)

 5. Desde esta pagina podemos crear nuevos dominios APM desde el botón **Create APM Domain**.

![imagen](https://user-images.githubusercontent.com/59672915/201535803-2f71f670-1798-4f1d-88a9-2f7a68a188e6.png)

 6. Podemos volver al **Home** haciendo click en la barra lateral izquierda

![imagen](https://user-images.githubusercontent.com/59672915/201535842-cad17efe-b864-4554-aa7a-ba5f87945069.png)

 7. Si scrolleamos hacia abajo podemos ver tambien diferentes paneles donde se detalla como los usuarios interactuan con nuestra aplicacion

![imagen](https://user-images.githubusercontent.com/59672915/201535918-0289c37a-3776-4007-88b2-bcc9c0f1518b.png)

 8. Desde el recuadro que se llama **Web Apps** podemos seleccionar una de nuestras aplicaciones y nos llevará directamente a su **Dashboard** donde apareceran tambien sus respectivas metricas
 
 ![imagen](https://user-images.githubusercontent.com/59672915/201536141-b00f7561-534a-4376-81ff-aa28a09a6e35.png)

 9. Desde aqui podemos ver metricas especificas de nuestra aplicacion con sus respectivas estadisticas
 
![imagen](https://user-images.githubusercontent.com/59672915/201536529-e4fa9533-67d0-4d8a-99e4-081dc66e008b.png)

 10. Ahora debemos ir a la esquina superior izquierda y seleccionar desde el menu desplegable **Home**.
 
![imagen](https://user-images.githubusercontent.com/59672915/201536628-925c94d8-81c1-45ad-afc7-1f0bc2295c9d.png)

 11. Vamos a hacer click en el recuadro de **Traces** el cual nos dará mayor informacion sobre el rendimiento de nuestra aplicación segun los parametros que definimos 

![imagen](https://user-images.githubusercontent.com/59672915/201536667-d7e42350-509d-48fb-8589-04ef14cdf87e.png)

12. Desde este tablero podemos seleccionar distintas querys para consultar la informacion y se nos mostrará cada status disponible

![imagen](https://user-images.githubusercontent.com/59672915/201537396-9729a9c1-742e-4133-a070-78dd2f508f78.png)

13. Tambien podemos ver de manera especifica cada trace y asi tener mas detalles 

![imagen](https://user-images.githubusercontent.com/59672915/201659291-ba968e3b-7d84-404c-b0b0-f2591f01dee5.png)

14. Este seria el tablero de detalles, pero incluso si en **Spans** hacemos click, podremos acceder a otro listado con mayor información

![imagen](https://user-images.githubusercontent.com/59672915/201659926-763b0cd8-9f28-4782-8193-e627922a54b0.png)

15. Esta información tambien puede contener logs 

![imagen](https://user-images.githubusercontent.com/59672915/201660034-870528e7-38e9-46b8-bc57-2d476cefc723.png)

 16. Podemos volver al **Home** haciendo click en la barra lateral izquierda
 
 ![imagen](https://user-images.githubusercontent.com/59672915/201660410-24bd9183-7545-44bd-acf3-93de041179b5.png)
 
 17. Ahora veremos el funcionamiento y funcionalidades de los **Monitors**

![imagen](https://user-images.githubusercontent.com/59672915/201664091-c375aa0f-fb40-4ccd-9ea7-3a9211c22233.png)

18. Una vez hecho click en el monitor llegaremos a esta pagina donde tendremos la informacion de nuestro monitor y tambien podremos ver informacion historica de nuestro monitor

![imagen](https://user-images.githubusercontent.com/59672915/201667752-dbfd5957-f65d-4404-8292-e2f9cb054537.png)

![imagen](https://user-images.githubusercontent.com/59672915/201667654-0e6259bb-dfe4-4b45-a811-2a77f2ab7386.png)

19. Adicionalmente si hacemos click en los tres puntos al lado derecho de cualquier **History** tenemos varias opciones a nuestra disposicion para descargar informacion

![imagen](https://user-images.githubusercontent.com/59672915/201668062-a4282ac3-2dbb-4d7b-9837-5314df0e37a4.png)

20. Podemos ver screenshots de nuestra app, descargarlas y tambien descargar los logs que esten registrados en nuestro monitor 

![imagen](https://user-images.githubusercontent.com/59672915/201670902-6687417a-34f4-4a41-803b-41af49517b8d.png)

21. Si quisieramos crear nuestro monitor tendriamos que hacer click aquí 

![imagen](https://user-images.githubusercontent.com/59672915/201672803-aa129606-b06d-46fe-a684-e15d9f336164.png)

22. Hacer click en **Create Monitor** tal como en la imagen 

![imagen](https://user-images.githubusercontent.com/59672915/201672985-9922ab0c-05cd-45cb-9690-c186ae723e3c.png)

23. Los monitores pueden ser de diversos tipos, como los detallados aqui en la imagen

![imagen](https://user-images.githubusercontent.com/59672915/201673151-607220fd-dd43-461b-8d39-707b37fed022.png)

24. Cada uno de ellos tiene un formulario el cual podremos llenar con lo que necesitemos, como el nombre o la URL

![imagen](https://user-images.githubusercontent.com/59672915/201673338-1545a6e6-94bd-4329-841a-52d36d7346a2.png)


Y con eso terminamos el Lab#6 Esperamos que te hayan parecido interesante las funcionalidades de APM en Oracle Cloud










