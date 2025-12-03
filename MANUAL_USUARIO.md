# OptiCut – Manual de Usuario

## 1. Acceso e inicio de sesión
1. Abre `http://127.0.0.1:8000/`.
2. Regístrate con correo, nombre y contraseña o ingresa con un usuario existente.
3. Después de autenticarte serás redirigido al optimizador.

> Consejo: si compartes el equipo, recuerda cerrar sesión con el botón “Cerrar sesión”.

## 2. Crear una optimización

### 2.1 Dimensiones del tablero
- Introduce **ancho** y **alto** en centímetros.
- Puedes usar los botones de **Medidas predefinidas** (OSB, MDF, Melamina, etc.).
- Si el tablero no aparece en la lista, escribe sus dimensiones de forma manual.

### 2.2 Piezas a cortar
- Cada fila es una pieza. Campos:
  - **Nombre** (opcional, pero recomendable para identificarla).
  - **Ancho (cm)**, **Alto (cm)**, **Cantidad**.
- Botón **“Agregar otra pieza”** para más filas.
- Validaciones:
  - Todas las medidas deben ser positivas.
  - Las piezas no pueden ser más grandes que el tablero.
  - Debe haber al menos una pieza válida.

### 2.3 Calcular
1. Pulsa **“Calcular Optimización”**.
2. El sistema procesa los cortes con el algoritmo First Fit Decreasing (FFD).
3. Se generan:
   - Imágenes por tablero.
   - Aprovechamiento (%), área utilizada y desperdicio.
   - Información detallada por tablero.

## 3. Resultado del plan de corte
- Tarjetas de resumen con:
  - **Aprovechamiento total**.
  - **Área usada** y **desperdicio** (cm²).
  - Cantidad de tableros.
- Tabla por tablero con porcentaje de uso y número de piezas.
- Galería con todos los tableros.
- Botones:
  - **Descargar PDF** (incluye portada con piezas + tableros).
  - **Volver al optimizador**.
  - **Ver historial**.

## 4. Historial de optimizaciones
- Acceso desde el botón “Ver Historial” o la barra superior.
- Cada tarjeta muestra:
  - Imagen de la optimización.
  - Número secuencial, fecha, hora (Chile), dimensiones, aprovechamiento.
  - Enlace **“Ver Piezas”** con la lista detallada.
- Acciones:
  - **Duplicar**: abre el formulario con los mismos datos para editarlos.
  - **PDF**: genera el reporte nuevamente.
  - **Borrar**: elimina solo esa optimización.
- Filtros disponibles:
  - Nombre de pieza (texto).
  - Fecha desde / hasta.
- Acciones globales:
  - **Borrar historial**: elimina todas las optimizaciones del usuario (irreversible).

## 5. FAQ / Preguntas frecuentes

### ¿Por qué una pieza no se agrega?
Verifica que tenga ancho, alto y cantidad. Asegúrate de que las dimensiones sean menores o iguales a las del tablero.

### ¿Puedo usar decimales?
Actualmente los campos reciben enteros (centímetros). Si necesitas milímetros, multiplica por 10.

### ¿Qué pasa si el PDF no se genera?
El sistema muestra un mensaje de advertencia. Revisa que la carpeta `media/pdfs` exista y que el usuario tenga permisos de escritura.

### ¿Cómo respaldo mi información?
- Copia el archivo `db.sqlite3` y la carpeta `media/`.
- Si usas Git, incluye `MANUAL_USUARIO.md` para distribuirlo con el proyecto.

### ¿Puedo exportar las piezas a Excel?
No aún. Temporariamente puedes copiar la tabla de historial o usar el PDF. (Ver mejoras futuras.)

## 6. Consejos de uso
- Nombra las piezas según el proyecto (ej. “Puerta clóset izquierda”).
- Usa comentarios en el nombre para indicar material o acabado.
- Guarda los PDFs como respaldo para el área de corte.
- Si compartes el sistema en red, configura un `STATIC_ROOT` y `MEDIA_ROOT` accesibles.

---

**Contacto interno:** agrega aquí datos del responsable del sistema para soporte dentro del taller.



