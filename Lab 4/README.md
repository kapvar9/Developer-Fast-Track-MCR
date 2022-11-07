# Lab. #4 - Automating Deployment

En este paso, creará un ambiente de desarrollo, con el servicio **OCI DevOps**, que automatizará la entrega de una aplicación en contenedores a un clúster de Kubernetes.


**Aprenderás todo el paso a paso de esta implementación:**
 - [Pre Reqs: Recopilación de información relevante para el proceso.](#PreReqs)
 - [Paso 1: Clone el repositorio y mueva el contenido al repositorio del proyecto DevOps](#Paso1)
 - [Paso 2: Crear y configurar el proceso de Build (CI)](#Paso2)
 - [Paso 3: Crear y configurar entrega de artefactos (CI)](#Paso3)
 - [Paso 4: Crear y configurar entrega de aplicacion a cluster de kubernetes (CD)](#Paso4)
 - [Paso 5: Configurar trigger de flujo y conectar pipelines de CI/CD](#Paso5)
 - [Paso 6: Ejecucion de tests](#Paso6)

 - - -

 ## <a name="PreReqs"></a> Pre Reqs: Recopilación de información relevante para el proceso.

 1. [Inicie sesión](https://www.oracle.com/cloud/sign-in.html) en su cuenta OCI . 

 2. Realizar los laboratorios [Lab. #1](https://github.com/kapvar9/Developer-Fast-Track-MCR/tree/main/Lab%201) y [Lab #2](https://github.com/kapvar9/Developer-Fast-Track-MCR/tree/main/Lab%202).

 3. En el 🍔 menú de hamburguesas, vaya a: **Observability & Management** → **Application Performance** → **Administration**.

 ![imagen](https://user-images.githubusercontent.com/59672915/200050273-107ca551-3079-4dcb-b6fb-fd79438e22ad.png)

 4. En la esquina inferior izquierda, debajo de Scope , valide que el Comparment creado en [Lab. #1](../Lab.%20%231%20-%20Resource%20Provisioning) está seleccionado.

 5. Seleccione el dominio APM de la lista.
   
![imagen](https://user-images.githubusercontent.com/59672915/200050637-9431de5e-a19e-4830-833e-a83e771c2330.png)

 6. Copie la clave privada del dominio en un notepad.

 ![imagen](https://user-images.githubusercontent.com/59672915/200050656-b1ec9df8-dbfe-43bf-8c82-df330569d370.png)
 
 ¡Eso es! ¡Hemos cumplido todos los requisitos previos para el laboratorio!

 - - -

 ## <a name="Paso1"></a> Paso 1: clone el repositorio y mueva el contenido al repositorio del proyecto DevOps

 1. Acceda a **Cloud Shell** haciendo clic en el icono como en la imagen a continuación.
 
![imagen](https://user-images.githubusercontent.com/59672915/200052850-05cec204-2e29-40fd-900a-dadcde72601e.png)


 2. Clona el repositorio del proyecto.

 ```shell
 git clone https://github.com/CeInnovationTeam/BackendFTDev.git
 ```

 3. En el🍔menú de hamburguesas, vaya a: **Developer Services** → **DevOps** → **Projects**.
  
 ![imagen](https://user-images.githubusercontent.com/59672915/200052882-ee579c58-a49d-4f16-9b7d-5d51672769b3.png)

 4. Acceda al proyecto enumerado (creado en el aprovisionamiento de Resource Manager😄).
  
 ![imagen](https://user-images.githubusercontent.com/59672915/200052964-7cd3cc9e-8c9f-4191-97dc-e8ffea5111c2.png)

 5. En la página del proyecto, haz clic en **Create repository**.

 ![imagen](https://user-images.githubusercontent.com/59672915/200053043-a23d0952-0b6d-4acd-9a52-d5b3078dfeed.png)

 6. Rellene el formulario de la siguiente manera:

   - **Name:** ftRepo
   - **Description:** (Definir cualquier descripción).
   - **Default branch:** main

 ![imagen](https://user-images.githubusercontent.com/59672915/200053072-901e6a3d-f315-4260-8b5d-07f1b90b6807.png)

 7. En la página del repositorio recién creada, haga clic **HTTPS** y:

- [1] Copie en el Bloc de notas la información del usuario que se usará para trabajar con git (**Usuário Git**).
- [2] Copie el comando git clone y ejecútelo en Cloud Shell.

 ![imagen](https://user-images.githubusercontent.com/59672915/200054412-0ac0422e-a949-40a6-b869-22cb01b3ec4e.png)

 8. En Cloud Shell, al ejecutar el comando, ingrese el **Usuario Git** recién copiado y su **Auth Token** como contraseña.

 9. En este punto, Cloud Shell debería tener dos directorios nuevos:
 - BackendFTDev
 - ftRepo
 
![imagen](https://user-images.githubusercontent.com/59672915/200054455-d257fb7e-7f53-4adb-8666-86e2fd7e514f.png)

 10. Ejecute los siguientes comandos para copiar el contenido del repositorio **BackendFTDev**, al repositorio **ftRepo**.

 ```shell
 git config --global user.email "<su-email>"
 git config --global user.name "<su-username>"
 cp -r BackendFTDev/* ftRepo/
 cd ftRepo
 git add -A
 git commit -m "Inicio de projecto"
 git push origin main
 ```

*Al final del último comando , se puede volver a solicitar el **Usuário git**  y la contraseña (**Auth Token**) *.

 ## <a name="Paso2"></a> Paso 2: crear y configurar el proceso de compilación (CI)

 1. Vuelva a la página de inicio del proyecto DevOps.
 2. Haga clic en **Create build pipeline**. 

 ![imagen](https://user-images.githubusercontent.com/59672915/200364914-285cbaec-cb7b-4094-86af-bd030d6eb7ab.png)

 3. Complete el formulario de la siguiente manera y haga clic en **Create**:
   - **Name**: build
   - **Description**: (Definir cualquier descripción).

 ![imagen](https://user-images.githubusercontent.com/59672915/200364965-bdcac1bf-2c95-407f-92c9-ca102fa21b20.png)

 4. Abra el pipeline build recién creado.
 5. En la pestaña de parámetros, configure los siguientes parámetros:
  - APM_ENDPOINT: *Información recopilada en prerequisitos*.
  - APM_PVDATAKEY: *Información recopilada en prerequisitos*.
  - APM_AGENT_URL: *Información recopilada en prerequisitos*.

  **ATENCIÓN** - Al ingresar nombre, valor y descripción, haga clic en el signo "+" para guardar la información.
  
 ![imagen](https://user-images.githubusercontent.com/59672915/200365834-40f70568-9bf2-4303-a7b1-1857f06ac143.png)

 6. Acceda a la pestaña **Build Pipeline** y haga clic en **Add Stage**.

 ![imagen](https://user-images.githubusercontent.com/59672915/200365879-3e323305-0a94-40a9-b12e-aa6712c40e68.png)

 7. Seleccione la opción **Managed Build** y haga clic en **Next**.

 ![imagen](https://user-images.githubusercontent.com/59672915/200365950-5b97c309-f757-4233-adec-d8303df9feaa.png)

 8. Rellene el formulario de la siguiente manera:

- **Stage Name**: Creación de artefactos
- **Description**: (Definir cualquier descripción).
- **OCI build agent compute shape**: *no cambiar*.
- **Base container image**: *no cambiar*.
- **Build spec file path**: *no cambiar*.
      
![imagen](https://user-images.githubusercontent.com/59672915/200366262-62081f55-e640-4335-878d-9ca58e17f0c6.png)


9. En Repositorio de código principal, haga clic en **Select**, seleccione las opciones a continuación y haga clic en **Save**. 

- **Source Connection type**: OCI Code Repository
- **Repositório**: ftRepo
- **Select Branch**: *no cambiar*.
- **Build source name**: java_root
    
![imagen](https://user-images.githubusercontent.com/59672915/200366309-1f371a1e-3921-4f57-ac73-1021bf941361.png)

- Una vez hecho esto, haga clic en **Add**.

![imagen](https://user-images.githubusercontent.com/59672915/200367289-50b60b0a-b9fe-4ff8-9908-f92e217f5b12.png)


🤔En este punto es importante entender cómo funciona la herramienta.📝.
    
- La herramienta utiliza un documento en formato YAML para definir los pasos que se deben realizar durante el proceso de construcción de la aplicación.
- Por defecto este documento se llama build_spec.yaml y debe configurarse previamente de acuerdo a las necesidades de la aplicación.
- Luego, los pasos serán ejecutados por una instancia temporal (agente), que se aprovisionará al comienzo de cada ejecución y se destruirá al final del proceso.
- 🧾 [Documentación sobre cómo dar formato al documento de build](https://docs.oracle.com/pt-br/iaas/Content/devops/using/build_specs.htm)
- 📑 [Documento utilizado en este workshop (build_spec.yaml)](https://raw.githubusercontent.com/CeInnovationTeam/BackendFTDev/main/build_spec.yaml)

 ## <a name="Paso3"></a> Paso 3: crear y configurar la entrega de artefactos (CI)

 1. En la pestaña Build Pipeline, haga clic en el signo **"+"**, debajo de la etapa de **creación de artefactos** y en **Add Stage**.
     
![imagen](https://user-images.githubusercontent.com/59672915/200367811-4786cbcc-dabc-4f6c-bf54-55a759599087.png)


 2. Seleccione la opción **Deliver Artifacts** y haga clic en **Next**.
     
![imagen](https://user-images.githubusercontent.com/59672915/200367843-ac7b3f0d-4e40-48c7-99e9-9c072c8340db.png)


 3. Complete el formulario como se muestra a continuación y haga clic en **Create artifact**.
 - **Stage name**: Entrega de artefactos
 - **Description**: (Definir cualquier descripción).

![imagen](https://user-images.githubusercontent.com/59672915/200368068-baed6a4a-7f14-475c-a61b-e271718cb866.png)

 4. En la opción de selección de artefactos, complete como se indica a continuación y haga clic en **Add**.
- **Name**: backend_jar
 - **Type**: General artifact
 - **Artifact registry**: *seleccione el registro de artefactos generado por terraform llamado "artifact_repository"*.
- **Artifact location**: Set a Custom artifact location and version
- **Artifact path**: backend.jar
- **Version**: ${BUILDRUN_HASH}
- **Replace parameters used in this artifact**: Yes, substitute placeholders
       
![imagen](https://user-images.githubusercontent.com/59672915/200368117-85e05e35-9e6b-4e82-855b-db3b19143b7c.png)


5. Rellene el campo restante de la tabla de **Build config/result artifact name** con "aplicación" y haga clic en **Add**.
    
![](./Images/029_1-LAB4.png)

 6. En la pestaña Build Pipeline, haga clic en el signo **"+"** debajo de la etapa **Entrega de artefato** y haga clic en **Add Stage**.

 ![](./Images/031-LAB4.png)

 7. Nuevamente, haga clic en **Deliver Artifacts** y luego en **Next**.

 ![](./Images/028-LAB4.png)

 8. Complete el formulario como se muestra a continuación y haga clic en **Create Artifact**.
 - **Stage name**: Entrega de imágenes de contenedores
 - **Description**: (Definir cualquier descripción).

 ![](./Images/033_0-LAB4.png)
 
 9. En *Add artifact*, complete el formulario como se muestra a continuación y haga clic en **Add**.
- **Name**: backend_img
- **Type**: Container image repository
- **Artifact Source**: `<código-de-região>.ocir.io/${IMG_PATH}`
- **Replace parameters used in this artifact**: Yes, substitute placeholders
   
*Para Ashburn y Santiago, los códigos de región son respectivamente "iad" y "scl". Si se encuentra en otra región, utilice la [tabela de refêrencia](https://docs.oracle.com/en-us/iaas/Content/General/Concepts/regions.htm)*.
       
![](./Images/032_0-LAB4.png)

9. Complete el campo restante de la tabla de **Build config/result artifact name** con: docker-img y haga clic en **Add**.
       
![](./Images/033_1-LAB4.png)

<a name="FinalPasso3"></a> ¡Esto completa la parte Build (CI) del proyecto! Hasta ahora, hemos automatizado la compilación del código Java, hemos creado la imagen del contenedor y la hemos almacenado en los repositorios de artefactos e imágenes del contenedor, respectivamente. ¡Ahora para la parte de implementación (CD)!

## <a name="Paso4"></a> Paso 4: crear y configurar la entrega de aplicaciones en un clúster de Kubernetes (CD)

1. En **Cloud Shell** , para crear el secreto, ejecute los siguientes comandos e ingrese su OCID de usuario y token de autenticación, recopilados anteriormente.

 ```shell
  cd ftRepo/scripts/
  chmod +x create-secret.sh 
  ./create-secret.sh  
 ```

2. Espera el final del flujo.
        
![](./Images/039-LAB4.png)

 3. Vuelva a su proyecto DevOps haciendo clic en el🍔menú hamburguesa y accediendo a: **Developer Services**  → **Projects**.
 4. En la esquina izquierda, seleccione **Environments**.
         
![](./Images/040-LAB4.png)

 5. Haga clic en **Create New Environment**.

 6. Complete el formulario como se muestra a continuación y haga clic en **Next**.
  - **Environment type**: Oracle Kubernetes Engine
  - **Name**: OKE
  - **Description**: OKE

 7. Seleccione el clúster de Kubernetes y haga clic en **Create Envrinoment**.

 ![](./Images/041-LAB4.png)

 8. En la esquina izquierda, seleccione **Artifacts** y luego **Add Artifact**.
          
![](./Images/042-LAB4.png)

 9. Complete el formulario como se muestra a continuación y haga clic en **Add**.
 - **Name**: deployment.yaml
 - **Type**: Kubernetes manifest
 - **Artifact Source**: Inline
 - **Value**: pegue el contenido del archivo https://github.com/CeInnovationTeam/BackendFTDev/blob/main/scripts/deployment.yaml
 *No cambie la indentación (espacios) del documento, ya que esto puede romperlo .*.
 - **Replace parameters used in this artifact**: Yes, substitute placeholders
          
![](./Images/043_0-LAB4.png)

 10. En la esquina izquierda, seleccione **Deployment Pipelines** y luego haga clic en **Create Pipeline**.
          
![](./Images/044-LAB4.png)

 11. Complete el formulario como se muestra a continuación y haga clic en **Create pipeline**.
 - **Pipeline name**: deploy
 - **Description**: (Definir cualquier descripción).
          
![](./Images/048-LAB4.png)

 12. En la pestaña **Parameters** configure el siguiente parámetro:
 
 - REGISTRY_REGION: `<codigo-de-region>`.ocir.io  
          
![](./Images/049-LAB4.png)

 13. Regrese a la pestaña **Pipeline** y haga clic en **Add Stage**.
          
![](./Images/050-LAB4.png)

 14. Seleccione la opción **Apply Manifest to your Kubernetes Cluster** y haga clic en **Next**.
          
![](./Images/051-LAB4.png)

 15. Rellene el formulario de la siguiente manera:
 - **Name**: Deploy de aplicacion
 - **Description**: (establecer cualquier descripción).
 - **Environment**: OKE

![](./Images/052_0-LAB4.png)

16. Haz clic en **Select Artifact** y selecciona **deployment.yaml**.

![](./Images/052_1-LAB4.png)

17. Una vez hecho esto, haga clic en **Add**.
 
 ¡Con eso terminamos la parte de Despliegue (CD) de nuestro proyecto! En el siguiente paso, conectaremos ambas canalizaciones y definiremos un disparador (trigger) para que comience el proceso automatizado.

 ## <a name="Paso5"></a> Paso 5: configurar el trigger y conectar pipelines de CI/CD

  1. Regrese al proyecto haciendo clic en el🍔menú de hamburguesas y yendo a: **Developer Services**  → **Projects**.
  2. En la esquina izquierda, seleccione **Triggers** y, a continuación, haga clic en **Create Trigger**.

  ![](./Images/053-LAB4.png)

  3. Complete el formulario como se muestra a continuación y haga clic en **Create**.
  - **Name**: Inicio
  - **Description**: (Definir cualquier descripción).
  - **Source connection**: OCI Code Repository
  - **Select code repository**: ftRepo
  - **Actions**: Add Action
    - **Select Build Pipeline**: build
    - **Event**: Push (check) 
    - **Source branch**: main

![](./Images/054-LAB4.png)

*A partir de ese momento, cualquier nuevo push realizado en el repositorio del proyecto iniciará el pipeline de build creada en este taller .*.

4. Vuelva a la configuración de pipelines del proyecto seleccionando **Build Pipelines** → **build**.

![](./Images/055-LAB4.png)

  5. En la pestaña Build Pipeline, haga clic en el signo **"+"** debajo de la etapa **Entrega de Imagem de Container** y haga clic en **Add Stage**.

![](./Images/056-LAB4.png)

6. Seleccione el elemento **Trigger Deployment** y haga clic en **Next**.

![](./Images/057-LAB4.png)

7. Complete el formulario como se muestra a continuación y haga clic en **Add**.
- **Nome**: Inicio de Deployment
- **Description**: (Definir cualquier descripción).
- **Select deployment pipeline**: deploy

*Mantenga los otros campos sin cambios*.

![](./Images/058-LAB4.png)

Enhorabuena por llegar hasta aquí!! ¡Nuestro pipeline está listo! En el siguiente paso validaremos el proyecto, comprobando si todo está bien.

 ## <a name="Paso6"></a> Paso 6: Ejecución y prueba
  1.  Regrese al proyecto haciendo clic en el🍔menú de hamburguesas y yendo a: **Developer Services**  → **Projects**.
  2.  Vuelva a la configuración de pipelines del proyecto seleccionando **Build Pipelines** → **build**.
  
  ![](./Images/055-LAB4.png)

  3. En la esquina superior derecha, seleccione **Start Manual Run**.

![](./Images/055_1-LAB4.png)

  4. Mantenga la información del formulario predeterminado y haga clic en **Start Manual Run**.
  5. Espere a que se ejecute el flujo.
  6. Acceda a Cloud Shell nuevamente y ejecute el siguiente comando.

  ```shell
  kubectl get svc
  ```

  7. Copie la información de EXTERNAL-IP del servicio svc-java-app tan pronto como esté disponible.

```shell
NAME           TYPE           CLUSTER-IP      EXTERNAL-IP       PORT(S)          AGE
kubernetes     ClusterIP      10.96.0.1       <none>            443/TCP          30h
svc-app        LoadBalancer   10.96.252.115   <svc-app-ip>   80:31159/TCP     29h
svc-java-app   LoadBalancer   10.96.16.229    <EXTERNAL-IP>   8081:32344/TCP   103m
```

  8. En **Cloud Shell**, ejecute el siguiente comando reemplazando la información con`<EXTERNAL-IP>` la IP copiada.

   ```shell
  curl --location --request POST '<EXTERNAL-IP>:8081/processcart' \
--header 'Content-Type: application/json' \
--data '[
      {   "nome":"Oranges",
      "preco":1.99
      },
      {   "nome":"Apples",
          "preco":2.97
      },
      {   "nome":"Bananas",
          "preco":2.99
      },
      {   "nome":"Watermelon",
          "preco":3.99
      }
]'
```
- ¡Debería ver la suma de los precios de los productos como respuesta! ¡Prueba a modificar los valores para comprobar la suma!

![](./Images/059-LAB4.png)

### 👏🏻 Felicidades!!! ¡Pudo construir con éxito un pipeline completo de DevOps en OCI!

COMPLETASTE EXITOSAMENTE EL LABORATORIO N#4 !! 💯✅

<a href="https://github.com/kapvar9/Developer-Fast-Track-MCR">Regresar</a>

