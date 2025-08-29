---
# **Instalación de Visual Studio Code**
## Guía para Windows

**Fuente:** Documentación oficial de VS Code

---

## **¿Qué es VS Code?**

Es un editor de código ligero pero potente. Esta guía te ayudará a instalarlo de forma segura en tu equipo.

---

## **Paso 1: Descargar el Instalador**

1.  Abre tu navegador y ve a la página oficial:
    **https://code.visualstudio.com/**

2.  Haz clic en el botón de descarga para **Windows**.

> **Consejo:** Elige la opción **User Installer** si no tienes permisos de administrador.

---

## **Paso 2: Ejecutar el Instalador**

1.  Una vez descargado, abre el archivo `VSCodeUserSetup-<version>.exe`.
2.  Acepta el acuerdo de licencia y haz clic en **"Next"** en las siguientes ventanas.

---

## **Paso 2 (cont.): Opciones de Instalación**

En la pantalla "Select Additional Tasks", te recomiendo marcar estas casillas para una mejor experiencia:

-   ✅ **Add "Open with Code" action...** (ambas opciones para archivos y carpetas).
-   ✅ **Add to PATH** (muy importante para usarlo desde la terminal).

Luego, haz clic en **Install**.

---

## **Paso 3: Probar que Funciona**

1.  Abre una nueva terminal (**PowerShell** o **cmd**).
2.  Escribe el siguiente comando para verificar la versión:

```powershell
code --version