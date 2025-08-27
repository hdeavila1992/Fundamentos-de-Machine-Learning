# Instalación de Python en Windows

Este tutorial explica **paso a paso** cómo instalar Python en Windows.  
Está basado en la [documentación oficial de Python](https://www.python.org/).

!!! note  Si tienes otro sitema operativo mira los siguiente tutoriales:

* [Instrucciones para macOS](instalacion_python_macos.md)
* [Instrucciones para Linux](instalacion_python_linux.md)

---

## 1. Descargar Python

1. Abre tu navegador web (por ejemplo: Edge, Chrome o Firefox).  
2. Escribe en la barra de búsqueda: [https://www.python.org](https://www.python.org).  
3. En la página principal, haz clic en el menú **Downloads**.  
4. Automáticamente, el sitio te recomendará la última versión de Python para Windows.  
   - Ejemplo: *Download Python 3.x.x*  
5. Haz clic en el botón de descarga.

📌 Esto descargará un archivo ejecutable con extensión `.exe`.

---

## 2. Ejecutar el instalador

1. Busca el archivo descargado en tu carpeta de **Descargas**.  
   Ejemplo: `python-3.x.x-amd64.exe`.  
2. Haz **doble clic** sobre el archivo para iniciar el instalador.

---

## 3. Configurar la instalación

Cuando se abra la ventana del instalador:

1. Marca la casilla que dice:  
   **"Add Python 3.x to PATH"**  
   (esto es muy importante, ya que permite usar Python desde la terminal).  
2. Luego, haz clic en el botón:  
   **"Install Now"**.

El instalador comenzará a copiar los archivos. Espera unos minutos.

---

## 4. Confirmar la instalación

1. Una vez termine la instalación, abre la aplicación **Símbolo del sistema**:  
   - Presiona `Windows + R`.  
   - Escribe `cmd` y presiona **Enter**.  
2. En la ventana negra que aparece, escribe:

```bash
python --version
```

3. Si todo salió bien, deberías ver un mensaje como:

```python
Python 3.x.x
```

---

## 5. Instalar `pip` (gestor de paquetes)

En versiones recientes de Python, `pip` ya viene instalado. Para comprobarlo:

```bash
pip --version
```

Si aparece un número de versión, ya tienes `pip`.  
Si no aparece, puedes instalarlo manualmente siguiendo la [guía oficial de pip](https://pip.pypa.io/en/stable/installation/).

---

## 🎉 ¡Listo!

Ahora tienes Python instalado en tu computadora con Windows.  
Puedes comenzar a programar y ejecutar tus primeros scripts.

---

!!! video "🎥 Video: Cómo Descargar e Instalar Python"

    <iframe width="100%" height="315" 
    src="https://www.youtube.com/embed/QHA6_39dTTk" 
    frameborder="0" allowfullscreen></iframe>
---

[Regresar a : Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)

[O continuar con: Instalar Visual Studio Code &rarr;](visual_studio_code.md)

