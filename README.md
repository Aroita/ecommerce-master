# ecommerce-master
Tec de comercio electrónico
Esta aplicación web se creó como un proyecto final para el curso Python organizado por la Fundación Adecco. Esta creado con Django de Python y Msql, no se utilizó ninguna plantilla.

Diseño
Se diseñó pensando en que ibamos a tocar todos los campos que habiamos aprendido durante el curso, y asi sido. La página de login.html y register.html constan de un usuario, email y contraseña.

La página index.html consta de una barra de navegación en la que veras el inicio, productos, fabricante y admi. Un carrusel, las categorias y los 10 productos mas actualizados.

La página del producto que enumera todos los productos en una tabla. Filtra por categorias y fabricante, tambien tiene el boton de añadir al carrito para que usuario cliente pueda si quiere comprarlo.

La página de categorías (vinculada a través de 'búsqueda' en la barra de navegación) permite al usuario filtrar productos por categoría.

La página de cart.html Importante el usuario cliente no puede editar ni borrar en ninguna página pero el usuario admi que también lo tenemos creado si que puedo hacerlo.

Relaciones
Usuario Admi ----- Cliente uno a uno

Cliente ---------- Carrito uno a muchos

Producto --------- Carrito muchos a muchos

Producto --------- Fabricante Muchos a muchos

Producto --------- Categoria muchos a uno

Programas a utilizar
Django

Mysql

Python 3.9

HTML 5

CSS 3

Javascript

Bootstrap 5.0.1

URL
urls.py a nivel de proyecto (ecommerce) proporciona los patrones de PATH rutas a las vistas, ya sea directamente:

desde django.contrib import admin

de la ruta de importación django.urls, incluir

urlpatterns = [ruta ('admin /', admin.site.urls), ruta ('', include ('app.urls')),]

Puntos de vista
Las vistas llamadas a través de PATH son funciones de Python que realizan las diferentes acciones necesarias para que el sitio web funcione, por ejemplo, renderizar una plantilla, iniciar sesión, cerrar sesión, etc.

Plantillas
La página base.html en la carpeta de plantillas de nivel superior es la plantilla base que se utiliza para todas las páginas e incluye todos los enlaces CSS / Bootstrap / Javascript, etc. y la barra de navegación y el pie de página totalmente receptivos que aparecen en todas las páginas del sitio web. También contiene:

{% block header%} {% endblock header%}

{% block content%} {% endblock content%}

{% block sidebar%} {% endblock%} Lo que permite insertar otras plantillas en esa sección (entre la barra de navegación y el pie de página). Vinculando el archivo base.html a las plantillas dentro de Apps, ejemplo a continuación:

{% extiende 'base.html'%}

{% block content%}

El código de la aplicación va aquí y aparecerá entre la barra de navegación y el pie de página de base.html

{% endblock content%} Aplicaciones Casa La aplicación de inicio muestra la plantilla index.html, que una vez llama a la plantilla base.html para presentar una página web completa con barra de navegación, contenido y pie de página.

Cuentas La aplicación de cuentas se utiliza para la autenticación completa del usuario. Cuando los usuarios visitan el sitio web por primera vez, tienen dos opciones en 'Mi cuenta': registrarse si no tienen una cuenta o iniciar sesión si la tienen. Una vez registrados / conectados, pueden ver su propio perfil que mostrar su nombre de usuario y la dirección de correo electrónico con la que solían registrarse. Las dos opciones en 'Mi cuenta cambiarán a Perfil o Cerrar sesión. Es posible que los usuarios se suscriban a una revista mensual; una vez que se hace clic, se llama a la función de suscripción dentro de views.py en la aplicación de cuentas que se conecta con los pagos de Stripe y si los detalles de la tarjeta se ingresan correctamente en el formulario, se realizar un pago mensual del usuario.

Productos / Categorías Estas aplicaciones muestran los productos que se han agregado a través del panel de administración de Django



Bases de datos / Archivos estáticos Cuando se ejecuta localmente, se utilizó la base de datos Mysql. El archivo settings.py se modificó para que la base de datos y los archivos estáticos apunten a los recursos en línea.
