Backlog Backend
===============

Programa de gestión de backlog de videojuegos que puede funcionar de manera pública, privada o semipública. Es decir,
puede permitir la apertura de cuentas al público, puede exigir login para acceder a cualquier URL del sitio o puede
permitir el acceso público para lectura pero que la creación de cuentas esté en manos del administrador (modo semipúblico).
Además de herramienta de backlog, pretende ser una base de datos de colección.

Funciones básicas
-----------------

El backlog básicamente permite almacenar una lista de fichas de juegos clasificadas por plataforma a las que se permiten
añadir algunos datos. Esto se separará en lo que llamaremos "Fichas" que sólo contendrán los datos objetivos del juego,
como su título, desarrolladora, plataformas, etiquetas, etc. Y otra que será la ficha de usuario, que contendrá las notas del
usuario sobre el juego (su calificación, si lo tiene, sus reseñas...).

Ficha del juego:

- Título
- Colección (si es parte de una).
- Año
- Plataformas
- Desarrolladora
- Miniatura (para mostrar en la búsqueda). Generalmente será la portada o el logo.
- Etiquetas. Aquí se puede poner lo que se quiera, sirve para más adelante buscar.
- Multimedia. Captura, audio o vídeo del juego.

Ficha de usuario:

- Estado actual (Sin empezar, sin terminar, terminado, completado). Terminado cuenta si has visto los créditos. Completado
es si lo has completado al 100% o (si el juego no tiene fin) consideras que ya has hecho todo lo que se puede hacer.
- Puntuación (de 1 a 5 estrellas).
- Versiones en posesión. Opcional, se puede dejar vacío si se quiere poner en la wishlist.
- Fotografías. Del juego físico.
- Notas. Unas notas rápidas del juego.
- Reseña. Un artículo completo del juego. Se compondrá de un título, un cuerpo de texto y un banner (opcional).
- Multimedia. Captura, audio o vídeo del juego.

El contenido multimedia es un tanto particular, 

Las plataformas tendrán su página de búsqueda. Básicamente se compone del nombre y un banner.

Además de esto, obviamente también está la gestión de backlog, que es lo principal. Cada ficha de usuario tendrá un historial de 
eventos, los que cada uno tendrá:

- Fecha
- Tipo. Puede ser compra, comienzo, finalización, completación, o comentario (el cual puede incluir contenido multimedia).
El contenido multimedia de las notas también se añadirá a la ficha del juego.
- Metadatos. Que variará según el tipo de evento.

Arquitectura
------------

Para permitir el uso tanto de interfaz web como de aplicación móvil (o integración con otras plataformas) la herramienta de
backlog seguirá una arquitectura REST, para la que luego se programarán clientes, entre ellos uno web y otro para Android.

Se puede encontrar una definición completa de la API en el directorio `doc`.
