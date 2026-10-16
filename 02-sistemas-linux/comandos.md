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
</ul>

<div style="backgorund-color:red"><h2 id="sintaxis-basica">1. Sintaxis Básica</h2></div>
<p>La estructura general de los comandos en la interfaz de comandos (CLI) es:</p>

<img width="75%" alt="image42" src="https://github.com/user-attachments/assets/da0eb497-e09f-4901-a4ea-3ea0ca5d4184" /><br><br>


<ul>
  <li><strong>Opciones (-)</strong>: Modifican el comportamiento del comando.</li>
  <li><strong>Argumentos</strong>: Indican el elemento o valor sobre el que actúa el comando.</li><br><br>
</ul>

<h2 id="navegacion-y-directorios">2. Navegación y Directorios</h2>
<p><code>pwd</code>: Muestra la ruta absoluta del directorio actual de trabajo.</p>

<img width="75%" alt="image14" src="https://github.com/user-attachments/assets/799fc4d2-8227-4333-92c8-6b5e6a0379f9" /><br><br>

<p><code>cd &lt;ruta&gt;</code>: Cambia de directorio.</p>
<p><code>cd ~</code> o solo <code>cd</code>: Va al directorio personal (home) del usuario.</p>

<img width="75%" alt="image13" src="https://github.com/user-attachments/assets/10a86366-f682-4db7-bf47-9e0625d66508" /><br><br>

<p><code>cd /</code>: Va al directorio raíz (root general del sistema).</p>

<p><img width="75%" alt="Code_Generated_Image" src="https://github.com/user-attachments/assets/2c1faa26-c3e8-44a8-9e58-8bfbb70382bc" /></p><br><br>


<p><code>cd ..</code>: Sube un nivel en el directorio superior.</p>

<p><img width="75%" alt="Code_Generated_Image(1)" src="https://github.com/user-attachments/assets/bb83f0fc-47c7-4d23-b924-c014eee00c09" /></p><br><br>

<h2 id="listado-y-permisos">3. Listado y Permisos de Archivos</h2>
<p><code>ls</code>: Lista los archivos del directorio.</p>

<img width="75%" alt="image5" src="https://github.com/user-attachments/assets/61ea04fe-c277-415a-9bc9-1acc51b144b7" /><br><br>

<p><code>ls -l</code>: Muestra información detallada (permisos, propietario, tamaño, fecha).</p>

<img width="75%" alt="image23" src="https://github.com/user-attachments/assets/48fec1c0-63c1-4ffe-8667-3f73d8e27db3" /><br><br>

<p><code>ls -r</code>: Invierte el orden alfabético.</p>

<img width="75%" alt="image27" src="https://github.com/user-attachments/assets/28ee5984-f660-4551-b6c7-bfaa4f21e2fb" /><br><br>

<p><code>ls -t</code>: Ordena por sello de tiempo (última modificación).</p>

<img width="75%" alt="image15" src="https://github.com/user-attachments/assets/29c3d058-81d9-4795-afb9-166ea11bcf9b" /><br><br>

<p><code>ls -S</code>: Ordena por tamaño del archivo.</p>

<img width="75%" alt="image16" src="https://github.com/user-attachments/assets/669054c5-52c3-46ba-ae98-f8c3e9b93b78" /><br><br>

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
</ul>

<p>Cambiar permisos (<code>chmod</code>): Método simbólico</p>

<img width="75%" alt="image41" src="https://github.com/user-attachments/assets/cd6b2dc7-abaf-4fac-915f-81d75c06ae00" /><br><br>

<p>Cambiar propietario (<code>chown</code>): (Requiere <code>sudo</code>)</p>

<img width="75%" alt="image37" src="https://github.com/user-attachments/assets/2d32ee39-4e9a-4690-be22-be015845c351" /><br><br>

<h2 id="gestion-de-usuarios">4. Gestión de Usuarios y Accesos</h2>
<p><code>su [usuario]</code> / <code>su - [usuario]</code>: Cambia temporalmente de usuario (por defecto a root) creando una nueva shell. Usa <code>exit</code> para salir. Se recomienda utilizar la opción de inicio de sesión (<code>su -</code> o <code>su --login</code>) ya que configura completamente el entorno y las variables del nuevo usuario.</p>

