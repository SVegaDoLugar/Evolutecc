# Evolutecc

Para mayor legibilidad de este archivo, seleccione la ocpion <> "DISPLAY THE SOURCE BLOB" ubicada en el menu superior.

------------------------------------------------------------------------------------------------------
PASO 1: CONFIGURACION DE ENTORNO DE DESARROLLO - EN CASO DE NO TENER CONFIGURADO PHP, MYSQL y composer
  1.1. INSTALACION DE XAMPP - permite el uso de PHP (1), MySQL (2) y simulacion de servidor web (3) -
      1. Ingrese a la página https://www.apachefriends.org
      2. Seleccione la opcion de descarga "XAMPP para Windows (en este caso, mostrara PHP en su version 8.1.6).
      3. Se descargará un archivo de instalación (extension .exe). Presionaremos clic derecho sobre el archivo y seleccionaremos la opcion EJECUTAR COMO ADMINISTRADOR.
      4. Permitimos que la aplicación realice cambios en el dispositivo.
      5. Aparecera una advertencia en caso de que tengamos un antivirus activado, este ralentizara la instalacion. Seleccionamos la opcion YES.
      6. Aparecera otra advertencia, indicando que si nuestro sistema no tiene activado el UAC (User Account Control), algunas funcionalidades de Xampp no estarán disponibles. Presionamos el boton OK.
      7. Luego, seleccionaremos los componentes a instalar:
        7.1. Server: Apache, MySQL, Mercury Mail Server.
        7.2. Program Languages: PHP, Perl.
        7.3. Program Languages: phpMyAdmin, Webalizer, Fake Sendmail.
      8. Despues, seleccionaremos la carpeta donde se instalará Xampp - se recomienda dejar la ruta por defecto 'C:\xampp' - y presionamos "NEXT>".
      9. Posteriormente, seleccionaremos el idioma de la aplicacion - recomendable en Ingles / English - y presionamos "NEXT>".
      10. Aparecerá un cuadro indicando que Xampp posee instaladores que pueden instalar otros recursos como Wordpress. Presionamos "NEXT>".
      11. Al aparecer en el menú superior el titulo "Ready to Install" es posible seguir con la instalacion. Presionamos "NEXT>" para instalar xampp. Este proceso puede tardar varios minutos.
      12. Al terminar la instalacion desmarcaremos la opcion "Do you want to start the Control Panel now?" - previniendo la apertura de la aplicacion -; finalmente presionamos "FINISH".
      13. IMPORTANTE: La aplicacion a ejecutar para el uso de PHP y simulacion del servidor tiene como nombre " xampp-control.exe ", y SIEMPRE DEBERÁ EJECUTARSE COMO ADMINISTRADOR -presionando clic derecho y seleccionando la opcion. - La ruta de este archivo es " C:\xampp\xampp-control.exe ".
      
  1.2. INSTALACION DE COMPOSER - permite la instalacion y gestion de paquetes para programar en PHP -
      1. Ingresamos a la pagina web " https://getcomposer.org/download/ " y buscamos el archivo de descarga " Composer-Setup.exe ".
      2. Una vez descargado el archivo de instalacion, lo abrimos y seleccionamos la opcion "Install for all users (recommended)" para instalar composer en todos los usuarios de nuestro ordenador.
      3. Luego, desmarcamos la opcion "Developer mode" ya que no utilizaremos composer en el modo de desarrollo y presionamos "NEXT>".
      4. Posteriormente, nos motrará la ruta del archivo de " php.exe " que utilizaremos; en nuestro caso " C:\xampp\php\php.exe ". En caso de que tengas una ruta diferente de tu archivo php, reemplázala. Presionamos "NEXT>".
      5. IMPORTANTE, que nuestra version de PHP sea igual o superior a 7.3, ya que es uno de los requisitos de instalacion de DRUPAL.
      6. Nos aparecerá una opcion "Use a proxy server to connect to internet", la dejamos desmarcada. Presionamos "NEXT>".
      7. Al aparecer en el menú superior el titulo "Ready to Install", verificamos todas las configuraciones de instalacion. Presionamos "INSTALL".
      8. Presionamos "NEXT>" al terminar la instalacion y finalmente, presionamos "FINISH".
      
  1.3. CONFIGURACION DE VARIABLES DE ENTORNO PARA PHP Y COMPOSER
      1. Para poder utilizar composer y PHP en nuestro equipo, deberemos configurar las variables de entorno, para ello nos dirigiremos a la barra de busqueda de nuestro ordenador y escribimos "SISTEMA", posteriormente ingresamos a dicha aplicacion.
      2. Seleccionaremos la opcion " Configuracion avanzada del sistema " y posteriormente se abrirá una ventana, en la que seleccionaremos la opcion "Variables de entorno".
      3. Luego en el nuevo recuadro abierto, nos ubicamos en el titulo " Variables del sistema " en la parte inferior y buscamos la opcion " PATH ", a la cual le haremos doble clic.
      4. Al seleccionar dicha opcion, nos mostrará en un listado todas las variables de entorno y, en caso de no estar registrado composer o PHP las agregaremos.
      5. Para agregar PHP, nos dirigimos a la pestaña " Nuevo " y alli escribiremos la ruta de nuestro archivo "php.exe", en este caso " C:\xampp\php\php.exe " y presionamos aceptar.
      6. Para agregar composer, de nuevo, nos dirigimos a la pestaña " Nuevo " y escribimos la ruta de composer, en nuestro caso " C:\ProgramData\ComposerSetup\bin " y presionamos aceptar.
      7. Luego de agregar nuestras dos nuevas variables de entorno, tendremos que reiniciar nuestro computador.
      8. Finalmente, al reiniciar nuestro computador, podremos abrir nuestra linea de comandos y ejecutar " composer -v " para verificar la version de composer; igualmente para PHP, ejecutando el comando " php -v ".
      
