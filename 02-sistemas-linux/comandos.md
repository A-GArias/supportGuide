<h1>🐧 Hoja de Consulta Rápida: Linux Essentials</h1>
<p>Guía de referencia rápida con los comandos, sintaxis y ejemplos prácticos para la administración y navegación en sistemas Linux.</p>

<h2>📑 Tabla de Contenidos</h2>
<ul>
  <li><a href="#sintaxis-basica">Sintaxis Básica</a></li>
  <li><a href="#navegacion-y-directorios">Navegación y Directorios</a></li>
  <li><a href="#listado-y-permisos">Listado y Permisos de Archivos</a></li>
  <li><a href="#gestion-de-usuarios">Gestión de Usuarios y Accesos</a></li>
  <li><a href="#manipulacion-de-archivos">Manipulación de Archivos</a></li>
  <li><a href="#copias-de-seguridad">Copias de Seguridad y Duplicación de Bits (dd)</a></li>
  <li><a href="#filtros-y-grep">Filtros y Expresiones Regulares (Grep)</a></li>
  <li><a href="#redes-y-sistema">Redes y Sistema</a></li>
  <li><a href="#procesos-y-paquetes">Procesos y Paquetes (APT)</a></li>
  <li><a href="#editor-vim">Editor de Texto (Vim/Vi)</a></li>
</ul><br><br>


<h2 id="sintaxis-basica"><span style="background-color: #0969da;">1. Sintaxis Básica</h2>

<p>La estructura general de los comandos en la interfaz de comandos (CLI) es:</p>

<img width="100%" alt="image42" src="https://github.com/user-attachments/assets/da0eb497-e09f-4901-a4ea-3ea0ca5d4184" /><br><br>


<ul>
  <li><strong>Opciones (-)</strong>: Modifican el comportamiento del comando.</li>
  <li><strong>Argumentos</strong>: Indican el elemento o valor sobre el que actúa el comando.</li><br><br>
</ul>

<h2 id="navegacion-y-directorios">2. Navegación y Directorios</h2>
<p><code>pwd</code>: Muestra la ruta absoluta del directorio actual de trabajo.</p>

<img width="100%" alt="image14" src="https://github.com/user-attachments/assets/799fc4d2-8227-4333-92c8-6b5e6a0379f9" /><br><br>

<p><code>cd &lt;ruta&gt;</code>: Cambia de directorio.</p>
<p><code>cd ~</code> o solo <code>cd</code>: Va al directorio personal (home) del usuario.</p>

<img width="100%" alt="image13" src="https://github.com/user-attachments/assets/10a86366-f682-4db7-bf47-9e0625d66508" /><br><br>

<p><code>cd /</code>: Va al directorio raíz (root general del sistema).</p>

<p><img width="100%" alt="Code_Generated_Image" src="https://github.com/user-attachments/assets/2c1faa26-c3e8-44a8-9e58-8bfbb70382bc" /></p><br><br>

<p><code>cd ..</code>: Sube un nivel en el directorio superior.</p>

<p><img width="100%" alt="Code_Generated_Image(1)" src="https://github.com/user-attachments/assets/bb83f0fc-47c7-4d23-b924-c014eee00c09" /></p><br><br>

<h2 id="listado-y-permisos">3. Listado y Permisos de Archivos</h2>
<p><code>ls</code>: Lista los archivos del directorio.</p>

<img width="100%" alt="image5" src="https://github.com/user-attachments/assets/61ea04fe-c277-415a-9bc9-1acc51b144b7" /><br><br>

<p><code>ls -l</code>: Muestra información detallada (permisos, propietario, tamaño, fecha).</p>

<img width="100%" alt="image23" src="https://github.com/user-attachments/assets/48fec1c0-63c1-4ffe-8667-3f73d8e27db3" /><br><br>

<p><code>ls -r</code>: Invierte el orden alfabético.</p>

