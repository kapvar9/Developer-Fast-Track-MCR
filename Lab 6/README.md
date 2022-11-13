# Lab. #6 - Monitoreo con APM en OCI

En este paso, creará un ambiente de desarrollo, con el servicio **OCI DevOps**, que automatizará la entrega de una aplicación en contenedores a un clúster de Kubernetes.

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

