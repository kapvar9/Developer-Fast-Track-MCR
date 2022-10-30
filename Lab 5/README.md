<h1>Laboratorio #5 - Operar aplicaciones nativas de la nube</h1>
<p>
  Hola, en este laboratorio aprenderemos a registrar, monitorear y analizar los registros de la infraestructura informática de OCI que se aprovisionaron en los laboratorios anteriores utilizando <b>Oracle Cloud Observability and Management Platform</b>.
</p>

<ul>
  <li>
    🌀<a href="https://www.oracle.com/es/manageability/">Página oficial de OCI Observability and Management Platform</a>   
  </li>
  <li>
    🧾<a href="https://docs.oracle.com/en-us/iaas/Content/Logging/Concepts/loggingoverview.htm">Documentación de OCI Logging</a>
  </li>
  <li>
    🧾<a href="https://docs.oracle.com/en-us/iaas/logging-analytics/index.html">Documentación de OCI Logging Analytics</a>
  </li>
</ul>
<h2>Recopilando información necesaria</h2>
<ul>
    <li>Acceder a tu cuenta de  <a href="https://www.oracle.com/cloud/sign-in.html">Oracle cloud &#127781;</a> y loggeate </li>
    <li>Ejecutar el lab#1</li>
</ul>
<h2>Paso 1: Activar el servicio de registro y habilitar la recopilación de registros</h2>
<ol>
  <li>
    En el menú 	&#127828; , ve a Observability & Management &#10145; Logging
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_34.png" alt="img34">
  </li>
  <br>
  <li>
    En el menú de <b>Logging</b>, selecciona <b>Logs</b>. Verifica que el compartimiento, sea el que creaste en el Lab#1
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_36.png" alt="img36">
  </li>
  <br>
  <li>
    En la sección de <b>Select Resource</b>, llena los campos con la siguiente información 👇:
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_37.png" alt="img37">
  </li>
  <br>
  <li>
    En la sección de <b>Configure Log</b>, selecciona la opción <b>Flow Logs - All Records</b> y especifica un nombre👇:
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_38.png" alt="img38">
  </li>
  <br>
  <li>
    Luego de llenar ambas secciones, clic en <b>Show Advanced options</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_39.png" alt="img39">
  </li>
  <br>
  <li>
    En la sección de <b>Log Location</b>, clic en <b>Create New Group</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_40.png" alt="img40">
  </li>
  <br>
  <li>
    Asigna un nombre al grupo y luego, clic en <b>Create</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_41.png" alt="img41">
  </li>
  <br>
  <li>
    Verifica que tu grupo creado esté seleccionado en <b>Log Group</b> y despúes, clic en <b>Enable Log</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_42.png" alt="img42">
  </li>
  <br>
  <li>
    Después de la activación (2-3 min), comienza la recopilación de registros (5-6 min). Para ver el dashboard, sigue esta ruta: Menú <b>Logging</b> &#10145; <b>Logs</b> &#10145;selecciona el log creado <b>Flowlogs-VCN</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_43.png" alt="img43">
  </li>
  <br>
  <li>
    Ahora visualizaremos el dashboard de recolección de logs de la VCN escogida. Ahora, clic en <b>Explore with Log Search</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_44.png" alt="img44">
  </li>
  <br>
  <li>
    Con <b>Search</b>, podrás modificar las búsquedas de tus logs
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_45.png" alt="img45">
  </li>
</ol>
<h2>Paso 2: Activar el servicio de Logging Analytics y crear un grupo para los logs</h2>
<ol>
  <li>En el menú 	&#127828; , sigue esta ruta: Observability & Management &#10145; Logging Analytics
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_46.png" alt="img46">
  </li>
  <br>
  <li>Clic en <b>Start Using Loggings Analytics</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_47.png" alt="img47">
  </li>
  <br>
  <li>Luego de la inicialización, clic en  <b>Take me to Log Explorer</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_48.png" alt="img48">
  </li>
  <br>
  <li>En <b>Log Explorer</b>, clic en <b>Administration</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_49.png" alt="img49">
  </li>
  <br>
  <li>En <b>Resources</b>, clic en  <b>Log Groups</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_50.png" alt="img50">
  </li>
  <br>
  <li>En <b>Log Groups</b>, clic en  <b>Create Log Group</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_51.png" alt="img51">
  </li>
  <br>
  <li>Asigna un nombre a tu grupo de Log y clic en  <b>Create</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_52.png" alt="img52">
  </li>
