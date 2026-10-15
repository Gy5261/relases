# PRUEBA-ALFA-ORION-MINI

**Orion Mini** es un navegador para Windows x64 con host C# y motor WebView2, sin Electron.

## Descargar y abrir

Descarga [Orion Mini 1.3.11 portátil](https://github.com/Gy5261/relases/releases/download/v1.3.11/Orion-Mini-Portable-1.3.11.exe) desde [GitHub Releases](https://github.com/Gy5261/relases/releases/latest) y abre el EXE. Incluye el runtime WebView2; no necesita un instalador ni una descarga independiente del motor. La primera apertura extrae y verifica sus componentes en una caché local. Requiere Windows x64 compatible con WebView2 y .NET Framework 4.8, incluido en Windows 11.

El archivo es grande porque contiene el motor completo. La caché y los datos de navegación ocupan espacio adicional. El inicio y las pestañas nuevas abren Google.

## Actualizaciones

El canal portátil comprueba versiones al abrir y periódicamente. Verifica el manifiesto firmado mediante RSA/SHA-256, el tamaño y hash del EXE y el arranque real de WebView2 antes de preparar una actualización. La aplica al cerrar el navegador. Conserva un respaldo temporal hasta confirmar el siguiente arranque; si ese arranque termina sin confirmación, intenta recuperar la versión anterior. La actualización pública de 1.3.6 a 1.3.7 pasó la descarga con el actualizador anterior, validación criptográfica, arranque real, recuperación exacta, reactivación y confirmación.

**La primera adopción desde la versión 1.3.0 requiere descargar manualmente este nuevo portátil.** Las versiones antiguas no incluyen este canal. Los datos de navegación no forman parte del EXE ni son sustituidos por el actualizador.


La versión 1.3.11 deja únicamente Gemini oficial, sin paneles de configuración API ni un segundo chat. Escribe en Gemini y pulsa Compartir captura para adjuntar un pantallazo nuevo de la pestaña activa, sin activar ventanas ni capturar el escritorio. Conserva tu pregunta, trabaja en memoria y no usa el portapapeles ni captura continuamente. Cambiar de pestaña, navegar o cerrar cancela el trabajo pendiente; no retira datos recibidos por Google. Capturas reales de páginas rojas y azules, JPEG recibido por un receptor controlado, conservación de la pregunta, permisos y cancelación pasaron en el EXE protegido. La sesión anónima real requiere iniciar sesión para adjuntar imágenes; Orion lo indica. El inicio de sesión y la interpretación de imágenes por Google requieren la cuenta del usuario y siguen pendientes de verificación manual.

Histórico: la versión 1.3.10 abría Gemini web oficial dentro de Orion, sin clave API. Usa las funciones públicas disponibles o inicia sesión manualmente con Google. Para consultar la pestaña: Contexto → Compartir esta pestaña → pregunta → Preparar en Gemini → revisar y Enviar en Gemini. Cada preparación captura texto actualizado. Se verificó una respuesta real del servicio sobre un dato aleatorio extraído de una pestaña de prueba, sin cuenta ni clave. Las imágenes son opcionales y requieren iniciar sesión; el inicio de sesión y su procesamiento por Google siguen pendientes de verificación con una cuenta real. No se importan sesiones de Chrome ni se suplanta GLIC. Cambiar de pestaña, navegar o cerrar revoca el acceso y retira el borrador; no borra datos recibidos por Google. La API propia queda como opción explícita.

Histórico: la versión 1.3.9 incorporaba un panel nativo Gemini con clave propia de [Google AI Studio](https://aistudio.google.com/apikey). El botón de la barra permite compartir la pestaña, revisar localmente el texto y activar una captura visible opcional. Cada pregunta actualiza el contexto; navegar, cambiar de pestaña o cerrar el panel revoca el acceso y borra el historial local. La clave se guarda opcionalmente protegida con DPAPI, fuera del EXE y de las páginas. No utiliza sesiones de Chrome ni ejecuta acciones del modelo.

En esa modalidad API se probaron en WebView2 real la extracción aislada, imagen JPEG, exclusión de campos editables, permisos, revocación, vista previa y actualización del DOM. Las solicitudes HTTP locales verifican formato, cabeceras, errores, redirecciones y cancelación. La inferencia mediante esa API no está verificada porque el usuario no dispone todavía de una clave; las fixtures del parser no se presentan como respuestas generadas. La imagen puede incluir información privada visible: revocar no elimina datos ya enviados a Google.

La versión 1.3.8 integra el icono de Orion en el EXE portátil, el núcleo nativo, el actualizador y la ventana, con nueve resoluciones de 16 a 256 píxeles. El acceso directo conserva la identidad estable del portátil. Las actualizaciones funcionan sin controles visibles: mientras el navegador está abierto consulta nuevas versiones al iniciar y cada 15 minutos, con conexión a Internet, y aplica la versión verificada al cerrar.

La versión 1.3.7 elimina las pausas de protocolo en solicitudes permitidas, adapta la frecuencia de captura del cristal, sincroniza los menús con el reloj del motor y reduce el objetivo de memoria de pestañas ocultas sin suspender scripts. La comprobación de arranque usa un perfil aislado. Se verificaron iframes publicitarios de YouTube directos y anidados, navegación principal y reproducción pública; esa sesión no sirvió un anuncio que permita certificar su eliminación.

El EXE portátil protegido obtuvo medianas de Speedometer 3.1 de 34,9 antes y 34,89 después, con tres ejecuciones por versión: sin mejora concluyente. Un lote local de solicitudes legítimas pasó de 107,9 a 90,4 ms (-16,2 %), con cero pausas de protocolo. Las medianas observadas en el arnés de código fuente cambiaron +7,41 % en Speedometer, +6,45 % en JetStream y +35,22 % en MotionMark; la dispersión y la actividad externa impiden atribuir esas ganancias al producto. Los picos de RAM aumentaron. WebPageTest devolvió HTTP 403 y Edge no produjo una ejecución válida. No se afirma superioridad frente a otros navegadores.

La versión 1.3.6 integra Orion Shield en C#: SQLite WAL con fuentes comprimidas, excepciones y dos generaciones recuperables; validación de compatibilidad antes de activar reglas; observaciones limitadas a dominios/motivos, sin historial ni código remoto; controles nativos de descargas y redirecciones a destinos publicitarios conocidos. El escudo por sitio conserva la autoridad del documento cargado. Las redirecciones por JavaScript que atraviesen un dominio bloqueado pueden necesitar desactivar el escudo del sitio.

Las pruebas del EXE protegido cubren SQLite real, recuperación, concurrencia, SQL parametrizado, navegación, descargas, privacidad, Anti-AdBlock, workers y reproducción. Turtlecute público sin modificar: 128/132 (96,97 %); 240/240 solicitudes legítimas de control permitidas. En la medición histórica de 1.3.6, Speedometer 3.1: 33,6 / 34,5 / 35,08 frente a 34,3 / 34,99 / 34,74 antes; no demuestra mejora de velocidad y no compara otros navegadores.

El bloqueo de red evita contactar el destino publicitario mediante una respuesta nativa de redirección a contenido vacío. Las solicitudes fetch normales y las cargas de scripts, imágenes y CSS fallan; fetch con redirect: 'manual' recibe una respuesta opaca vacía de estado 0. Los sustitutos locales de compatibilidad conservan su respuesta correcta. En Turtlecute quedan cuatro señuelos sin reglas específicas de cobertura.

La versión 1.3.5 añade los 17 dominios solicitados como bloqueos explícitos; el escudo por sitio permite restaurar sus solicitudes. Estos bloqueos también pueden afectar recursos legítimos de los mismos dominios. La integración de barra de tareas utiliza una identidad estable y relanza el EXE portátil, independiente de la caché del motor. Propiedades nativas y persistencia del acceso directo verificadas; interacción manual de anclar/desanclar pendiente de comprobación en Explorer.

La versión 1.3.5 consolida doce fuentes oficiales mediante deduplicación canónica y un índice único por hostname. Integra Unbreak para entradas hosts, contramedidas Anti-AdBlock locales y acotadas, preservación de SRI y bloqueo de popups publicitarios automáticos. Conserva la protección contextual de privacidad, las excepciones y el escudo por sitio. El filtrado opera dentro de WebView2; no se garantiza bloqueo universal, DNS del sistema, CNAME desconocidos, SSAI ni neutralización de todos los desafíos Anti-AdBlock.

## Privacidad y distribución

Este repositorio público distribuye únicamente ejecutables y notas de versión. El código fuente se mantiene privado. No incluye perfiles, credenciales, llaves privadas ni diagnósticos personales.

**Estado: prueba alfa.** La firma criptográfica de las actualizaciones no equivale a un certificado Authenticode: Windows puede mostrar una advertencia de editor desconocido. Las pruebas locales de interfaz, reproducción, integridad y recuperación no garantizan ausencia de fallos en todos los equipos ni bloqueo universal de anuncios.