-------------------------------------------------------------------------------------
PASO 2: INSTALACION DE DRUPAL - IMPORTANTE, TENER UNA VERSION DE PHP SUPERIOR A 7.3 -
      1. Previo a la instalacion de DRUPAL crearemos la carpeta donde estara nuestro proyecto de DRUPAL, la podemos crear donde deseemos, ya sea el disco local C o cualquier otro. En nuestro caso, la ruta del proyecto sera " D:\DevProjects\option_1".
      2. Ingresamos a la linea de comandos Windows Power Shell, presionando clic derecho sobre el icono y seleccionando la opcion EJECUTAR COMO ADMINISTRADOR.
      3. Posteriormente, ingresamos a la carpeta de nuestro proyecto (" D:\DevProjects\option_1 " en nuestro caso) y ejecutamos el comando " composer update --ignore-platform-reqs ", para ignorar temporalmente las extensiones requeridas por DRUPAL.
      4. Finalizada la configuracion, escribimos el comando " composer create-project drupal/recommended-project ./" , lo cual permitira crear el proyecto desde composer en la carpeta donde estamos.
      5. IMPORTANTE. EL PROCESO ES DEMORADO, SE DEBERA TENER UN POCO DE PACIENCIA.
      6. Finalizado el proceso, deberemos hacer otra configuracion para que en el siguiente paso no se presenten posibles errores:
          6.1. Buscamos el archivo " php.ini " en la carpeta donde se encuentra instalado php, en nuestro caso " C:\xampp\php ".
          6.2. Los comentarios en este tipo de archivos están hechos con un punto y coma ( ; ). Deberemos configurar dos lineas para que no queden comentadas y se puedan ejecutar.
          6.3. Descomentaremos la linea con el texto " extensions = gd " (1) - linea 920 aproximadamente - y la linea con el texto " zend_extension=opcache " - linea 953 aproximadamente -.

---------------------------------------------------------------
PASO 3: CREACION DE NUESTRA BASE DE DATOS, A EMPLEAR POR DRUPAL
    1. Inicializamos xampp, tal como se dijo anteriormente, ejecutando como administrador.
    2. Automaticamente, los modulos de Apache (1) y MySQL (2) estaran ejecutandose.
    3. En nuestro navegador, ingresaremos a la ruta " http://localhost/dashboard/ " y seleccionaremos la opcion del menu superior " phpMyAdmin ".
    4. Una vez dentro de phpMyAdmin, crearemos una nueva base de datos con el nombre " option_1 ", seleccionando la opcion de la barra izquierda " Nueva ". Luego ingresaremos el nombre de la base de datos y haremos clic en " CREAR ".

--------------------------------------------------------------------------------------
PASO 4: INSTALACION DEL LIVE SERVER Y CONFIGURACION DE USO DE PHP EN VISUALSTUDIO CODE
    1. Para poder arrancar el servidor web, es necesario instalar extensiones en nuestro editor de codigo. Para ello, lo abrimos y nos ubicaremos en el menu de la izquierda, seleccionando la opcion " Extensions " e instalaremos 3 extensiones:
        1.1. PHP Debug.
        1.2. PHP Intelephense.
        1.3. PHP Server.
            1.3.1. Al instalar esta extension, entraremos a configurarla, modificando la ruta de nuestro archivo php.exe, la cual es " C:/xampp/php/php.exe ".
            1.3.2. Luego, verificamos el numero del puerto, por defecto es 3000.