<img width="100%" alt="image27" src="https://github.com/user-attachments/assets/28ee5984-f660-4551-b6c7-bfaa4f21e2fb" /><br><br>

<p><code>ls -t</code>: Ordena por sello de tiempo (última modificación).</p>

<img width="100%" alt="image15" src="https://github.com/user-attachments/assets/29c3d058-81d9-4795-afb9-166ea11bcf9b" /><br><br>

<p><code>ls -S</code>: Ordena por tamaño del archivo.</p>

<img width="100%" alt="image16" src="https://github.com/user-attachments/assets/669054c5-52c3-46ba-ae98-f8c3e9b93b78" /><br><br>

<h3>🔒 Cómo leer los Permisos de los Archivos (<code>-rw-r--r--</code>)</h3>
<p>Cuando ejecutas <code>ls -l</code>, el primer campo muestra una cadena de 10 caracteres que define el tipo de archivo y sus permisos. Tomando como ejemplo <code>-rw-r--r--</code>:</p>

<p><strong>Primer carácter (<code>-</code>):</strong> Indica el tipo de archivo.</p>
<ul>
  <li><code>-</code> : Archivo ordinario.</li>
  <li><code>d</code> : Directorio.</li>
  <li><code>l</code> : Enlace simbólico.</li>
</ul>

<p><strong>Siguientes 9 caracteres</strong> (divididos en 3 bloques de 3):</p>
<ul>
  <li><strong>Primer bloque (<code>rw-</code>)</strong>: Permisos para el usuario propietario del archivo.</li>
  <li><strong>Segundo bloque (<code>r--</code>)</strong>: Permisos para el grupo propietario del archivo.</li>
  <li><strong>Tercer bloque (<code>r--</code>)</strong>: Permisos para todos los demás usuarios (others).</li>
</ul>

<p><strong>Significado de cada letra:</strong></p>
<ul>
  <li><code>r</code> (Read / Leer): Permite leer el contenido o listar el directorio.</li>
  <li><code>w</code> (Write / Escribir): Permite modificar el archivo o añadir/eliminar archivos en el directorio.</li>
  <li><code>x</code> (Execute / Ejecutar): Permite ejecutar el archivo como proceso o entrar en el directorio.</li>
  <li><code>-</code> : El permiso en esa posición está desactivado.</li>
</ul><br><br>

<p>Cambiar permisos (<code>chmod</code>): Método simbólico</p>

<img width="100%" alt="image41" src="https://github.com/user-attachments/assets/cd6b2dc7-abaf-4fac-915f-81d75c06ae00" /><br><br>

<p>Cambiar propietario (<code>chown</code>): (Requiere <code>sudo</code>)</p>

<img width="100%" alt="image37" src="https://github.com/user-attachments/assets/2d32ee39-4e9a-4690-be22-be015845c351" /><br><br>

<h2 id="gestion-de-usuarios">4. Gestión de Usuarios y Accesos</h2>
<p><code>su [usuario]</code> / <code>su - [usuario]</code>: Cambia temporalmente de usuario (por defecto a root) creando una nueva shell. Usa <code>exit</code> para salir. Se recomienda utilizar la opción de inicio de sesión (<code>su -</code> o <code>su --login</code>) ya que configura completamente el entorno y las variables del nuevo usuario.</p>

<img width="100%" alt="image12" src="https://github.com/user-attachments/assets/626ed2f4-2b6e-4023-9f78-742eb0b189de" /><br><br>

<p><code>sudo &lt;comando&gt;</code>: Ejecuta un comando específico con privilegios administrativos sin cambiar de shell.</p>

<img width="100%" alt="image1" src="https://github.com/user-attachments/assets/6b22cf0b-7fac-46c8-9aaa-28395aeb7f5d" /><br><br>

<p><code>passwd</code>: Cambia la contraseña del usuario actual.</p>