<img width="75%" alt="image12" src="https://github.com/user-attachments/assets/626ed2f4-2b6e-4023-9f78-742eb0b189de" /><br><br>

<p><code>sudo &lt;comando&gt;</code>: Ejecuta un comando específico con privilegios administrativos sin cambiar de shell.</p>

<img width="75%" alt="image1" src="https://github.com/user-attachments/assets/6b22cf0b-7fac-46c8-9aaa-28395aeb7f5d" /><br><br>

<p><code>passwd</code>: Cambia la contraseña del usuario actual.</p>

<img width="75%" alt="image28" src="https://github.com/user-attachments/assets/91104156-2dd7-41ee-9f43-992fd5997d25" /><br><br>

<p><code>passwd -S &lt;usuario&gt;</code>: Muestra información detallada sobre el estado de la contraseña (estado, última actualización, días mínimos/máximos, avisos e inactividad).</p>

<img width="75%" alt="image10" src="https://github.com/user-attachments/assets/efa3bede-eaae-4c75-9db2-ce161c9a3c30" /><br><br>

<h2 id="manipulacion-de-archivos">5. Manipulación de Archivos</h2>

<h3>Visualización:</h3>
<p><code>cat &lt;archivo&gt;</code>: Muestra todo el contenido de un archivo pequeño.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="cat command output" /></p>

<p><code>head -n &lt;num&gt; &lt;archivo&gt;</code>: Muestra las primeras líneas.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="head command output" /></p>

<p><code>tail -n &lt;num&gt; &lt;archivo&gt;</code>: Muestra las últimas líneas.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="tail command output" /></p>

<h3>Copiar, Mover y Eliminar:</h3>
<p><code>cp &lt;origen&gt; &lt;destino&gt;</code>: Copia archivos o directorios.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="cp command output" /></p>

<p><code>mv &lt;origen&gt; &lt;destino&gt;</code>: Mueve o renombra archivos.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="mv command output" /></p>

<p><code>rm &lt;archivo&gt;</code>: Elimina un archivo ordinario.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="rm command output" /></p>

<p><code>rm -r &lt;directorio&gt;</code>: Elimina un directorio y su contenido de forma recursiva.</p>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="rm -r command output" /></p>

<h3>Duplicación de nivel de bits (<code>dd</code>):</h3>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABLAAAAA/CAYAAABwly98AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAS0SURBVHhe7d3Bchs1EIXhU8i/31m2M+04zSp1sWfSBUgw8P5g/m1z4I8E3n4//f71+z//AQIECBAgQIAAAQIECBAgQIBArcAnf/n9z09vv729pRsIECBAgAABAgQIECBAgAABAn9G4NvbL3/6+53we+RPdz92L0f0jvu3+/AECBAgQIAAAQIECBAgQIAAAQIERgEPfSOfGgECBAgQIECAAAECBAgQIECAAAEC5QLe4FbfgFf/eYEPP3z8zL+p///4/d2/33/fX/74zN+z/y8x/N//ffu+/e3vE97jP//z47E+/f4j97I2M3U33mO8x/PefY/e4z3+/s4j3E/vcfc1/66Pce89xvv6G8/fS+8x3vve4/x3C3yMff351/m/32v1/450AgQIECBAgAABAgQIECBAgACBB4Hv/v25J73BDa35eQ/e/f4oX9/34L3/9z7p3v1+BAgQIECAAAECBAgQIECAAIGPCnhjO2rl+n2BPx+6Ie37Lly/3f6e/3q/+/N9j8/f34D/9y/9z2O+3/d910N234Pvu3u+/dvn+/7y9j2M6J3+A6/x/O8fQ/X7mfrf9x/5vPte+/n723X/c9/rX33+p4/4Efcxrvf7e++X9x8JECBAgAABAgQIECBAgACBHxTwxvbBx2re/0fAG9vf4/Lp13j/5/u///S75R4CBAgQIECAAAECBAgQIECAAIF3CngDexf2yfe/4A3sw78E3f2e+sXo2Lvf98j/fP/zE9/f//ze8sXXq/fMef/m3//2mO/X39/f+3//9v0z5/vf39/X92++f74fAQIECBAgQIAAAQIECBAgQIDAhws8+g24v8fDvx313x341AgQIECAAAECBAgQIECAAAECBF4p0O8//vL74f07eAM7fB89/fHbf4/09s+/4f4E/7Mv+C/x/i8+R3A/vcfdV+49vcfd19ze/c33f/P3v9xL73H3NXqP3e/x/O8fx3s87/P3e+09xnuc3qf32N6zN7a75u9/+R/d39/p/v5e135LPEf3/vd3fwGf/u306d/3A/U3O/O9AAECBAgQIECAAAECBAgQIPD/L/D09j9/+v/A/7/A/yv8sA0ECBAgQIAAAQIECBAgQIAAgbMK/AMU2X9d4/aMuwAAAABJRU5ErkJggg==" alt="dd command example" /></p>