</ol>
<h2>Paso 3: Crear un Service Connectors para replicar los logs de Loggings para Logging Analytics</h2>
<ol>
  <li>En el menú 	&#127828; , sigue esta ruta: Observability & Management &#10145; Service Connectors
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_53.png" alt="img53">
  </li>
  <br>
  <li>Clic en <b>Create Service Connector</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_54.png" alt="img54">
  </li>
  <br>
  <li>Asigna un nombre para el conector. Puedes usar "LogVCNConnector"
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_55.png" alt="img55">
  </li>
  <br>
  <li>En <b>Configure Service Connector</b>, selecciona "Logging" como <b>Source</b> y "Logging Analytics" como <b>Target</b>. En <b>Configure source</b>, selecciona el log group y logs que creaste en el paso 1
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_56.png" alt="img56">
  </li>
  <br>
  <li>⚠️ <b>En este paso, es importante que sigas los pasos en orden </b>⚠️
    <br>
    En <b>Configure target connection</b>, selecciona el Log Group que creaste. Luego,clic en el <b>Create</b> de la esquina inferior derecha para crear las políticas de permiso de escritura para el conector. Por último, dale clic al otro botón de <b>Create</b>.
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_57.png" alt="img57">
  </li>
</ol>
<h2>Paso 4: Configure consultas personalizadas y cree un tablero</h2>
<ol>
  <li>En el menú 	&#127828; , sigue esta ruta: Observability & Management &#10145; Log explorer
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_58.png" alt="img58">
  </li>
  <br>
  <li>En la consola de <b>Log Explorer</b>, reemplace la consulta existente con la siguiente consulta para buscar las direcciones IP de origen que acceden a la VCN que configuramos y haga clic en el botón <b>Run</b>:
    <br>
    <br>
    <textarea name="textarea" rows="1" cols="100" disabled>
      'Log Source' = 'OCI VCN Flow Unified Schema Logs' | stats count as logrecords by 'Source IP'
    </textarea>
    <br>
    <img src="/Lab 5/images/Screenshot_59.png" alt="img59">
    <br>
    <br>
    <b>Resultado</b>👇
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_60.png" alt="img60">
  </li>
  <br>
  <li> Guardamos el resultado de la query para utilizarlo en la creación del dashboard. En <b>Actions</b>, clic en <b>Save</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_61.png" alt="img61">
  </li>
  <br>
  <li>Asigna un nombre en <b>Search Name</b> y por último, clic en <b>Save</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_62.png" alt="img62">
  </li>
  <br>
  <li>En este paso, crearemos otro gráfico. En la consola de <b>Log Explorer</b>, reemplaza la query existente con la de abajo y en <b>Visualizations</b> selecciona el gráfico de <i>Line</i>
    <br>
    <br>
    <textarea name="textarea" rows="1" cols="100" disabled>
      'Log Source' = 'OCI VCN Flow Unified Schema Logs' | timestats avg('Content Size Out') as 'Outbound Traffic'
    </textarea>
    <br>
    <img src="/Lab 5/images/Screenshot_63.png" alt="img63">
  </li>
  <br>
  <li> Repite los pasos 3 y 4 para guardar el resultado. Puedes asignarle el nombre <i>Tráfico de Salida</i>
  </li>
  <br>
  <li>En el menú de <b>Log Explorer</b>, selecciona <b>Dashboard</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_64.png" alt="img64">
  </li>
  <br>
  <li>Clic en <b>Create Dashboard</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_65.png" alt="img65">
  </li>
  <br>
  <li>En la consola de creación de Dashboard, ve a <b>Widgedts &#10145; Add Widgedts</b> , selecciona tu compartimiento y busca el gráfico <i>Ips de Entrada</i>. Haz clic sobre él y arrástralo a la zona de <b>Add a Filter</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_66.png" alt="img66">
  </li>
  <br>
  <li>Cuando se arrastre el widget, se le solicitará la creación de un filtro. Adicionaremos un nuevo filtro, seleccionaremos la opción <i>Log Group Compartment</i>. Por último, clic en <b>Save Changes</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_67.png" alt="img67">
  </li>
  <br>
  <li>Para la configuración de Entidad, seleccionamos <i>Add new "Entity" filter </i> y clic en <b>Save changes</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_68.png" alt="img68">
  </li>
  <br>
  <li>Para la configuración de Entidad, seleccionamos <i>Add new "Entity" filter </i> y clic en <b>Save changes</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_68.png" alt="img68">
    <br>
    <br>
    <b>Resultado</b>👇
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_69.png" alt="img69">
  </li>
  <br>
  <li>Agregamos el widget de <i>Tráfico de Salida</i>.Cuando se arrastre el widget, seleccionamos la opción <b>Link to Log Group Compartment input with an existing filter</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_70.png" alt="img70">
  </li>
  <br>
  <li>En la configuración de <i>Entity</i>, también seleccionamos la opción de <b>Link the Entity input with an existing filter</b>
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_71.png" alt="img71">
    <br>
    <br>
    <b>Resultado</b>👇
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_72.png" alt="img72">
  </li>
  <br>
  <li>Por último, cambiamos el nombre del Dashboard haciendo clic en el ✏️ y luego, clic en <b>Save Changes</b> para guardar los cambios
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_73.png" alt="img73">
    <br>
    <br>
    <b>Resultado</b>👇
    <br>
    <br>
    <img src="/Lab 5/images/Screenshot_74.png" alt="img74">
  </li>
</ol>
<h1>
  Felicitaciones!👏🏻 👏🏻 👏🏻  Creaste con éxito tu primer dashboard! 🚀🚀
</h1>
