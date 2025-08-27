# Instalación de Visual Studio Code en Linux

**Fuente oficial:** [visualstudio](https://code.visualstudio.com/) (Guía de instalación en Linux).

> Nota para principiantes: hay paquetes listos para usar (.deb, .rpm) y repositorios oficiales que permiten actualizar automáticamente VS Code con el gestor de paquetes del sistema.

---

## 1. Comprobar si tu distribución ya tiene VS Code

Algunas distribuciones permiten instalar desde el centro de software. Si no, sigue los pasos según tu tipo de distro.

---

## 2. Debian / Ubuntu (y derivadas) — forma sencilla (.deb)

1. Descarga el paquete `.deb` desde [visualstudio](https://code.visualstudio.com/)  

2. Instala con la interfaz gráfica (doble clic) o por terminal:

```bash
sudo apt install ./<archivo>.deb
```

- Si tu sistema es muy antiguo, puedes usar:

```bash
sudo dpkg -i <archivo>.deb
sudo apt-get install -f
```

### Repositorio (para actualizaciones automáticas)

Para añadir el repositorio oficial y la clave (recomendado):

```bash
# Instala dependencias necesarias
sudo apt-get install wget gpg apt-transport-https -y

# Importa la llave
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -o root -g root -m 644 microsoft.gpg /usr/share/keyrings/microsoft.gpg
rm -f microsoft.gpg

# Agrega el repositorio
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list

# Actualiza e instala
sudo apt update
sudo apt install code
```

---

## 3 RHEL / Fedora / CentOS (RPM)

Instala la llave y el repositorio y luego usa `dnf` o `yum`:
```bash
# Importar llave
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Agregar repo (ejemplo para dnf)
echo -e "[code]
name=Visual Studio Code
baseurl=https://packages.microsoft.com/yumrepos/vscode
enabled=1
autorefresh=1
type=rpm-md
gpgcheck=1
gpgkey=https://packages.microsoft.com/keys/microsoft.asc" | sudo tee /etc/yum.repos.d/vscode.repo

# Instalar
sudo dnf check-update
sudo dnf install code
```

---

## 4. Probar y usar

- Abre VS Code desde el menú de aplicaciones o con:

```bash
code --version
code .
```

---

## 5. Problemas comunes

- **Falta de dependencias:** si la instalación con `dpkg` falla, ejecuta `sudo apt-get install -f` para resolver dependencias.

- **Actualizaciones:** usar el repositorio oficial asegura que `apt`/`dnf` pueda actualizar VS Code automáticamente.

---

**Referencia oficial (instalación en Linux y repositorios).**

[Regresar a : Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)

[O Regresar a: Instalación de Visual Studio Code &rarr;](visual_studio_code.md)
