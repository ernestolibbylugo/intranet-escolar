# Guía de contribución de AulaConecta

## Propósito

Este documento establece el proceso para realizar cambios en AulaConecta de
forma ordenada, comprensible y verificable.

Aunque el proyecto se desarrolla individualmente, se utiliza un flujo
profesional basado en ramas, commits y pull requests.

---

## Preparación del proyecto

Para trabajar en una copia local:

```bash
git clone https://github.com/ernestolibbylugo/intranet-escolar.git
cd intranet-escolar
```

Después, se debe abrir la carpeta en VS Code y ejecutar `index.html` mediante
Live Server.

No se necesitan dependencias ni comandos de instalación.

---

## Flujo de trabajo

Cada cambio debe seguir este proceso:

1. Actualizar la rama objetivo `origin/main`.
2. Crear una rama para la tarea.
3. Modificar únicamente los archivos relacionados.
4. Probar los cambios localmente.
5. Crear uno o varios commits pequeños.
6. Publicar la rama en GitHub.
7. Crear un pull request.
8. Revisar los archivos modificados.
9. Integrar el pull request en `main`.

> No se deben desarrollar funcionalidades directamente sobre `main`.

---

## Nombres de ramas

Las ramas deben utilizar minúsculas, palabras separadas con guiones y uno de
los siguientes prefijos:

| Prefijo | Propósito | Ejemplo |
|---|---|---|
| `feature/` | Nueva funcionalidad | `feature/inicio-sesion` |
| `fix/` | Corrección de un error | `fix/validacion-correo` |
| `docs/` | Cambios de documentación | `docs/instrucciones-uso` |
| `style/` | Cambios visuales | `style/panel-responsive` |
| `refactor/` | Reorganización del código | `refactor/almacenamiento` |
| `test/` | Pruebas | `test/permisos-roles` |
| `chore/` | Configuración y mantenimiento | `chore/estructura-inicial` |

Cada rama debe tener un propósito concreto.

---

## Mensajes de commit

Los mensajes se escribirán en español, en infinitivo y con esta estructura:

```text
tipo: descripción breve
```

Tipos permitidos:

- `feat`: agregar una funcionalidad.
- `fix`: corregir un error.
- `docs`: modificar documentación.
- `style`: cambiar presentación sin alterar la lógica.
- `refactor`: reorganizar código sin cambiar el resultado.
- `test`: agregar o actualizar pruebas.
- `chore`: realizar mantenimiento o configuración.

Ejemplos correctos:

```text
feat: validar inicio de sesión
fix: impedir correos duplicados
docs: explicar cuentas de demostración
style: mejorar contraste del formulario
refactor: reutilizar lectura de localStorage
test: verificar acceso por rol
chore: configurar archivos ignorados
```

Se debe evitar:

```text
cambios
actualización
arreglé cosas
proyecto terminado
```

---

## Tamaño de los commits

Cada commit debe:

- Resolver una parte concreta de la tarea.
- Incluir únicamente archivos relacionados.
- Mantener el proyecto en un estado comprensible.
- Tener un mensaje que explique claramente el cambio.

Si se modifican al mismo tiempo la documentación y una funcionalidad, se
recomienda crear commits separados cuando los cambios sean independientes.

---

## Pull requests

Cada pull request debe incluir:

### Descripción

Una explicación breve del cambio y su propósito.

### Cambios realizados

Una lista de las modificaciones principales.

### Pruebas

Los pasos utilizados para comprobar el funcionamiento.

### Lista de comprobación

- [ ] El cambio cumple el requerimiento.
- [ ] La interfaz funciona con teclado.
- [ ] No se utilizaron datos personales reales.
- [ ] No hay errores en la consola.
- [ ] La documentación fue actualizada.
- [ ] Los commits tienen mensajes descriptivos.

---

## Revisión

Antes de integrar un pull request se debe revisar:

1. La pestaña **Files changed**.
2. Que no existan archivos temporales.
3. Que no haya credenciales ni información sensible.
4. Que cada archivo pertenezca a la tarea.
5. Que el código respete `AGENTS.md`.
6. Que la aplicación continúe funcionando.
7. Que la documentación se lea correctamente.

Al trabajar individualmente, el autor realizará esta revisión antes de
integrar el cambio.

---

## Estilo de código

Las reglas completas están en [`AGENTS.md`](AGENTS.md). Como resumen:

- Utilizar español para nombres propios del proyecto.
- Preferir `const` y utilizar `let` solo cuando sea necesario.
- No utilizar `var`.
- Utilizar igualdad estricta.
- Evitar estilos CSS en línea.
- Mantener una responsabilidad principal por archivo.
- Validar los datos antes de guardarlos.
- Utilizar HTML semántico y accesible.

---

## Reporte de errores

Un reporte debe indicar:

- Página o módulo afectado.
- Usuario o rol utilizado.
- Pasos para reproducir el problema.
- Resultado esperado.
- Resultado obtenido.
- Mensajes mostrados en la consola.
- Navegador utilizado.

Ejemplo:

```text
Rol: docente
Página: calificaciones.html

Pasos:
1. Iniciar sesión como docente.
2. Abrir Calificaciones.
3. Enviar el formulario sin seleccionar estudiante.

Resultado esperado:
Mostrar un mensaje de validación.

Resultado obtenido:
Se crea un registro sin estudiante.
```

---

## Conducta y privacidad

Toda colaboración debe ser respetuosa y proteger la privacidad de estudiantes,
familias y personal educativo.

Está prohibido incluir información personal real en ejemplos, capturas,
commits, incidencias o documentación.