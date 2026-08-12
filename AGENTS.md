# AGENTS.md — Memoria del agente de AulaConecta

## 1. Contexto

AulaConecta es un prototipo académico de una intranet para una institución
educativa pública.

El sistema permite administrar usuarios y consultar información escolar según
tres perfiles:

- Administración.
- Docente.
- Estudiante/familia.

El proyecto se desarrolla individualmente como parte del curso de Programación
Front End con IA Aplicada. Utiliza HTML5, CSS3 y JavaScript puro.

Los datos se almacenan en `localStorage` y son completamente ficticios. La
aplicación no representa un sistema seguro para uso institucional real.

---

## 2. Requerimientos

El sistema debe permitir:

- Iniciar y cerrar sesión.
- Controlar el acceso según el rol.
- Crear, consultar, editar y desactivar usuarios.
- Registrar y consultar calificaciones.
- Registrar y consultar asistencia.
- Crear y consultar comunicados.
- Mostrar a cada usuario únicamente la información correspondiente.
- Conservar los datos al recargar la página.
- Ejecutarse mediante Live Server sin instalar dependencias.

Los requerimientos detallados y su progreso se encuentran en
[`docs/requerimientos.md`](docs/requerimientos.md).

---

## 3. Reglas

### Idioma y nombres

- Utilizar español en nombres de variables, funciones y archivos.
- Utilizar `camelCase` para variables y funciones.
- Utilizar `PascalCase` solamente si se crean clases.
- Utilizar mayúsculas con guion bajo para constantes globales.
- Utilizar nombres descriptivos y evitar abreviaciones ambiguas.

Ejemplos:

```javascript
const ROL_ADMINISTRACION = "administracion";
const usuariosActivos = obtenerUsuariosActivos();

function validarCredenciales(correo, clave) {
    // Lógica de validación.
}
```

### JavaScript

- Declarar variables con `const` siempre que no cambien.
- Utilizar `let` únicamente cuando el valor deba reasignarse.
- No utilizar `var`.
- Dividir las funciones extensas en funciones pequeñas.
- Evitar modificar variables globales directamente.
- Validar los datos antes de almacenarlos.
- Utilizar igualdad estricta con `===` y `!==`.
- Agregar control de errores cuando una operación pueda fallar.

### HTML

- Utilizar un solo elemento `h1` por página.
- Usar HTML semántico: `header`, `nav`, `main`, `section` y `footer`.
- Asociar cada campo de formulario con un elemento `label`.
- Definir el atributo `type` de cada botón.
- Incluir texto alternativo en las imágenes.

### CSS

- Mantener los estilos generales en `css/global.css`.
- Utilizar clases reutilizables.
- Evitar estilos en línea.
- Mostrar claramente el foco mediante `:focus-visible`.
- Diseñar primero para pantallas pequeñas.
- Mantener contraste suficiente entre texto y fondo.

### Git y commits

- Trabajar cada funcionalidad en una rama propia.
- Crear commits pequeños y relacionados.
- Escribir los mensajes en español y en infinitivo.
- Utilizar prefijos como `feat`, `fix`, `docs`, `style`, `refactor`, `test` y
  `chore`.
- Integrar los cambios en `main` mediante pull requests.

Ejemplo:

```text
feat: validar inicio de sesión por rol
```

---

## 4. Restricciones

- NO utilizar datos reales de menores, familias o personal educativo.
- NO presentar `localStorage` como almacenamiento seguro.
- NO guardar credenciales personales o API keys.
- NO incorporar un backend sin documentar primero la decisión.
- NO agregar frameworks o dependencias sin justificación.
- NO utilizar `eval()`.
- NO almacenar elementos del DOM dentro de `localStorage`.
- NO permitir correos duplicados.
- NO eliminar usuarios físicamente; se debe utilizar baja lógica.
- NO ocultar errores mediante bloques `catch` vacíos.
- NO escribir toda la lógica en un único archivo.
- NO modificar funcionalidades ajenas a la tarea solicitada.
- NO realizar cambios directamente en `main`.
- NO hacer un único commit con todo el proyecto.

---

## 5. Objetivos

### Objetivo actual

Completar una versión mínima funcional que permita:

