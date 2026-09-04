# Auditoria de `prueba1`

**Fecha:** 2026-09-04  
**Alcance:** `index.html` y `styles.css`  
**Herramienta solicitada:** OpenCode

## Estado de la auditoria

La extension OpenCode GUI esta instalada en VS Code, pero el comando `opencode` no esta disponible en el terminal de este entorno. Por ese motivo, este informe recoge la revision local del proyecto y deja identificado lo que debe confirmar el agente OpenCode cuando se habilite su ejecucion.

La revision posterior se aplico el 2026-09-04 con los cambios descritos en este documento.

## Novedades encontradas

### 1. Dependencias visuales externas

**Severidad: media · Resuelto parcialmente**

- La fotografia principal ahora se sirve desde `assets/player.jpg`.
- Las tipografias se cargan desde Google Fonts.
- Sin conexion a internet, las tipografias caeran a sus fuentes de respaldo.

**Impacto:** la experiencia visual depende de Google Fonts para conservar la tipografia principal.

**Recomendacion pendiente:** servir las tipografias localmente o documentar expresamente esta dependencia de red.

### 2. Contenido de ejemplo sin fuente editorial

**Severidad: baja · Resuelto**

El jugador, el club y las estadisticas parecen datos demostrativos. La pagina ahora incluye un aviso visible de ficha demostrativa y fecha de revision.

**Impacto:** reducido; la interfaz ya advierte que los datos no estan verificados.

**Recomendacion pendiente:** sustituir los datos por informacion verificada si la ficha se publica como contenido real.

### 3. Falta de pruebas automatizadas de responsive y accesibilidad

**Severidad: baja · Mejorado**

El HTML y CSS siguen sin pruebas automatizadas, pero la pagina ahora incorpora foco visible para teclado, fallback de imagen y estilos responsive para movil.

**Impacto:** cambios futuros podrian introducir desbordamientos, problemas de contraste o perdida de legibilidad sin detectarse.

**Recomendacion pendiente:** comprobar la pagina en mobile (360 px) y desktop (1280 px), y validar contraste mediante una herramienta automatizada.

## Comprobaciones realizadas

- HTML, CSS y Markdown revisados sin errores detectados por VS Code.
- La imagen local existe en `assets/player.jpg` y tiene texto alternativo descriptivo.
- La interfaz muestra "Ficha demostrativa" y la fecha de revision.
- El enlace de estadisticas apunta a una seccion existente mediante `#stats`.
- La hoja de estilos incluye breakpoints para 900 px y 600 px.
- Los controles interactivos tienen un estado `:focus-visible`.
- Si la imagen local falla, se muestra el estado "Imagen no disponible".

## Prioridad sugerida

1. Resolver la dependencia externa de las tipografias si la pagina debe funcionar completamente offline.
2. Sustituir los datos demostrativos por informacion verificada si procede.
3. Añadir una comprobacion visual automatizada en movil y escritorio.
