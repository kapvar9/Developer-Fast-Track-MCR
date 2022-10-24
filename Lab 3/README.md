<header>
  <h1>Lab 1 - Preparando el ambiente con Resource Manager</h1>
</header>


<body>
  <section>
    <p>
      En este laboratorio prepararemos la infraestructura base para el taller, donde crearemos los siguientes servicios:
    <ul>
      <li><b>Compartimiento:</b>
        Separación lógica de recursos dentro de la nube. El compartimento juega un papel fundamental en el control de
        las
        políticas de acceso, la gobernanza y el control de costos dentro del arrendamiento. <a
          href="https://docs.oracle.com/es-ww/iaas/Content/Identity/Tasks/managingcompartments.htm">Ver más</a></li>
      <li><b>Resource Manager Stack:</b>
        Pila de códigos terraform que se usarán en el taller
        <a href="https://docs.oracle.com/es-ww/iaas/Content/ResourceManager/Concepts/resourcemanager.htm">Ver más</a>
      </li>
      <li><b>Dynamic Groups:</b>
        Los grupos dinámicos le permiten agrupar instancias informáticas de Oracle Cloud Infrastructure como actores
        "principales" (similares a los grupos de usuarios)
        <a href="https://docs.oracle.com/es-ww/iaas/Content/Identity/Tasks/managingdynamicgroups.htm">Ver más</a>
      </li>
      <li><b>Políticas de acceso:</b>
        Es un documento que especifica los usuarios que pueden acceder a recursos determinados de Oracle Cloud
        Infrastructure de la compañía y el método de acceso.
        <a href="https://docs.oracle.com/es-ww/iaas/Content/Identity/Concepts/policygetstarted.htm">Ver más</a>
      </li>
      <li><b>Virtual Cloud Network: </b>
        Red virtual en nube
        <a href="https://docs.oracle.com/es-ww/iaas/Content/Rover/Network/VCN/vcn_management.htm#VCNManagement">Ver
          más</a>
      </li>
      <li><b>OCI Streaming Service:</b>
        Servicio de transmisión compatible con Kafka (publicar - suscribirse)
        <a href="https://docs.oracle.com/es-ww/iaas/Content/Streaming/Concepts/streamingoverview.htm">Ver más</a>
      </li>
      <li><b>Object Storage:</b>
        Plataforma de almacenamiento en Internet de alto rendimiento que ofrece durabilidad de datos fiable y rentable.
        Puede almacenar una cantidad ilimitada de datos no estructurados de cualquier tipo de contenido, incluidos los
        datos analíticos y el contenido enriquecido, como imágenes y vídeos.
        <a
          href="https://docs.oracle.com/es-ww/iaas/Content/Object/Concepts/objectstorageoverview.htm#Overview_of_Object_Storage">Ver
          más</a>
      </li>
      <li><b>Container Registry:</b>
        Registro de contenedores similares a Docker Hub
        <a href="https://docs.oracle.com/es-ww/iaas/Content/Registry/Concepts/registryoverview.htm">Ver más</a>
      </li>
    </ul>
    </p>
  </section>

  <section>
    <h2>Creando el compartimiento</h2>
    <ol type="1">
      <li>Accede a tu cuenta de Oracle Cloud &#128073; https://www.oracle.com/cloud/sign-in.html </li>
      <br>
      <img src="/Lab 3/images/image1.png" alt="image1">
      <br>
      <br>
      <li>
        Acceda al menú &#127828;, en Identidad y seguridad y clic en Compartimentos.
        <br>
        <br>
        <img src="/Lab 3/images/image2.png" alt="image2">
        <br>
      </li>
      <br>
      <li>
        Clic en crear compartimiento
        <br>
        <br>
        <img src="/Lab 3/images/image3.png" alt="image3">
        <br>
      </li>
      <br>
      <li>
        Rellena los campos y haz clic en <b>Create Compartment</b>
        <br>
        <br>
        <ul>
          <li>
            Nombre: < Ingresa el nombre del compartimento>
          </li>
          <li>
            Descripción: < Definir una descripción para el compartimento>
          </li>
          <li>
            Compartimento principal: Selecciona el compartimento marcado como raíz (root)
          </li>
        </ul>
        <br>
        <br>
        <img src="/Lab 3/images/image4.png" alt="image4">
        <br>
      </li>
      <br>
      <li>

        Espere un momento a que el compartimiento termine de crearse. Aparecerá en la lista de compartimientos creados.
        <br>
        <br>
        <img src="/Lab 3/images/image5.png" alt="image5">
        <br>
      </li>
    </ol>
  </section>
  <section>
    <h2>Recopilación de la información necesaria</h2>
    <ol type="1">
      <li>Selecciona el compartimiento recién creado para ver sus detalles </li>
      <br>
      <img src="/Lab 3/images/image6.png" alt="image6">
      <br>
      <br>
      <li>
        Copia en un block de notas el <b>Nombre</b> y el <b>OCID</b>
        <br>
        <br>
        <img src="/Lab 3/images/image7.png" alt="image7">
        <br>
      </li>
  </section>
  <section>
    <h2>Creación de una pila y un job</h2>
    <ol type="1">
      <li>Accede al menú &#127828;, en Developer Services y clic en <b>Stacks</b>.  </li>
      <br>
      <img src="/Lab 3/images/image8.png" alt="image8">
      <br>
      <br>
      <li>
        En <b>List Scope</b>, seleccina el compartimiento en el que quieres crear la pila. Para este ejercicio, usaremos el compartimiento <b>Workshop</b>
        <br>
        <br>
        <img src="/Lab 3/images/image7.png" alt="image7">
        <br>
      </li>
  </section>
</body>