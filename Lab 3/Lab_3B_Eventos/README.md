<h1>Creando una función y configurando el ambiente de Cloud Shell</h1>
<p>
    En este laboratorio, crearemos nuestra regla que asignará los eventos de creación a nuestro object storage y activará la función que creamos en la práctica anterior. Para esta tarea utilizaremos los siguientes recursos:
</p>
<ul>
    <li><b>Oracle Events:</b> <a
            href="https://docs.oracle.com/es-ww/iaas/Content/Events/Concepts/eventsoverview.htm">Ver más
            &#129299;</a></li>
</ul>
<h2>Creando regla de evento</h2>
<ol>
    <li>
        En el menú &#127828;, haz clic en Observability & Management &#10145; Events Services
    </li>
    <br>
    <li>Selecciona el compartimiento creado en el laboratorio 1 y haz clic en <b>Create Rule</b>
        <br>
        <img src="/Lab 3/images/Screenshot_20.png" alt="img20">
    </li>
    <br>
    <li>
        Llena la sección de <b>Rule Conditions</b> con esta información:
        <br>
        <br>
        <ul>
            <li><b>Display name: </b>Regla1_Workshop</li>
            <li><b>Display name: </b>Primera regla</li>
            <li><b>Condition: </b>Event type</li>
            <li><b>Service name: </b>Object Storage</li>
            <li><b>Display name: </b>Object Create</li>
        </ul>
        <br>
        <img src="/Lab 3/images/Screenshot_21.png" alt="img21">
        <br>
    </li>
    <br>
    <li>Llena la sección de <b>Actions</b> con esta información:
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_22.png" alt="img22">
    </li>
    <br>
    <li>Haz clic en <b>Create Rule</b>
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_23.png" alt="img23">
    </li>
</ol>
    <br>
    <h2>Probando el funcionamiento del flujo</h2>
    <p>
        Ahora que tenemos el flujo creado, podemos probar su funcionalidad. Para ello:
        <ul>
            <li>Abriremos una nueva pestaña en el navegador, donde accederemos a nuestro flujo</li>
            <li>En nuestra pestaña principal probaremos la creación de un archivo .txt en nuestro bucket</li>
        </ul>
    </p>
    <h3>En la nueva pestaña</h3>
<ol>
    <li>
        Accede a tu cuenta de  <a href="https://www.oracle.com/cloud/sign-in.html">Oracle cloud &#127781;</a> y loggeate
    </li>
    <li>
        En el menú &#127828; , accede a Analytics & AI &#10145; Messaging
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_24.png" alt="img24">
    </li>
    <br>
    <li>
        Verifica que te encuentras dentro del compartimiento creado en el Lab#1 y verifica que ya existe un stream creado con el nombre de <b>workshop</b>
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_25.png" alt="img25">
    </li>
    <br>
    <li>
        Haz clic en el stream <b>workshop</b> para visualizar su información
    </li>
    <li>
        Manten la pestaña abierta y abre la pestaña principal del navegador
    </li>
</ol>
<h3>En la pestaña principal</h3>
<ol>
    <li>
        En el menú &#127828; , accede a Storage &#10145; Buckets
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_26.png" alt="img26">
    </li>
    <br>
    <li>
        Encontrarás un bucket ya creado con el nombre <b>workshop_bucket</b>. Haz clic en este.
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_27.png" alt="img27">
    </li>
    <li>
        El disparo de eventos usando un bucket es opcional, por lo que puede ser habilitado o deshabilitado en cualquier momento. Para este laboratorio, habilitaremos esta opción
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_28.png" alt="img28">
    </li>
    <br>
    <li>
        Para realizar las pruebas, manten esta pestaña abierta junto a la anterior
    </li>
</ol>
<h3>Pruebas</h3>
<ol>
    <li>
        Crea un archivo en formato <b>.txt</b> con el siguiente texto
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_29.png" alt="img29">
    </li>
    <br>
    <li>
        Vuelve a la pestaña principal, donde se tiene la página del bucket <b>workshop_bucket</b> y sube el archivo creado
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_30.png" alt="img30">
    </li>
    <br>
    <li>
        Haz clic en <b>Close</b>. Visualizarás el archivo subido en la sección de <b>Objects</b>
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_31.png" alt="img31">
    </li>
    <br>
    <li>
        Ahora vuelve a la pestaña principal, donde se tiene la página del stream <b>workshop</b> abierta y haz clic en <b>Load Messages</b>
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_32.png" alt="img32">
    </li>
    <br>
    <li>
        No se preocupe si no se encontraron elementos, este proceso puede llevar algún tiempo ya que es la primera vez que se ejecuta la función. Espere unos segundos e intente cargar mensajes nuevamente si es necesario.
        <br>
        <br>
        <img src="/Lab 3/images/Screenshot_33.png" alt="img33">
    </li>
</ol>

COMPLETASTE EXITOSAMENTE EL LABORATORIO N#3.B !! 💯✅

<a href="https://github.com/kapvar9/Developer-Fast-Track-MCR/tree/main/Lab%203">Regresar</a>