<img width="100%" alt="image28" src="https://github.com/user-attachments/assets/91104156-2dd7-41ee-9f43-992fd5997d25" /><br><br>

<p><code>passwd -S &lt;usuario&gt;</code>: Muestra información detallada sobre el estado de la contraseña (estado, última actualización, días mínimos/máximos, avisos e inactividad).</p>

<img width="100%" alt="image10" src="https://github.com/user-attachments/assets/efa3bede-eaae-4c75-9db2-ce161c9a3c30" /><br><br>

<h2 id="manipulacion-de-archivos">5. Manipulación de Archivos</h2>

<h3>Visualización:</h3>
<p><code>cat &lt;archivo&gt;</code>: Muestra todo el contenido de un archivo pequeño.</p>

<img width="100%" alt="image26" src="https://github.com/user-attachments/assets/47b15b88-caf2-4fa3-be57-5b4e02be86e4" /><br><br>

<p><code>head -n &lt;num&gt; &lt;archivo&gt;</code>: Muestra las primeras líneas.</p>

<img width="100%" alt="image32" src="https://github.com/user-attachments/assets/fd50b70d-2e95-4b98-89b5-f88966ddf823" /><br><br>

<p><code>tail -n &lt;num&gt; &lt;archivo&gt;</code>: Muestra las últimas líneas.</p>

<img width="100%" alt="image43" src="https://github.com/user-attachments/assets/46501ade-6e6b-41d7-a2c5-d581d091168a" /><br><br>

<h3>Copiar, Mover y Eliminar:</h3>
<p><code>cp &lt;origen&gt; &lt;destino&gt;</code>: Copia archivos o directorios.</p>

<img width="100%" alt="image22" src="https://github.com/user-attachments/assets/cdada529-4b73-4c9b-8446-903cb8a47928" /><br><br>

<p><code>mv &lt;origen&gt; &lt;destino&gt;</code>: Mueve o renombra archivos.</p>

<img width="100%" alt="image30" src="https://github.com/user-attachments/assets/6593069f-2634-404c-9aca-076531f605f9" /><br><br>

<p><code>rm &lt;archivo&gt;</code>: Elimina un archivo ordinario.</p>

<img width="100%" alt="image39" src="https://github.com/user-attachments/assets/1d01a47a-64bb-4d61-9eed-48eb3eb931cf" /><br><br>

<p><code>rm -r &lt;directorio&gt;</code>: Elimina un directorio y su contenido de forma recursiva.</p>

<img width="100%" alt="image35" src="https://github.com/user-attachments/assets/37de5a21-51be-498c-99bf-f76da60abf4c" /><br><br>

<h3>Duplicación de nivel de bits (<code>dd</code>):</h3>

<img width="100%" alt="image33" src="https://github.com/user-attachments/assets/0b5b8c4b-c746-4713-bca2-4eaf85e0b36b" /><br><br>

<h2 id="copias-de-seguridad">6. Copias de Seguridad y Duplicación de Bits (dd)</h2>
<p>El comando <code>dd</code> se utiliza para copiar datos no procesados (raw) a nivel de bits. Es muy potente y sirve para clonar discos, particiones o realizar copias de seguridad de sectores de arranque como el MBR.</p>

<img width="100%" alt="image11" src="https://github.com/user-attachments/assets/c8758b43-996b-45ea-95e1-dfef34cd2d09" /><br><br>


<p><strong>Argumentos principales:</strong></p>
<ul>
  <li><code>if=</code> : Archivo o dispositivo de entrada (Input File).</li>
  <li><code>of=</code> : Archivo o dispositivo de salida (Output File).</li>
  <li><code>bs=</code> : Tamaño de bloque (Block Size, ej: 1M para megabytes).</li>
  <li><code>count=</code> : Número de bloques que se van a leer.</li>
</ul>

