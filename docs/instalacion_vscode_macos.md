# Instalación de Visual Studio Code en macOS

**Fuente oficial:** [visualstudio](https://code.visualstudio.com/) (Guía de instalación en macOS).

> Nota para principiantes: en macOS instalarás una app (.dmg) y, opcionalmente, añadirás el comando `code` al PATH para abrir VS Code desde la Terminal.

---

## 1. Descargar

1. Abre tu navegador y ve a [visualstudio](https://code.visualstudio.com/)

2. Haz clic en **Download** y selecciona **macOS** (verás la opción *Universal* que funciona en Intel y Apple Silicon).

---

## 2. Instalar la aplicación

1. Abre el archivo descargado (`.dmg`) haciendo doble clic.  

2. Arrastra **Visual Studio Code.app** a la carpeta **Applications** (esto instala la app para todos los usuarios del equipo).

---

## 3. Añadir el comando `code` al PATH (para usar desde Terminal)

**Opción rápida (recomendada):** desde VS Code:

1. Abre VS Code (desde Applications).  

2. Abre la **Paleta de comandos** con `Cmd+Shift+P`.  

3. Escribe y ejecuta: **Shell Command: Install 'code' command in PATH**.  

4. Cierra y vuelve a abrir la Terminal.

**Opción manual:** (si prefieres editar tu perfil)

- Para Zsh (macOS moderno):

```bash
cat << 'EOF' >> ~/.zprofile
# Add Visual Studio Code (code)
export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
EOF
```

- Para Bash:

```bash
cat << 'EOF' >> ~/.bash_profile
# Add Visual Studio Code (code)
export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
EOF
```

Luego abre una nueva Terminal y prueba:

```bash
code --version
code .
```

---

## 4. Recomendaciones post-instalación

- Mantén VS Code actualizado (tiene actualizaciones automáticas).  
- Instala extensiones (Python, GitLens, etc.) desde el Marketplace.  
- Si tu Mac tiene Apple Silicon (M1/M2), la versión **Universal** funciona bien; también puedes elegir builds específicos si deseas.

---

## 5. Problemas comunes

- **Diálogos de privacidad en macOS Catalina/Mojave:** macOS puede pedir permisos para acceder a calendario/contactos/fotos. Puedes elegir *Don't Allow* si no quieres dar acceso.  
- **`code` no funciona:** asegúrate de haber ejecutado el comando de la paleta o haber agregado la línea al archivo de perfil y de haber abierto una nueva Terminal.

---

**Referencia oficial (instalación en macOS).**

[Regresar a : Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)

[O Regresar a: Instalación de Visual Studio Code &rarr;](visual_studio_code.md)
