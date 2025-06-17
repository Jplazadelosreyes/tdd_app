# tdd_app
# API de Reservas

[![Pruebas API Reservas](https://github.com/Jplazadelosreyes/tdd_app/actions/workflows/testing.yml/badge.svg)](https://github.com/Jplazadelosreyes/tdd_app/actions/workflows/testing.yml)

## 📝 Descripción del Proyecto

Este repositorio contiene el código fuente de una API de Reservas, desarrollada utilizando el enfoque de Desarrollo Guiado por Pruebas (TDD - Test-Driven Development). La API permite a los usuarios gestionar reservas (por ejemplo, de mesas, salas, citas, etc.) de manera eficiente y robusta.

El objetivo principal de este proyecto es demostrar la implementación de una API RESTful con un fuerte énfasis en la calidad del código, la mantenibilidad y la fiabilidad, asegurando que cada funcionalidad esté cubierta por pruebas automatizadas.

## ✨ Características Principales

* **Gestión de Reservas:** Creación, lectura, actualización y eliminación de reservas.
* **API RESTful:** Interfaz bien definida para la interacción con la aplicación.
* **Desarrollo Guiado por Pruebas (TDD):** Código robusto y verificado mediante un conjunto exhaustivo de pruebas unitarias y de integración.
* **Automatización de CI/CD:** Integración y despliegue continuo con GitHub Actions para garantizar la calidad y la entrega ágil.

## 🚀 Tecnologías Utilizadas

* **Python 3.10+**
* **Flask / FastAPI (o framework Python que uses para la API)**: Para la construcción de la API web.
* **pytest**: Framework de pruebas para Python.
* **virtualenv (o venv)**: Para la gestión de entornos virtuales.
* **Git & GitHub:** Control de versiones y alojamiento del repositorio.
* **GitHub Actions:** Para la automatización de CI (pruebas).
* **Otros paquetes de Python** listados en `requirements.txt`.

## 🛠️ Configuración y Ejecución Local

Sigue estos pasos para configurar y ejecutar el proyecto en tu máquina local.

### Prerrequisitos

Asegúrate de tener instalado:
* [Python 3.10 o superior](https://www.python.org/downloads/)
* [Git](https://git-scm.com/downloads)

### Pasos

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/Jplazadelosreyes/tdd_app.git](https://github.com/Jplazadelosreyes/tdd_app.git)
    cd tdd_app # Navega a la raíz del repositorio
    ```

2.  **Navegar a la carpeta del proyecto (si aplica):**
    Dado que tu código fuente principal está en la subcarpeta `sala-reservas`, navega a ella:
    ```bash
    cd sala-reservas
    ```

3.  **Crear y activar un entorno virtual:**
    Es una buena práctica aislar las dependencias del proyecto.
    ```bash
    python -m venv venv
    source venv/bin/activate # En Linux/macOS
    # O para Windows: .\venv\Scripts\activate
    ```

4.  **Instalar dependencias:**
    ```bash
    pip install -r requirements.txt
    ```

5.  **Ejecutar la aplicación (dependerá de tu framework):**
    * **Si usas Flask:**
        ```bash
        # Asegúrate de que FLASK_APP esté configurado para tu punto de entrada (e.g., app/api.py o app/reservas.py)
        export FLASK_APP=app/api.py # O la ruta a tu archivo principal de la app
        flask run
        ```
    * **Si usas FastAPI (con uvicorn):**
        ```bash
        uvicorn app.api:app --reload # Ajusta 'app.api:app' a tu punto de entrada
        ```
    * **O si tienes un script de inicio:**
        ```bash
        python run.py # Si tienes un archivo 'run.py' en la raíz de sala-reservas
        ```
    La API estará disponible generalmente en `http://127.0.0.1:5000` o `http://127.0.0.1:8000`.

## 🧪 Ejecución de Pruebas

Para ejecutar las pruebas automatizadas del proyecto, sigue estos pasos:

1.  Asegúrate de haber configurado el entorno virtual e instalado las dependencias (ver sección anterior).
2.  Desde la carpeta `sala-reservas` (donde está tu carpeta `tests`):
    ```bash
    source venv/bin/activate # Si aún no está activo
    pytest
    ```
    Esto ejecutará todas las pruebas definidas en la carpeta `tests/`.

## ⚙️ Integración Continua (CI) con GitHub Actions

Este proyecto utiliza GitHub Actions para automatizar el proceso de Integración Continua. Cada vez que se realiza un `push` o se abre un `pull request` en cualquier rama, el workflow definido en `.github/workflows/testing.yml` se ejecuta automáticamente para:

1.  Clonar el repositorio.
2.  Configurar un entorno Python 3.10.
3.  Instalar las dependencias del `requirements.txt` (ubicado en `sala-reservas/`).
4.  Ejecutar todas las pruebas del proyecto.

El estado de las pruebas se refleja en la insignia de estado al principio de este `README`.

## 🚀 Despliegue Continuo (CD)

*(**Nota:** Esta sección asume que has configurado un job de despliegue en tu `testing.yml` o en un `cd.yml` separado. Si solo tienes pruebas, puedes omitir o adaptar esta sección.)*

El despliegue de la aplicación se gestiona también mediante GitHub Actions. Actualmente, el despliegue está configurado para:

* **Activación:** Se activa automáticamente al realizar un `push` a la rama `main`, **solo si las pruebas pasan exitosamente.**
* **Plataforma de Despliegue:** [Menciona aquí tu plataforma de despliegue, por ejemplo: Heroku, AWS Elastic Beanstalk, un servidor VPS, etc.]

Para más detalles sobre los comandos de despliegue, consulta el archivo `.github/workflows/testing.yml` (o el `cd.yml` si creaste uno separado).

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Si deseas contribuir a este proyecto, por favor sigue estos pasos:

1.  Haz un "fork" de este repositorio.
2.  Crea una nueva rama para tu característica (`git checkout -b feature/nombre-de-tu-caracteristica`).
3.  Realiza tus cambios y asegúrate de que las pruebas existentes pasen y, si es necesario, añade nuevas pruebas para tus cambios.
4.  Haz commit de tus cambios (`git commit -m 'feat: Añadir nueva característica X'`).
5.  Haz `push` a tu rama (`git push origin feature/nombre-de-tu-caracteristica`).
6.  Abre un Pull Request a la rama `main` de este repositorio.

## 📄 Licencia

Este proyecto está bajo la licencia [MIT License](https://opensource.org/licenses/MIT).

---
