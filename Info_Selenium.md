# Info Selenium

## Ejemplo clase Keys

La clase **`Keys`** en Selenium es fundamental porque te permite simular teclas que no son texto, como **Enter**, **Tabulador**, **Flechas**, **Escape**, etc.

Para usarla, la clave está en importarla correctamente:
`from selenium.webdriver.common.keys import Keys`

Aquí tienes un ejemplo muy sencillo. Vamos a abrir Google, escribir una búsqueda y presionar **ENTER** en lugar de buscar el botón de "Buscar" con el ratón.

### Ejemplo: Búsqueda en Google pulsando Enter

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
# 1. IMPORTACIÓN OBLIGATORIA DE KEYS
from selenium.webdriver.common.keys import Keys 
import time

# Inicializamos el navegador (asegúrate de tener el driver configurado)
driver = webdriver.Chrome()

try:
    # Vamos a Google
    driver.get("https://www.google.com")

    # Localizamos la barra de búsqueda (por su nombre 'q')
    caja_busqueda = driver.find_element(By.NAME, "q")

    # 2. USAMOS KEYS
    # Escribimos "Selenium Python" y concatenamos la tecla ENTER
    caja_busqueda.send_keys("Selenium Python", Keys.ENTER)

    # Esperamos un poco para ver el resultado
    time.sleep(5)

finally:
    # Cerramos el navegador
    driver.quit()

```

---

### Desglose de lo importante

1. **La Importación:**
Sin la línea `from selenium.webdriver.common.keys import Keys`, Python no sabrá qué es `Keys.ENTER` y te dará error.
2. **El método `send_keys()`:**
Este método acepta tanto texto (`"Hola"`) como objetos de la clase Keys. Puedes enviarlos juntos separados por comas.
* `elemento.send_keys("Texto", Keys.ENTER)` → Escribe y pulsa Enter.
* `elemento.send_keys(Keys.TAB)` → Pulsa Tabulador.



### Otras teclas útiles

Aquí tienes una tabla rápida con las teclas más comunes que usarás:

| Comando | Código en Python | Uso común |
| --- | --- | --- |
| **Enter** | `Keys.ENTER` o `Keys.RETURN` | Enviar formularios o búsquedas. |
| **Tabulador** | `Keys.TAB` | Moverse al siguiente campo del formulario. |
| **Espacio** | `Keys.SPACE` | Marcar casillas (checkboxes) o hacer scroll. |
| **Borrar** | `Keys.BACK_SPACE` | Borrar el último carácter escrito. |
| **Escape** | `Keys.ESCAPE` | Cerrar pop-ups o modales. |
| **Flechas** | `Keys.ARROW_DOWN`, `Keys.ARROW_UP` | Moverse por listas desplegables. |

### Truco Pro: Combinaciones de teclas

También puedes usar `Keys` para hacer combinaciones como **Copiar (Ctrl + C)** o **Seleccionar todo (Ctrl + A)**.

```python
# Ejemplo: Seleccionar todo el texto de un input y borrarlo
caja_busqueda.send_keys(Keys.CONTROL, "a") # Ctrl + A
caja_busqueda.send_keys(Keys.DELETE)       # Tecla Suprimir

```

---

¿Te gustaría ver un ejemplo de cómo usar `Keys.TAB` para rellenar un formulario con varios campos sin tener que buscar cada elemento individualmente?