<p><strong>Ejemplo práctico: Clonar un disco duro entero</strong></p>
<p>Para clonar un disco duro completo (<code>/dev/sda</code>) a otro (<code>/dev/sdb</code>) sin necesidad de especificar el tamaño de bloque:</p>


<img width="100%" alt="image9" src="https://github.com/user-attachments/assets/289de499-b3a2-4f7a-8ded-3e99cfacca77" /><br><br>


<p><strong>Ejemplo práctico: Crear un archivo de intercambio (swap) o de tamaño específico lleno de ceros</strong></p>


<img width="100%" alt="image40" src="https://github.com/user-attachments/assets/1a72e2f2-1119-45ba-bef8-b3601eb13163" /><br><br>


<h2 id="filtros-y-grep">7. Filtros y Expresiones Regulares (grep)</h2>
<p>Busca patrones o líneas coincidentes en archivos.</p>
<img width="100%"  alt="image25" src="https://github.com/user-attachments/assets/1a125511-7fce-4963-8cd6-05e16fb66304" /><br><br>

<ul>
  <li><code>grep 'palabra' archivo</code>: Búsqueda literal.</li><br>
  <img width="100%"  alt="image31" src="https://github.com/user-attachments/assets/cf7f7e9b-94a8-4054-8772-fdb521ffb798" /><br><br>

  <li><code>grep '^patrón' archivo</code>: Coincide si el patrón está al inicio de la línea.</li><br>
  <img width="100%"  alt="image19" src="https://github.com/user-attachments/assets/7950b8fc-2134-4b1b-83bc-ff8fe6dbd2e0" /><br><br>

  <li><code>grep 'patrón$' archivo</code>: Coincide si el patrón está al final de la línea.</li><br>
  <img width="100%" alt="image44" src="https://github.com/user-attachments/assets/03bcf36d-a614-4834-983f-478bfab0638a" /><br><br>

  <li><code>grep -E</code> o <code>egrep</code>: Activa expresiones regulares extendidas.</li><br>
  <img width="100%" alt="image44" alt="image29" src="https://github.com/user-attachments/assets/fba757f8-929b-43a1-8ec9-88162e575f13" /><br><br>

</ul>

<h2 id="redes-y-sistema">8. Redes y Sistema</h2>
<ul>
  <li><code>shutdown &lt;hora&gt; ["mensaje"]</code>: Apaga el sistema de forma segura.</li><br>
  <img width="100%" alt="image36" src="https://github.com/user-attachments/assets/19254667-596e-4e52-8f87-890fa0e9ae0e" /><br><br>

  <li><code>date</code>: Muestra la fecha y hora del sistema.</li><br>
  <img width="100%" alt="image18" src="https://github.com/user-attachments/assets/bb00ff1a-809c-421a-8fa1-6db1e16f305e" /><br><br>

  
  <li><code>ifconfig</code>: Muestra la configuración de las interfaces de red.</li><br>
  <img width="100%" alt="image7" src="https://github.com/user-attachments/assets/3d88da29-e7b6-4b4c-8d47-1a42e2f524c1" /><br><br>

  
  <li><code>iwconfig</code>: Similar a <code>ifconfig</code>, pero enfocado específicamente a la configuración y estado de interfaces de red inalámbricas (wireless).</li><br>
  <img width="100%" alt="image8" src="https://github.com/user-attachments/assets/07fe87e3-8be0-4310-9f7f-14c7c9d333dc" /><br><br>

  
  <li><code>ping -c &lt;num&gt; &lt;IP/dominio&gt;</code>: Comprueba la conectividad con un equipo.</li><br>
  <img width="100%" alt="image2" src="https://github.com/user-attachments/assets/37035e48-ea74-4fe7-af55-e2e9a3903af6" /><br><br>

  
</ul>

<h2 id="procesos-y-paquetes">9. Procesos y Paquetes (apt)</h2>

<h3>Procesos:</h3>
<ul>
  <li><code>ps</code>: Muestra los procesos de la terminal actual.</li><br>
