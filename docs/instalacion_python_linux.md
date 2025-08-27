# Instalación de Python en Linux (Ubuntu/Debian)

Este documento describe paso a paso cómo instalar **Python** en Linux (ejemplo: Ubuntu/Debian).

---

## 1. Verificar si Python está instalado

Abra la terminal y ejecute:

```bash
python3 --version
```

Si aparece una versión (ejemplo `Python 3.10.12`), ya está instalado.

---

## 2. Actualizar los repositorios

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 3. Instalar Python

```bash
sudo apt install -y python3 python3-pip
```

Verifique la instalación:

```bash
python3 --version
pip3 --version
```

---

## 4. Instalar dependencias adicionales (opcional)

Algunas bibliotecas necesitan herramientas de desarrollo:

```bash
sudo apt install -y build-essential libssl-dev libffi-dev python3-dev
```

---

## 5. Actualizar Python y pip

Actualizar pip:

```bash
pip3 install --upgrade pip
```

En Ubuntu, para tener la última versión de Python, puede usar el repositorio de **deadsnakes**:

```bash
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.12
```

Verificar la versión instalada:

```bash
python3.12 --version
```

---

✅ Ahora Python está listo para usarse en Linux.

[Regresar a : Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)

[O continuar con: Instalar Visual Studio Code &rarr;](visual_studio_code.md)
