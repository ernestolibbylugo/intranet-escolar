# AulaConecta

![Estado del proyecto](https://img.shields.io/badge/estado-en%20desarrollo-2563eb)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-f7df1e)
![Licencia](https://img.shields.io/badge/licencia-MIT-16a34a)

**AulaConecta** es un prototipo de intranet escolar para una institución
educativa pública. Permite gestionar usuarios, registrar información académica
y publicar comunicados según el rol de cada persona.

El proyecto fue desarrollado con fines educativos utilizando HTML, CSS,
JavaScript puro y `localStorage`.

> Los usuarios, contraseñas, calificaciones y demás registros son ficticios.
> Esta aplicación no debe utilizarse para almacenar información escolar real.

---

## Funcionalidades

### Administración

- Gestionar usuarios.
- Crear y editar cuentas.
- Desactivar usuarios.
- Consultar información académica.
- Publicar comunicados oficiales.

### Docente

- Consultar estudiantes.
- Registrar y editar calificaciones.
- Registrar asistencia.
- Publicar comunicados.

### Estudiante/familia

- Consultar sus propias calificaciones.
- Consultar sus propios registros de asistencia.
- Leer comunicados dirigidos a su perfil.

---

## Estado del desarrollo

- [x] Definir el alcance.
- [x] Crear la estructura inicial.
- [x] Documentar requerimientos.
- [x] Documentar arquitectura.
- [x] Crear la memoria del agente.
- [ ] Implementar almacenamiento local.
- [ ] Implementar autenticación.
- [ ] Implementar protección por roles.
- [ ] Implementar gestión de usuarios.
- [ ] Implementar calificaciones.
- [ ] Implementar asistencia.
- [ ] Implementar comunicados.
- [ ] Completar pruebas de accesibilidad.

El progreso detallado se encuentra en
[`docs/requerimientos.md`](docs/requerimientos.md).

---

## Tecnologías

| Tecnología | Propósito |
|---|---|
| HTML5 | Estructura semántica |
| CSS3 | Diseño adaptable y accesible |
| JavaScript | Lógica y manipulación del DOM |
| `localStorage` | Persistencia local de datos ficticios |
| Git | Control de versiones |
| GitHub | Repositorio y pull requests |
| GitButler | Gestión visual de ramas y commits |
| Markdown | Documentación |

---

## Requisitos

Para ejecutar el proyecto se necesita:

- Un navegador moderno.
- [Visual Studio Code](https://code.visualstudio.com/).
- La extensión
  [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).
- Git, únicamente si se desea clonar o contribuir al repositorio.

No se requieren Node.js, paquetes externos ni una base de datos.

---

## Instalación

### Opción 1: clonar con Git

Abre una terminal y ejecuta:

```bash
git clone https://github.com/ernestolibbylugo/intranet-escolar.git
cd intranet-escolar
```

Después abre la carpeta en Visual Studio Code.

### Opción 2: descargar el proyecto

1. Abre el repositorio en GitHub.
2. Presiona **Code**.
3. Selecciona **Download ZIP**.
4. Extrae el archivo.
5. Abre la carpeta extraída en Visual Studio Code.

---

## Ejecución

1. Abre `index.html` en Visual Studio Code.
2. Haz clic derecho dentro del archivo.
3. Selecciona **Open with Live Server**.
4. Espera a que la aplicación se abra en el navegador.

La dirección normalmente será similar a:

```text
http://127.0.0.1:5500/index.html
```

También es posible abrir `index.html` directamente, pero Live Server ofrece un
entorno más consistente durante el desarrollo.

---

## Cuentas de demostración

Cuando la autenticación esté implementada, se podrán utilizar estas cuentas:

| Rol | Correo | Contraseña |
|---|---|---|
| Administración | `admin@aulaconecta.test` | `Admin123` |
| Docente | `docente@aulaconecta.test` | `Docente123` |
| Estudiante/familia | `estudiante@aulaconecta.test` | `Estudiante123` |

Estas credenciales son públicas e intencionalmente ficticias.

---

## Ejemplo de uso

Para consultar calificaciones como estudiante:

1. Ejecuta la aplicación con Live Server.
2. Ingresa con la cuenta `estudiante@aulaconecta.test`.
3. Abre la opción **Mis calificaciones**.
4. Revisa las calificaciones correspondientes a la cuenta.
5. Presiona **Cerrar sesión** al terminar.

Para probar los permisos, intenta abrir una sección administrativa desde una
cuenta estudiantil. La aplicación deberá impedir el acceso.

---

## Estructura del proyecto

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

La estructura crecerá progresivamente conforme se implementen los módulos.

---

## Documentación

- [Arquitectura](docs/arquitectura.md)
- [Requerimientos](docs/requerimientos.md)
- [Memoria del agente](AGENTS.md)
- [Guía de contribución](CONTRIBUTING.md)
- [Historial de cambios](CHANGELOG.md)

---

## Limitaciones

`localStorage` permite ejecutar el prototipo sin servidor, pero presenta
limitaciones importantes:

- Los datos solo existen en el navegador utilizado.
- Cualquier persona con acceso al navegador puede modificarlos.
- Las contraseñas no se almacenan de forma segura.
- No existe sincronización entre dispositivos.
- No proporciona protección adecuada para datos personales.

Una versión de producción necesitaría un backend, una base de datos y un
sistema seguro de autenticación y autorización.

---

## Contribución

Las reglas para ramas, commits y pull requests están disponibles en
[`CONTRIBUTING.md`](CONTRIBUTING.md).

Antes de modificar el código también se debe consultar
[`AGENTS.md`](AGENTS.md).

---

## Autor

**Ernesto Libby Lugo**

Proyecto final del programa de Programación Front End con IA Aplicada, 2026.

---

## Licencia

Este proyecto se distribuye bajo la licencia MIT. Consulta el archivo
[`LICENSE`](LICENSE) para conocer sus términos.