<img width="100%" alt="image34" src="https://github.com/user-attachments/assets/cb42c41d-2088-4cc1-8d09-175dc3415d9e" /><br><br>

  <li><code>ps -e</code> o <code>ps -ef</code>: Muestra todos los procesos del sistema detalladamente.</li><br>
<img width="100%" alt="image20" src="https://github.com/user-attachments/assets/7076c6c9-3d60-41ae-9cf8-b6fabe18909d" /><br><br>

  
</ul>

<h3>Administrador de Paquetes (APT - Debian/Ubuntu):</h3>
<ul>
  <li><code>sudo apt-get update</code>: Actualiza la lista de paquetes disponibles.</li><br>
  <img width="100%" alt="image3" src="https://github.com/user-attachments/assets/af7f996a-6b3a-44c9-9f99-765c75131594" /><br><br>

  <li><code>apt-cache search &lt;palabra&gt;</code>: Busca paquetes por palabra clave.</li><br>
  <img width="100%" alt="image17" src="https://github.com/user-attachments/assets/104226a3-117d-4404-bf05-38cdd53d9962" /><br><br>

  <li><code>sudo apt-get install &lt;paquete&gt;</code>: Instala o actualiza un paquete.</li><br>
  <img width="100%" alt="image24" src="https://github.com/user-attachments/assets/e324fb6f-412f-48f8-beb6-6276677432ff" /><br><br>

  <li><code>sudo apt-get remove &lt;paquete&gt;</code>: Elimina un paquete (conserva configuraciones).</li><br>
  <img width="100%" alt="image4" src="https://github.com/user-attachments/assets/b25cb81a-1874-49f0-8e58-8420de85d7ef" /><br><br>

  <li><code>sudo apt-get purge &lt;paquete&gt;</code>: Elimina un paquete por completo junto con sus configuraciones.</li><br>
  <img width="100%" alt="image6" src="https://github.com/user-attachments/assets/518f2678-36a9-4dd7-ae4f-d3de6fed263a" /><br><br>

</ul>

<h2 id="editor-vim">10. Editor de Texto (vim / vi)</h2>
<p>Para abrir o crear un archivo: <code>vi &lt;archivo&gt;</code>. Cuenta con tres modos principales:</p>

<h3>🔀 Modos y Comandos Rápidos</h3>

<p><strong>Modo Comando:</strong> Se usa para moverse y preparar acciones. Presiona <code>Esc</code> para volver a este modo.</p>
<ul>
  <li><strong>Movimientos:</strong> <code>h</code> (izq), <code>j</code> (abajo), <code>k</code> (arriba), <code>l</code> (der), <code>gg</code> (inicio), <code>G</code> (final).</li>
  <li><strong>Acciones básicas:</strong>
    <ul>
      <li><code>dd</code>: Elimina la línea actual.</li>
      <li><code>yy</code>: Copia (yank) la línea actual.</li>
      <li><code>p</code> / <code>P</code>: Pega después o antes del cursor.</li>
      <li><code>/patrón</code>: Busca texto hacia adelante (pulsa <code>n</code> para siguiente).</li>
    </ul>
  </li>
</ul>

<p><strong>Modo Insertar:</strong> Para escribir texto libremente. Se entra con:</p>
<ul>
  <li><code>i</code>: Inserta antes del cursor.</li>
  <li><code>a</code>: Inserta después del cursor.</li>
  <li><code>o</code>: Abre una nueva línea debajo.</li>
</ul>

<p><strong>Modo Ex:</strong> Se accede pulsando <code>:</code> desde el modo comando.</p>
<ul>
  <li><code>:w</code>: Guarda los cambios.</li>
  <li><code>:wq</code> o <code>ZZ</code>: Guarda y sale.</li>
  <li><code>:q!</code>: Sale sin guardar los cambios.</li>
</ul>