1. Iniciar sesión con cuentas ficticias.
2. Detectar el rol del usuario.
3. Mostrar un panel correspondiente al rol.
4. Proteger las páginas restringidas.
5. Cerrar la sesión.

### Objetivos siguientes

- Implementar la gestión de usuarios.
- Implementar el módulo de calificaciones.
- Implementar el control de asistencia.
- Implementar el tablón de comunicados.
- Mejorar accesibilidad y diseño adaptable.
- Completar pruebas y documentación.

### Criterio de finalización

Una funcionalidad se considera terminada cuando:

- Cumple su requerimiento.
- Valida entradas incorrectas.
- Respeta los permisos establecidos.
- Se puede utilizar con teclado.
- Fue probada manualmente.
- Está documentada.
- Tiene un commit descriptivo.

---

## 6. Memoria del proyecto

### 2026-08 — Elección del alcance

Se decidió implementar los módulos mínimos obligatorios antes de agregar
calendario, horarios, materiales o reserva de recursos. Esto reduce el riesgo
de dejar incompletos los requisitos evaluados.

### 2026-08 — Elección del stack

Se eligieron HTML5, CSS3 y JavaScript puro para practicar los fundamentos del
desarrollo frontend sin introducir React u otro framework.

### 2026-08 — Almacenamiento local

Se eligió `localStorage` para ejecutar el proyecto sin servidor ni base de
datos. Se reconoce que esta tecnología no protege información sensible, por
lo que solo se utilizarán datos ficticios.

### 2026-08 — Roles

Se definieron tres roles:

- `administracion`
- `docente`
- `estudiante`

El rol `estudiante` también representa el acceso familiar para mantener el
alcance controlado.

### 2026-08 — Usuarios desactivados

Se decidió utilizar baja lógica. Al dar de baja una cuenta, la propiedad
`activo` cambiará a `false` en lugar de eliminar el registro.

### 2026-08 — Flujo de Git

Se decidió utilizar GitButler para organizar visualmente las ramas y los
commits. GitHub almacenará el repositorio y los cambios llegarán a `main`
mediante pull requests.

Toda decisión nueva que cambie la arquitectura, los datos o el alcance debe
agregarse a esta sección con su fecha y justificación.

---

## 7. Buenas prácticas

### Organización

- Mantener separadas la estructura, la presentación, la lógica y los datos.
- Crear un archivo JavaScript por responsabilidad principal.
- Reutilizar funciones de almacenamiento.
- Evitar duplicar validaciones y componentes visuales.
- Mantener la estructura de carpetas documentada.

### Datos

- Convertir los objetos a texto con `JSON.stringify()` antes de guardarlos.
- Recuperarlos con `JSON.parse()`.
- Utilizar valores predeterminados cuando una clave no exista.
- Generar identificadores únicos para los registros.
- Validar relaciones entre usuarios, materias y registros académicos.

### Interfaz

- Mostrar retroalimentación después de cada acción.
- Confirmar las operaciones que cambien datos importantes.
- Deshabilitar acciones no permitidas para el rol.
- Mostrar estados vacíos cuando no haya registros.
- Mantener textos y controles comprensibles.

### Documentación

- Documentar el motivo de las decisiones, no repetir literalmente el código.
- Actualizar `CHANGELOG.md` cuando cambie una versión.
- Actualizar las tareas de `docs/requerimientos.md`.
- Mantener `README.md` suficiente para ejecutar y probar el proyecto.
- Mantener este archivo actualizado para humanos y asistentes de IA.

### Pruebas

Antes de integrar una funcionalidad:

1. Probar el caso esperado.
2. Probar campos vacíos.
3. Probar valores inválidos.
4. Probar un usuario sin permisos.
5. Recargar la página y comprobar la persistencia.
6. Revisar la consola del navegador.
7. Comprobar la navegación mediante teclado.

---

## Instrucción final para asistentes de IA

Antes de modificar el proyecto:

1. Leer este archivo completo.
2. Consultar `docs/requerimientos.md`.
3. Revisar `docs/arquitectura.md`.
4. Respetar el alcance y las restricciones.
5. Explicar cualquier decisión técnica importante.
6. Mantener actualizada la memoria del proyecto.