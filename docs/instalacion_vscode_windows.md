# Instalación de Visual Studio Code en Windows

**Fuente oficial:** [visualstudio](https://code.visualstudio.com/) (Guía de instalación en Windows).

> Nota para principiantes: Visual Studio Code (VS Code) es un editor de código ligero pero potente. Estos pasos te guiarán para descargarlo e instalarlo de forma segura en Windows.

---

## 1. Descargar el instalador

1. Abre tu navegador y ve a: [visualstudio](https://code.visualstudio.com/)

2. Haz clic en **Download** y selecciona **Windows** (generalmente verás “User Installer” para Windows 64-bit).

> Consejo: Si no tienes permisos de administrador en tu equipo, descarga la opción **User Installer** (instala solo para tu usuario).

---

## 2. Ejecutar el instalador

1. Cuando termine la descarga, abre el archivo `VSCodeUserSetup-<version>.exe` (doble clic).
2. Si aparece la ventana del instalador, acepta los términos y haz clic en **Next** hasta llegar a las opciones de instalación.

### Opciones importantes (marca según prefieras)

- **Add "Open with Code" action to Windows Explorer file context menu** — agrega opción al menú contextual.
- **Add "Open with Code" action to Windows Explorer directory context menu** — para abrir carpetas con VS Code desde el Explorador.
- **Add to PATH** (agrega `code` al PATH) — permite abrir VS Code desde la terminal usando `code` o `code .`.
- **Register Code as an editor for supported file types** — opcional.

3. Haz clic en **Install** y espera a que finalice la instalación.

---

## 3. Probar que funciona

1. Abre **PowerShell** o **Símbolo del sistema** (cmd) y escribe:

```powershell
code --version
```

o navega a una carpeta y ejecuta:

```powershell
code .
```

2. Si VS Code se abre, ¡ya estás listo!

> Si `code` no funciona inmediatamente, cierra y vuelve a abrir la terminal (el instalador agrega rutas al PATH y la terminal debe reiniciarse).

---

## 4. Sugerencias post-instalación

- Instala la extensión **Python** (si piensas programar en Python) desde el Marketplace dentro de VS Code.  
- Explora la **paleta de comandos** con `Ctrl+Shift+P`.  
- Si trabajas con Linux dentro de Windows, considera usar **WSL** y la extensión **Remote - WSL**.

---

## 5. Problemas comunes y soluciones rápidas

- **No puedes instalar (permiso denegado):** Ejecuta el instalador como administrador (clic derecho → Ejecutar como administrador) o usa la instalación de usuario.  
- **`code` no se reconoce:** Reinicia la terminal; si persiste, marca manualmente la casilla "Add to PATH" y reinstala.

---

**Referencia oficial (instalación en Windows y notas útiles).**

[Regresar a : Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)

[O Regresar a: Instalación de Visual Studio Code &rarr;](visual_studio_code.md)
