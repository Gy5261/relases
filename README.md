# PRUEBA-ALFA-ORION-MINI

Distribución pública de **Orion Mini para Windows x64**.

[Descargar el instalador de la última versión](https://github.com/Gy5261/relases/releases/latest).

Este repositorio contiene exclusivamente documentación de distribución y archivos `.exe` publicados mediante GitHub Releases. El código fuente y el flujo de compilación permanecen en el repositorio privado `Gy5261/Orion-Mini`.

Después de la instalación inicial, Orion Mini comprueba automáticamente nuevas versiones al iniciar y cada 15 minutos. Descarga el instalador, verifica su manifiesto firmado y SHA-256, instala en una carpeta nueva y vuelve a abrir el navegador. Las versiones son inmutables y cada publicación identifica el commit privado que la produjo.

El perfil de usuario se conserva en `%LOCALAPPDATA%\CloneSafari`. Si la nueva versión no confirma un inicio correcto, el instalador intenta volver a la anterior. La instalación no requiere permisos de administrador y se realiza en `%LOCALAPPDATA%\OrionMini`.

**Versión alfa de pruebas.** Windows puede mostrar una advertencia inicial porque el instalador no tiene certificado Authenticode comercial. Las actualizaciones automáticas verifican una firma RSA independiente con la clave pública incluida en el navegador; no ejecutan instaladores sin verificar.
