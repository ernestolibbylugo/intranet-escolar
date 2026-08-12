# Arquitectura de AulaConecta

## Descripción general

AulaConecta es una aplicación web de múltiples páginas desarrollada como
prototipo académico. Su propósito es simular la gestión interna de una
institución educativa.

La aplicación se ejecuta completamente en el navegador y no necesita un
servidor ni una base de datos externa.

> La arquitectura fue elegida para practicar los fundamentos de HTML, CSS,
> JavaScript, Git y Markdown sin introducir un framework o backend.

---

## Tecnologías

| Tecnología | Uso |
|---|---|
| HTML5 | Estructura semántica de las páginas |
| CSS3 | Diseño, accesibilidad y adaptación a pantallas |
| JavaScript | Lógica, validaciones, eventos y manipulación del DOM |
| `localStorage` | Persistencia local de los datos ficticios |
| Git | Control de versiones |
| GitHub | Alojamiento del repositorio y pull requests |
| GitButler | Administración visual de ramas y commits |
| Markdown | Documentación técnica del proyecto |

---

## Modelo de arquitectura

El sistema utiliza una arquitectura sencilla dividida en tres capas:

1. **Presentación:** páginas HTML y estilos CSS.
2. **Lógica:** módulos JavaScript que procesan eventos y reglas.
3. **Datos:** objetos y arreglos almacenados mediante `localStorage`.

```text
Usuario
  ↓
Interfaz HTML y CSS
  ↓
Lógica de JavaScript
  ↓
localStorage del navegador
```

### Capa de presentación

Contiene las páginas visibles, los formularios, las tablas, los botones y los
mensajes del sistema.

### Capa lógica

Contiene las funciones responsables de:

- Validar formularios.
- Iniciar y cerrar sesiones.
- Aplicar permisos por rol.
- Crear, consultar y editar registros.
- Filtrar la información mostrada.
- Actualizar el contenido de las páginas.

### Capa de datos

Almacena temporalmente la información ficticia utilizada por el prototipo.

Para guardar un objeto o arreglo:

```javascript
localStorage.setItem("clave", JSON.stringify(datos));
```

Para recuperar la información:

```javascript
const datos = JSON.parse(localStorage.getItem("clave")) || [];
```

---

## Organización del proyecto

```text
intranet-escolar/
├── assets/
│   └── images/
├── css/
│   └── global.css
├── docs/
│   ├── arquitectura.md
│   └── requerimientos.md
├── js/
│   ├── almacenamiento.js
│   └── datos-iniciales.js
├── .gitignore
├── AGENTS.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── index.html
├── LICENSE
└── README.md
```

Durante el desarrollo se agregarán páginas y módulos nuevos sin cambiar la
separación principal de responsabilidades.

---

## Claves de almacenamiento

| Clave | Contenido |
|---|---|
| `aulaconecta_usuarios` | Usuarios ficticios registrados |
| `aulaconecta_sesion` | Información de la sesión activa |
| `aulaconecta_materias` | Materias disponibles |
| `aulaconecta_calificaciones` | Calificaciones registradas |
| `aulaconecta_asistencias` | Registros de asistencia |
| `aulaconecta_comunicados` | Comunicados publicados |
| `aulaconecta_inicializada` | Estado de inicialización del prototipo |

Se utiliza el prefijo `aulaconecta_` para evitar conflictos con datos de otras
aplicaciones ejecutadas en el mismo navegador.

---

## Modelo de usuario

Cada usuario tendrá inicialmente esta estructura:

```javascript
{
    id: "usr-001",
    nombre: "Ana Administradora",
    correo: "admin@aulaconecta.test",
    clave: "Admin123",
    rol: "administracion",
    activo: true
}
```

Los roles admitidos serán:

- `administracion`
- `docente`
- `estudiante`

El rol estudiante también representa el acceso de la familia en este
prototipo.

---

## Control de acceso

La aplicación aplicará dos niveles de control:

### Protección de páginas

JavaScript comprobará que exista una sesión y que el rol tenga permiso para
abrir la página solicitada.

### Filtrado de registros

Los datos visibles se filtrarán según el usuario. Por ejemplo, un estudiante
solo podrá visualizar calificaciones asociadas con su identificador.

Ocultar botones no se considerará suficiente para controlar la interfaz. Las
funciones también comprobarán el rol antes de ejecutar acciones restringidas.

---

## Decisiones técnicas

### JavaScript sin framework

Se eligió JavaScript puro para fortalecer el aprendizaje de:

- Funciones.
- Objetos y arreglos.
- Eventos.
- Manipulación del DOM.
- Condicionales.
- Módulos.
- Operaciones CRUD.

### Uso de localStorage

Se eligió `localStorage` porque permite conservar datos al recargar la página
sin configurar un servidor.

Sus limitaciones son:

- Los datos permanecen únicamente en el navegador utilizado.
- El usuario puede leerlos o modificarlos mediante las herramientas del
  navegador.
- No cifra las contraseñas.
- No permite colaboración simultánea.
- No proporciona seguridad apropiada para un sistema escolar real.

Por estas razones, el proyecto utiliza exclusivamente datos ficticios y se
presenta como un prototipo educativo.

### Baja lógica de usuarios

Los usuarios no se eliminarán físicamente. En su lugar, su propiedad `activo`
cambiará a `false`. Así se conservan los registros relacionados.

---

## Accesibilidad

La interfaz deberá seguir estas reglas:

- Utilizar elementos HTML semánticos.
- Asociar cada campo con una etiqueta `label`.
- Mostrar claramente el foco del teclado.
- Evitar depender únicamente del color.
- Mantener contraste legible.
- Incluir mensajes de error descriptivos.
- Utilizar texto alternativo en imágenes informativas.

---

## Ejecución

El proyecto podrá ejecutarse con la extensión Live Server de VS Code:

1. Abrir la carpeta del repositorio en VS Code.
2. Abrir `index.html`.
3. Presionar **Open with Live Server**.
4. Probar las cuentas ficticias documentadas en `README.md`.

No se requieren dependencias ni comandos de instalación.

---

## Evolución futura

Si el prototipo se convierte en una aplicación real, será necesario:

- Reemplazar `localStorage` por una base de datos.
- Incorporar un backend.
- Cifrar las contraseñas.
- Implementar sesiones seguras.
- Aplicar permisos desde el servidor.
- Registrar auditorías de cambios.
- Cumplir las normas aplicables a datos de menores.