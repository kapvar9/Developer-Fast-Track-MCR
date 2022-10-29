<h1>Creando una función y configurando el ambiente de Cloud Shell</h1>
<p>
    En este laboratorio crearemos nuestra primera aplicación en la plataforma de funciones. Implementaremos la función responsable de recopilar y enviar el contenido de un archivo en un object storage. También usaremos la función Cloud Shell para administrar/probar nuestra función. Para esta tarea utilizaremos los siguientes recursos:
</p>
<ul>
    <li><b>Oracle Functions:</b> <a href="https://docs.oracle.com/es-ww/iaas/Content/Functions/Concepts/functionshowitworks.htm">Ver más 	
        &#129299;</a></li>
    <li><b>Cloud Shell:</b> <a href="https://docs.oracle.com/es-ww/iaas/Content/API/Concepts/cloudshellintro.htm">Ver más 	
        &#129299;</a></li>
</ul>

<h2>Recopilando información necesaria</h2>

<p>
    <h3>&#128161;Tips &#9729;</h3>
    <ul>
        <li>Para este laboratorio es necesario que hayas ejecutado los laboratorios 1 y 2</li>
        <li>Tener a la mano los datos que recopilaste en el lab2</li>
    </ul>
    
</p>
<h2>¿Cómo crear una función?</h2>
<br>
<ol>
    <li>Abre el menú &#127828; y ve a la siguiente ruta: Developer Services &#10145; Functions &#10145; Applications
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_1.png" alt="img1">
    </li>
        <br>
    <li>Selecciona el compartimiento creado en el laboratorio 1 y haz clic en <b>Create application</b>
        <br>
        <img src="/Lab 3/images/Screenshot_2.png" alt="img2">
    </li>
    <br>
    <li>Define un nombre para tu función, selecciona la VCN y la subnet indicadas en la imagen y por último, dale clic a <b>Create</b>
        <br>
        <img src="/Lab 3/images/Screenshot_3.png" alt="img3">
    </li>
</ol>
    <br>

    <h2>Configurando ambiente de Cloud Shell</h2>
    <p>Para este lab, usaremos la función ya creada llamada <b>functionworkshop</b> que se encuentra dentro del compartimiento DevFT. Recuerda que la ruta es Developer Services &#10145; Functions &#10145; Applications &#10145; functionworkshop</p>
        <br>
        <img src="/Lab 3/images/image13.png" alt="img13">
        <br>
<ol>        
    <li>
        <p>Seleccionamos la función para ver sus detalles y nos ubicamos en la sección <b>Getting Started</b></p>
        <br>
            <img src="/Lab 3/images/Screenshot_4.png" alt="img4">
        <br>

    </li>
    <br>
    <br>
    <li>Selecciona la opción de <b>Configuración de Cloud Shell</b>
        <br>
        <img src="/Lab 3/images/Screenshot_5.png" alt="img5">
    </li>
    <br>
    <h3>&#128161;Tip &#9729;</h3>
    En este paso ejecutaremos algunos comandos. Te recomendamos tener un bloc de notas abierto con el que copies los códigos, modifiques los campos necesarios y luego, puedas pegarlo en el Cloud Shell
    <br>
    <br>
    <li>Clic en <b>Launch Cloud Shell</b>
    <br>
        <img src="/Lab 3/images/Screenshot_6.png" alt="img6">
    </li>
    <br>
    <h3>Setup fn on Cloud Shell</h3>
    <br>
    <li>Ejecuta los pasos 1 y 2 copiando los códigos en el Cloud Shell
        <br>
        <img src="/Lab 3/images/Screenshot_7.png" alt="img7">
        <br>
    </li>
    <br>
    <li>Agrega un repository name prefix único para distinguirte de los repositorios de otros usuarios &#10145; fn update context registry iad.ocir.io/idambthrb5ko/<b>[repo-name-prefix]</b>
        <br>
        <br>
        Te debe salir este mensaje &#128071;
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_8.png" alt="img8">
        <br>
    </li>
    <br>
    <li>Para el paso 5, puedes usar tu token generado en el lab#2 o generar uno nuevo. Copia el código y ejecuta el paso 6
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_9.png" alt="img9">
        <br>
        <h4>Resultado  &#128071</h4>
        <img src="/Lab 3/images/Screenshot_10.png" alt="img10">
        <br>
    </li>
    <br>
    <li>Copia el código y ejecuta el paso 7
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_11.png" alt="img11">
        <br>
        <h4>Resultado  &#128071</h4>
        <img src="/Lab 3/images/Screenshot_12.png" alt="img12">
        <br>
    </li>
    <h2>Crear, desplegar e invocar la función </h2>
    <li>Clona el repositorio que se va a usar en esta workshop &#10145; $ git clone https://github.com/gustavogaspar/events-function.git
        <br>
    </li>
    <br>
    <li>Entra a la carpeta del proyecto &#10145; $ cd events-function
    </li>
    <br>
    <li>Copia el código del paso 10
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_16.png" alt="img16">
        <br>
        <h4>El código tardará un poco en ejecutarse. Te debería quedar así &#128071</h4>
        <img src="/Lab 3/images/Screenshot_17.png" alt="img17">
        <br>
    </li>
    <br>
    <li>Modifica el código del paso 11 para invocar a la función &#10145;  fn invoke functionworkshop final-workshop
        <br>
        <h4>Te debe devolver este mensaje &#128071</h4>
        <img src="/Lab 3/images/Screenshot_18.png" alt="img18">
        <br>
    </li>

</ol>
