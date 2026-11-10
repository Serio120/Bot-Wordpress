# Bot-Wordpress

Scripts de automatización con Selenium para publicar contenido en varios sitios WordPress a partir de documentos Word.

## Seguridad y configuración

**No guardes usuarios ni contraseñas en el repositorio.** Los scripts leen las credenciales desde variables de entorno. El archivo histórico `usuarios-y-pwd.txt` se ha retirado del árbol de trabajo; como estuvo en un repositorio público, sus credenciales deben considerarse expuestas y rotarse.

Configura únicamente las variables correspondientes al sitio que vayas a utilizar:

| Script | Usuario | Contraseña |
|---|---|---|
| `canterablanca.py` | `CANTERABLANCA_WP_USERNAME` | `CANTERABLANCA_WP_PASSWORD` |
| `maipu.py` | `MAIPU_WP_USERNAME` | `MAIPU_WP_PASSWORD` |
| `maipuar.py` | `MAIPU_AR_WP_USERNAME` | `MAIPU_AR_WP_PASSWORD` |
| `maipuch.py` | `MAIPU_CH_WP_USERNAME` | `MAIPU_CH_WP_PASSWORD` |
| `nuicon.py` | `NUICON_WP_USERNAME` | `NUICON_WP_PASSWORD` |

En PowerShell, define las variables antes de ejecutar el script. Ejemplo:

```powershell
$env:CANTERABLANCA_WP_USERNAME = "tu_usuario"
$env:CANTERABLANCA_WP_PASSWORD = "tu_contraseña"
python .\canterablanca.py
```

En Bash:

```bash
export CANTERABLANCA_WP_USERNAME="tu_usuario"
export CANTERABLANCA_WP_PASSWORD="tu_contraseña"
python canterablanca.py
```

No compartas capturas, logs ni archivos que contengan credenciales.

## Contenido

- Los scripts Python automatizan tareas de publicación con Selenium.
- `Info_Selenium.md` contiene notas y ejemplos de uso de Selenium.
- Los documentos Word sirven como material de entrada para los scripts.

## Requisitos

Instala Python y las dependencias utilizadas por el script que vayas a ejecutar, incluyendo Selenium y python-docx. Configura también Chrome y su WebDriver de acuerdo con tu entorno.

## Ejecución

Configura primero las variables de entorno del sitio correspondiente y ejecuta el script:

```bash
python canterablanca.py
```

Sustituye el nombre del script por el sitio que necesites.

## Nota sobre el historial

Eliminar credenciales de los archivos actuales no las elimina de commits anteriores. Rota todas las contraseñas que hayan estado en este repositorio y, si necesitas retirar los valores del historial, realiza una limpieza de historial coordinada y vuelve a revisar todos los clones y forks.
