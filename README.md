# PRUEBA-ALFA-ORION-MINI

**Orion Mini** es un navegador para Windows x64 con host C# y motor WebView2, sin Electron.

## Descargar y abrir

Descarga [Orion Mini 1.3.3 portátil](https://github.com/Gy5261/relases/releases/download/v1.3.3/Orion-Mini-Portable-1.3.3.exe) desde [GitHub Releases](https://github.com/Gy5261/relases/releases/latest) y abre el EXE. Incluye el runtime WebView2; no necesita un instalador ni una descarga independiente del motor. La primera apertura extrae y verifica sus componentes en una caché local. Requiere Windows x64 compatible con WebView2 y .NET Framework 4.8, incluido en Windows 11.

El archivo es grande porque contiene el motor completo. La caché y los datos de navegación ocupan espacio adicional. El inicio y las pestañas nuevas abren Google.

## Actualizaciones

El canal portátil comprueba versiones al abrir y periódicamente. Verifica el manifiesto firmado mediante RSA/SHA-256, el tamaño y hash del EXE y el arranque real de WebView2 antes de preparar una actualización. La aplica al cerrar el navegador. Conserva un respaldo temporal hasta confirmar el siguiente arranque; si ese arranque termina sin confirmación, intenta recuperar la versión anterior.

**La primera adopción desde la versión 1.3.0 requiere descargar manualmente este nuevo portátil.** Las versiones antiguas no incluyen este canal. Los datos de navegación no forman parte del EXE ni son sustituidos por el actualizador.


La versión 1.3.3 añade protección contextual inicial de publicidad, analítica y grabación, informes opcionales, píxeles sociales, redes mixtas y destinos web de telemetría. Incorpora la lista de privacidad de uAssets y corrige variantes DNS/IDN/puertos. Las excepciones y el escudo por sitio se conservan; no se garantiza bloquear todo rastreo de primera parte, WebSockets ni tráfico fuera del navegador.

## Privacidad y distribución

Este repositorio público distribuye únicamente ejecutables y notas de versión. El código fuente se mantiene privado. No incluye perfiles, credenciales, llaves privadas ni diagnósticos personales.

**Estado: prueba alfa.** La firma criptográfica de las actualizaciones no equivale a un certificado Authenticode: Windows puede mostrar una advertencia de editor desconocido. Las pruebas locales de interfaz, reproducción, integridad y recuperación no garantizan ausencia de fallos en todos los equipos ni bloqueo universal de anuncios.
