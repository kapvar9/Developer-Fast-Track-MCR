# Lab. #6 - Monitoreo con APM en OCI

En este paso, creará un ambiente de desarrollo, con el servicio **OCI DevOps**, que automatizará la entrega de una aplicación en contenedores a un clúster de Kubernetes.

 ## <a name="Paso1"></a> Paso 1: Aprendiendo sobre APM

 1. En el🍔menú de hamburguesas, vaya a: **Observability & Management** → **Application Perfomance Monitoring** → **Home**.
 
 Acceda a **Cloud Shell** haciendo clic en el icono como en la imagen a continuación.
 
![imagen](https://user-images.githubusercontent.com/59672915/200052850-05cec204-2e29-40fd-900a-dadcde72601e.png)


 2. En caso de no estar seleccionado un **Compartment** o un **APM Domain** los seleccionamos y tambien configuramos a gusto el filtro de **Tiempo**

 ```shell
 git clone https://github.com/CeInnovationTeam/BackendFTDev.git
 ```

 3. Veremos como se despliegan diferentes componentes para analizar metricas
  
 ![imagen](https://user-images.githubusercontent.com/59672915/200052882-ee579c58-a49d-4f16-9b7d-5d51672769b3.png)

 4. Podemos ir a la esquina superior izquierda y seleccionar desde el menu desplegable **Administration**
  
 ![imagen](https://user-images.githubusercontent.com/59672915/200052964-7cd3cc9e-8c9f-4191-97dc-e8ffea5111c2.png)

 5. Desde esta pagina podemos crear nuevos dominios APM desde el botón **Create APM Domain**.

 ![imagen](https://user-images.githubusercontent.com/59672915/200053043-a23d0952-0b6d-4acd-9a52-d5b3078dfeed.png)

 6. Podemos volver al **Home** haciendo click en la barra lateral izquierda

 ![imagen](https://user-images.githubusercontent.com/59672915/200053072-901e6a3d-f315-4260-8b5d-07f1b90b6807.png)

 7. Si scrolleamos hacia abajo podemos ver tambien diferentes paneles donde se detalla como los usuarios interactuan con nuestra aplicacion

 ![imagen](https://user-images.githubusercontent.com/59672915/200054412-0ac0422e-a949-40a6-b869-22cb01b3ec4e.png)

 8. Desde el recuadro que se llama **Web Apps** podemos seleccionar una de nuestras aplicaciones y nos llevará directamente a su **Dashboard** donde apareceran tambien sus respectivas metricas

 9. Desde aqui podemos ver metricas especificas de nuestra aplicacion con sus respectivas estadisticas
 
![imagen](https://user-images.githubusercontent.com/59672915/200054455-d257fb7e-7f53-4adb-8666-86e2fd7e514f.png)

 10. Ahora debemos ir a la esquina superior izquierda y seleccionar desde el menu desplegable **Home**.

 11. Vamos a hacer click en el recuadro de **Traces** el cual nos dará mayor informacion sobre el rendimiento de nuestra aplicación segun los parametros que definimos 

![imagen](https://user-images.githubusercontent.com/59672915/200054455-d257fb7e-7f53-4adb-8666-86e2fd7e514f.png)