<h2 id="copias-de-seguridad">6. Copias de Seguridad y Duplicación de Bits (dd)</h2>
<p>El comando <code>dd</code> se utiliza para copiar datos no procesados (raw) a nivel de bits. Es muy potente y sirve para clonar discos, particiones o realizar copias de seguridad de sectores de arranque como el MBR.</p>

<p><strong>Argumentos principales:</strong></p>
<ul>
  <li><code>if=</code> : Archivo o dispositivo de entrada (Input File).</li>
  <li><code>of=</code> : Archivo o dispositivo de salida (Output File).</li>
  <li><code>bs=</code> : Tamaño de bloque (Block Size, ej: 1M para megabytes).</li>
  <li><code>count=</code> : Número de bloques que se van a leer.</li>
</ul>

<p><strong>Ejemplo práctico: Clonar un disco duro entero</strong></p>
<p>Para clonar un disco duro completo (<code>/dev/sda</code>) a otro (<code>/dev/sdb</code>) sin necesidad de especificar el tamaño de bloque:</p>
<pre><code>sudo dd if=/dev/sda of=/dev/sdb</code></pre>

<p><strong>Ejemplo práctico: Crear un archivo de intercambio (swap) o de tamaño específico lleno de ceros</strong></p>
<pre><code>sudo dd if=/dev/zero of=/tmp/swapex bs=1M count=50</code></pre>

<h2 id="filtros-y-grep">7. Filtros y Expresiones Regulares (grep)</h2>
<p>Busca patrones o líneas coincidentes en archivos.</p>

<ul>
  <li><code>grep 'palabra' archivo</code>: Búsqueda literal.</li>
  <li><code>grep '^patrón' archivo</code>: Coincide si el patrón está al inicio de la línea.</li>
  <li><code>grep 'patrón$' archivo</code>: Coincide si el patrón está al final de la línea.</li>
  <li><code>grep -E</code> o <code>egrep</code>: Activa expresiones regulares extendidas.</li>
</ul>

<h2 id="redes-y-sistema">8. Redes y Sistema</h2>
<ul>
  <li><code>shutdown &lt;hora&gt; ["mensaje"]</code>: Apaga el sistema de forma segura.</li>
  <li><code>date</code>: Muestra la fecha y hora del sistema.</li>
  <li><code>ifconfig</code>: Muestra la configuración de las interfaces de red.</li>
  <li><code>iwconfig</code>: Similar a <code>ifconfig</code>, pero enfocado específicamente a la configuración y estado de interfaces de red inalámbricas (wireless).</li>
  <li><code>ping -c &lt;num&gt; &lt;IP/dominio&gt;</code>: Comprueba la conectividad con un equipo.</li>
</ul>

<h2 id="procesos-y-paquetes">9. Procesos y Paquetes (apt)</h2>

<h3>Procesos:</h3>
<ul>
  <li><code>ps</code>: Muestra los procesos de la terminal actual.</li>
  <li><code>ps -e</code> o <code>ps -ef</code>: Muestra todos los procesos del sistema detalladamente.</li>
</ul>

<h3>Administrador de Paquetes (APT - Debian/Ubuntu):</h3>
<ul>
  <li><code>sudo apt-get update</code>: Actualiza la lista de paquetes disponibles.</li>
  <li><code>apt-cache search &lt;palabra&gt;</code>: Busca paquetes por palabra clave.</li>
  <li><code>sudo apt-get install &lt;paquete&gt;</code>: Instala o actualiza un paquete.</li>
  <li><code>sudo apt-get remove &lt;paquete&gt;</code>: Elimina un paquete (conserva configuraciones).</li>
  <li><code>sudo apt-get purge &lt;paquete&gt;</code>: Elimina un paquete por completo junto con sus configuraciones.</li>
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