-------------------------------------------
PASO 5: CONFIGURACION DE DRUPAL PARA SU USO
    1. Con nuestros servidores Apache y MySQL andando, abriremos la carpeta de nuestro proyecto desde nuestro editor de codigo (VisualStudio CODE en nuestro caso).
    2. Posteriormente, nos ubicaremos en el archivo " index.php ", ubicado dentro de la carpeta " web " de nuestro proyecto.
    3. Allí, presionaremos clic derecho y seleccionaremos la opcion " PHP Server: Serve Project " para abrir el servidor.
    4. Luego se abrira nuestro navegador con la configuracion de DRUPAL.
        4.1. Seleccionaremos el idioma " Español " y posteriormente presionaremos " Save and continue ".
            4.1.2 En caso de que en el siguiente paso aparezca el error " INTERNET The translation server is offline", seguiremos los pasos brindados por Escuela Drupal en el siguiente video en el minuto 6:00 : https://www.youtube.com/watch?v=BCXwMMH1lrY&list=PLpaFxIy5rsiO1Zj9f1pnTH2YDKWvfj1nq&index=2 
        4.2. Seleccionamos como perfil de instalacion " Estandar ".
        4.3. Luego, seleccionaremos las opciones de la base de datos.
            4.3.1. Base de datos: " option_1 ".
            4.3.2. Nombre de usuario: " root ".
            4.3.3. Contraseña: - DEJAMOS ESTE CAMPO VACIO -
            4.3.4. Presionamos continuar.
        4.4. Luego, en la configuracion del sitio:
            4.4.1. Nombre del sitio: " Prueba EvolutecC "
            4.4.2. Nombre de usuario: " samuel "
            4.4.3. Contrasena: " 123 "
            4.4.4. Direccion de correo electronico: " svegadolugar@hotmail.com "
            4.4.5. Opciones regionales: País predeterminado - " Colombia ", Zona horaria predefinida - " Bogota "
            4.4.6. Desmarcamos la opcion " Recibir notificaciones por correo electronico "

----------------------------------------
PASO 6: MODIFICACION DE LA PAGINA DRUPAL
    1. Una vez cargado el proyecto de DRUPAL, nos dirigimos a la barra de navegacion superior y seleccionamos la opcion " Ampliar >> Filtro >> Buscar extensiones " y alli buscamos las extensiones " media " y " media library " para permitir el uso de contenido multimedia.
    2. Una vez instalados, nos dirigimos a nuestra carpeta del proyecto en la linea de comandos, y ejecutamos el comando " composer require drupal/admin_toolbar ".
    3. Si buscamos luego en la pagina de DRUPAL el nombre del modulo  en la seccion " Administrar >> Filtro ", apareceran 4 opciones de Admin Toolbar, las cuales seleccionaremos y posteriormente le daremos clic a " Instalar ".

-----------------------------------------------------------------------------
PASO 7: INSTALACION DE BOOSTRAP - https://www.drupal.org/project/bootstrap5 -
    1. Ingresamos a nuestra linea de comandos, y nos ubicamos en la carpeta " web\themes " y alli ejecutamos el comando " composer require 'drupal/bootstrap5:^2.0' ".
    2. Se nos preguntara si deseamos usar el archivo .json que esta en otra ubicacion, presionamos " Y " y luego enter.
    3. Luego iremos a nuestra pagina de DRUPAL en la seccion de " Apariencia "y nos aparecera la opcion de "Bootstrap5 2.0.0"; alli, seleccionamos la opcion de " INSTALAR ".
    4. Una vez instalado, nos dirigiremos a la opcion de configuracion, y dentro de ella, nos dirigimos a la zona inferior al apartado de " Subtheme ", que sera nuestro subtema utilizado por DRUPAL.
        4.1. Subtheme location: themes/custom - recomendable -.
        4.2. Subtheme name: " B5subtheme" - sin espacios -.
        4.3. Subtheme machine name: "b5ssubtheme" - sin espacios -.
    5. Finalmente, seleccionamos la opcion de " CREAR ".
    6. Luego, iremos nuevamente a nuestra barra de navegacion >> Apariencia y buscaremos el subtema creado "B5subtheme" y seleccionamos la opcion " Instalar y seleccionar de modo predeterminado ".
    7. Luego, dentro de ese subtema seleccionado, ingresamos a su configuracion y aplicamos los estilos de bootstrap que deseamos, donde incluso podremos cambiar el Favicon de la pagina. Luego de tener todas las configuraciones deseadas, presionamos el boton " Guardar configuracion ".
    8. De esta forma, se importaran todos los archivos CSS y JS para el correcto funcionamiento de Bootstrap 5.

---------------------------------------------------------
PASO 8: CREACION DE NUESTRA PRIMERA PAGINA " HOLA MUNDO "
    1. En el menu superior de DRUPAL, seleccionamos la opcion " Contenido >> Añadir contenido >> Pagina basica " para crear nuestra pagina principal.
    2. Luego seleccionamos un titulo para la página.
    3. Si deseamos utilizar BOOTSTRAP, es necesario cambiar a la opcion " Fuente HTML " y en " Formato de texto " seleccionar la opcion " HTML COMPLETO ", permitiendo asi modificacion de las etiquetas HTML, agregando clases y atributos propios de bootstrap.
    4. Luego, dejamos marcada la opcion de " Published " y presionamos la opcion " Guardar ".
    5. Finalmente, para modificar nuestra nueva pagina como pagina principal del proyecto, nos dirigiremos al menu superior " Configuracion >> Sistema >> Configuraciones basicas del sitio " y en la opcion " Pagina inicial predeterminada ", pegamos la ruta de nuestra pagina, siendo en nuestro caso "/node/1 y presionamos el boton de " Guardar configuracion ".
    
