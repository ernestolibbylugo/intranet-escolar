# Requerimientos de AulaConecta

## Descripción

**AulaConecta** es un prototipo de intranet escolar para gestionar usuarios,
calificaciones, asistencia y comunicados internos.

El sistema está dirigido a una institución educativa pública y utiliza
información completamente ficticia con fines académicos.

> Este proyecto utiliza `localStorage` y no debe almacenar información real o
> sensible de estudiantes, familias o personal educativo.

---

## Requerimientos funcionales

### Autenticación y autorización

- [ ] Permitir el inicio de sesión mediante correo y contraseña.
- [ ] Mantener la sesión mientras el usuario navega por el sistema.
- [ ] Permitir que el usuario cierre su sesión.
- [ ] Controlar el acceso según el rol.
- [ ] Redirigir los accesos no autorizados.

### Gestión de usuarios

- [ ] Mostrar la lista de usuarios.
- [ ] Crear usuarios.
- [ ] Editar usuarios existentes.
- [ ] Desactivar usuarios sin eliminar su información.
- [ ] Evitar la creación de correos duplicados.
- [ ] Asignar uno de los roles permitidos a cada usuario.

### Módulo de calificaciones

- [ ] Permitir que los docentes registren calificaciones.
- [ ] Permitir que los docentes editen calificaciones.
- [ ] Mostrar al estudiante únicamente sus calificaciones.
- [ ] Permitir que administración consulte las calificaciones registradas.
- [ ] Validar que las calificaciones estén dentro del rango permitido.

### Módulo de asistencia

- [ ] Permitir que los docentes registren la asistencia.
- [ ] Utilizar los estados presente, ausente y tardía.
- [ ] Mostrar al estudiante únicamente sus registros de asistencia.
- [ ] Permitir que administración consulte los registros.

### Tablón de comunicados

- [ ] Permitir que administración publique comunicados.
- [ ] Permitir que docentes publiquen comunicados.
- [ ] Definir los destinatarios de cada comunicado.
- [ ] Mostrar los comunicados correspondientes al rol del usuario.
- [ ] Ordenar los comunicados desde el más reciente.

### Consulta según el rol

| Función | Administración | Docente | Estudiante/familia |
|---|:---:|:---:|:---:|
| Gestionar usuarios | Sí | No | No |
| Registrar calificaciones | No | Sí | No |
| Consultar todas las calificaciones | Sí | No | No |
| Consultar calificaciones propias | No | No | Sí |
| Registrar asistencia | No | Sí | No |
| Consultar asistencia propia | No | No | Sí |
| Publicar comunicados | Sí | Sí | No |
| Consultar comunicados | Sí | Sí | Sí |

---

## Requerimientos no funcionales

### Accesibilidad

- [ ] Utilizar etiquetas asociadas con cada campo de formulario.
- [ ] Permitir la navegación mediante teclado.
- [ ] Mantener suficiente contraste entre texto y fondo.
- [ ] Mostrar mensajes de error comprensibles.
- [ ] Incluir texto alternativo en las imágenes informativas.
- [ ] Utilizar HTML semántico.

### Privacidad y seguridad

- [ ] Utilizar exclusivamente información ficticia.
- [ ] No mostrar información personal innecesaria.
- [ ] No incluir credenciales reales en el repositorio.
- [ ] Filtrar los registros mostrados según la sesión.
- [ ] Documentar las limitaciones de `localStorage`.

### Calidad técnica

- [ ] Separar la estructura, los estilos y la lógica.
- [ ] Utilizar nombres descriptivos en español.
- [ ] Evitar la repetición innecesaria de código.
- [ ] Versionar el proyecto con Git desde el inicio.
- [ ] Mantener documentación actualizada en Markdown.
- [ ] Comprobar el funcionamiento en diferentes tamaños de pantalla.

---

## Roles del sistema

### Administración

Gestiona los usuarios, consulta la información académica y publica comunicados
oficiales.

### Docente

Consulta estudiantes, registra calificaciones y asistencia, y publica
comunicados.

### Estudiante/familia

Consulta sus propias calificaciones, su asistencia y los comunicados que le
corresponden.

---

## Fuera del alcance inicial

Las siguientes funciones pueden desarrollarse después de completar los
requerimientos obligatorios:

- Calendario académico.
- Consulta de horarios.
- Descarga de materiales.
- Entrega de tareas.
- Reserva de aulas y recursos.
- Recuperación automática de contraseñas.
- Notificaciones por correo electrónico.

---

## Criterios de aceptación

El prototipo estará listo cuando:

1. Los tres roles puedan iniciar y cerrar sesión.
2. Cada rol tenga acceso únicamente a sus funciones.
3. Administración pueda gestionar usuarios.
4. Docentes puedan registrar calificaciones y asistencia.
5. Estudiantes puedan consultar únicamente sus propios registros.
6. Los comunicados se muestren según sus destinatarios.
7. Los datos se mantengan al recargar la página.
8. La documentación permita instalar, entender y probar el proyecto.