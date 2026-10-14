# PRUEBA-ALFA-ORION-MINI

**Orion Mini** es un navegador para Windows x64 con host C# y motor WebView2, sin Electron.

## Descargar y abrir

Descarga [Orion Mini 1.3.6 portátil](https://github.com/Gy5261/relases/releases/download/v1.3.6/Orion-Mini-Portable-1.3.6.exe) desde [GitHub Releases](https://github.com/Gy5261/relases/releases/latest) y abre el EXE. Incluye el runtime WebView2; no necesita un instalador ni una descarga independiente del motor. La primera apertura extrae y verifica sus componentes en una caché local. Requiere Windows x64 compatible con WebView2 y .NET Framework 4.8, incluido en Windows 11.

El archivo es grande porque contiene el motor completo. La caché y los datos de navegación ocupan espacio adicional. El inicio y las pestañas nuevas abren Google.

## Actualizaciones

El canal portátil comprueba versiones al abrir y periódicamente. Verifica el manifiesto firmado mediante RSA/SHA-256, el tamaño y hash del EXE y el arranque real de WebView2 antes de preparar una actualización. La aplica al cerrar el navegador. Conserva un respaldo temporal hasta confirmar el siguiente arranque; si ese arranque termina sin confirmación, intenta recuperar la versión anterior.

**La primera adopción desde la versión 1.3.0 requiere descargar manualmente este nuevo portátil.** Las versiones antiguas no incluyen este canal. Los datos de navegación no forman parte del EXE ni son sustituidos por el actualizador.


La versión 1.3.6 integra Orion Shield en C#: SQLite WAL con fuentes comprimidas, excepciones y dos generaciones recuperables; validación de compatibilidad antes de activar reglas; observaciones limitadas a dominios/motivos, sin historial ni código remoto; controles nativos de descargas y redirecciones a destinos publicitarios conocidos. El escudo por sitio conserva la autoridad del documento cargado. Las redirecciones por JavaScript que atraviesen un dominio bloqueado pueden necesitar desactivar el escudo del sitio.

Las pruebas del EXE protegido cubren SQLite real, recuperación, concurrencia, SQL parametrizado, navegación, descargas, privacidad, Anti-AdBlock, workers y reproducción. Turtlecute público sin modificar: 128/132 (96,97 %); 240/240 solicitudes legítimas de control permitidas. Speedometer 3.1: 33,6 / 34,5 / 35,08 frente a 34,3 / 34,99 / 34,74 antes; no demuestra mejora de velocidad y no compara otros navegadores.

El bloqueo de red hace que las solicitudes publicitarias fallen en Chromium en lugar de devolver HTTP 204 exitoso. En Turtlecute quedan cuatro señuelos sin reglas específicas de cobertura.

La versión 1.3.5 añade los 17 dominios solicitados como bloqueos explícitos; el escudo por sitio permite restaurar sus solicitudes. Estos bloqueos también pueden afectar recursos legítimos de los mismos dominios. La integración de barra de tareas utiliza una identidad estable y relanza el EXE portátil, independiente de la caché del motor. Propiedades nativas y persistencia del acceso directo verificadas; interacción manual de anclar/desanclar pendiente de comprobación en Explorer.

La versión 1.3.5 consolida doce fuentes oficiales mediante deduplicación canónica y un índice único por hostname. Integra Unbreak para entradas hosts, contramedidas Anti-AdBlock locales y acotadas, preservación de SRI y bloqueo de popups publicitarios automáticos. Conserva la protección contextual de privacidad, las excepciones y el escudo por sitio. El filtrado opera dentro de WebView2; no se garantiza bloqueo universal, DNS del sistema, CNAME desconocidos, SSAI ni neutralización de todos los desafíos Anti-AdBlock.

## Privacidad y distribución

Este repositorio público distribuye únicamente ejecutables y notas de versión. El código fuente se mantiene privado. No incluye perfiles, credenciales, llaves privadas ni diagnósticos personales.

**Estado: prueba alfa.** La firma criptográfica de las actualizaciones no equivale a un certificado Authenticode: Windows puede mostrar una advertencia de editor desconocido. Las pruebas locales de interfaz, reproducción, integridad y recuperación no garantizan ausencia de fallos en todos los equipos ni bloqueo universal de anuncios.
