# Instalación de Python en macOS

Este documento describe paso a paso cómo instalar **Python** en macOS.

---

## 1. Verificar si Python está instalado

Abra la aplicación **Terminal** y ejecute:

```bash
python3 --version
```

Si aparece una versión (por ejemplo, `Python 3.9.6`), significa que ya está instalado.  
Si no, siga los pasos siguientes.

---

## 2. Instalar Homebrew (si no lo tiene)

Homebrew es el gestor de paquetes más usado en macOS.  
Para instalarlo, ejecute en **Terminal**:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Luego agregue Homebrew al PATH (si aún no está):

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

---

## 3. Instalar Python con Homebrew

```bash
brew install python
```

Una vez finalizado, verifique la versión instalada:

```bash
python3 --version
```

---

## 4. Instalar pip (si no viene incluido)

Normalmente `pip` ya está disponible con la instalación.  
Verifique con:

```bash
pip3 --version
```

Si no está, instálelo con:

```bash
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py
```

---

## 5. Actualizar Python y pip

Para mantener Python actualizado:

```bash
brew upgrade python
```

Para actualizar pip:

```bash
pip3 install --upgrade pip
```

---

✅ Ahora Python está listo para usarse en macOS.

[Regresar a : Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)

[O continuar con: Instalar Visual Studio Code &rarr;](visual_studio_code.md)
