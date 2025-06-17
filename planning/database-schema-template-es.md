# Esquema de Base de Datos - A MI RITMO

---

## Diagrama ER

```mermaid
erDiagram
  USUARIO {
    int id
    string nombre
    string correo
    string password
    string tipo_usuario
    string foto_perfil
  }
  RUTINA {
    int id
    string titulo
    string descripcion
    int creador_id
    int duracion
    string nivel
    string categoria
    string multimedia_url
    datetime fecha_creacion
  }
  COMENTARIO {
    int id
    int usuario_id
    int rutina_id
    string texto
    datetime fecha
  }
  VALORACION {
    int id
    int usuario_id
    int rutina_id
    int puntuacion
    string comentario
    datetime fecha
  }
  SEGUIDOR {
    int id
    int usuario_id
    int seguido_id
  }
  MENSAJE {
    int id
    int remitente_id
    int destinatario_id
    string texto
    datetime fecha
  }
  CONTENIDO_EXPERTO {
    int id
    string titulo
    string tipo
    string url
    string descripcion
    datetime fecha_publicacion
  }
  GRUPO {
    int id
    string nombre
    string descripcion
    datetime fecha_creacion
  }
  USUARIO ||--o{ RUTINA : crea
  USUARIO ||--o{ COMENTARIO : escribe
  USUARIO ||--o{ VALORACION : valora
  USUARIO ||--o{ SEGUIDOR : sigue
  USUARIO ||--o{ MENSAJE : envia
  USUARIO ||--o{ MENSAJE : recibe
  RUTINA ||--o{ COMENTARIO : recibe
  RUTINA ||--o{ VALORACION : recibe
  USUARIO ||--o{ GRUPO : pertenece
  GRUPO ||--o{ USUARIO : tiene
```
<small>Diagrama generado según las historias de usuario y requisitos del proyecto.</small>

---

## Descripción

El sistema "A MI RITMO" se basa en usuarios que pueden crear, buscar y compartir rutinas de ejercicio. Cada rutina puede recibir comentarios y valoraciones de otros usuarios. Los usuarios pueden seguirse entre sí, enviar mensajes privados y formar grupos temáticos. Además, existe una sección de contenido de expertos en fitness. Las entidades principales son USUARIO, RUTINA, COMENTARIO, VALORACION, SEGUIDOR, MENSAJE, CONTENIDO_EXPERTO y GRUPO. Las relaciones permiten la interacción social, la personalización y el acceso a contenido relevante, alineándose con los objetivos del proyecto y las historias de usuario.

<small>Descripción generada según las historias de usuario y requisitos del proyecto.</small>

---

<small>Agrega más entidades y relaciones a medida que tu proyecto crezca.</small>
