# Herramienta de Siembra (CLI / Seeder)

Script externo especializado en inicializar datos de prueba y catálogo maestro en el sistema.

## Limitaciones Arquitectónicas
1. **Comunicación Exclusiva vía HTTP**: Esta herramienta tiene estrictamente prohibido conectarse al puerto 3306 (MySQL). Toda inyección de datos ocurre consumiendo la API de la aplicación.
2. **Idempotencia**: Debe construirse pensando en ejecuciones múltiples. Si el catálogo ya existe, actualiza o salta, previniendo duplicidades de datos.
3. **Manejo de Credenciales**: Datos sensibles como contraseñas de admin inicial deben inyectarse exclusivamente por variables de entorno (`.env`).
