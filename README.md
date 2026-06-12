
# 🤖 OpenClaw Telegram Agent (Local LLM Orchestration)

Este proyecto es una implementación de un agente de Inteligencia Artificial autónomo que se ejecuta de manera 100% local, orquestado a través de **OpenClaw** y **Ollama**, y expuesto a través de la API de bots de **Telegram** para su control remoto.

##  Arquitectura y Stack Tecnológico

*   **Framework de Agentes:** [OpenClaw](https://github.com/openclaw/openclaw) - Utilizado para la lógica de razonamiento y ejecución de tareas.
*   **Motor de Inferencia Local:** [Ollama](https://ollama.com/) - Encargado de correr el modelo de lenguaje de forma eficiente aprovechando los recursos de hardware local.
*   **Modelo de Lenguaje:** Gamma4 - Desplegado a través de Ollama.
*   **Interfaz de Usuario:** Telegram Bot API - Actúa como el cliente/frontend para interactuar con el agente desde cualquier dispositivo sin exponer la infraestructura local directamente.
*   **Entorno:** Windows Core / Python.

##  Características Principales

*   **Privacidad Total:** Al correr la inferencia de manera local con Ollama, ningún dato (prompts o respuestas) sale a servidores de terceros.
*   **Ejecución Autónoma:** Gracias a OpenClaw, el bot no solo responde a estímulos directos (chat), sino que puede razonar y estructurar pasos para resolver la consulta del usuario.
*   **Baja Latencia de Interfaz:** La conexión directa entre el script de Python local y el webhook/polling de Telegram permite una interacción fluida.

##  Requisitos Previos (Prerequisites)

Para levantar este proyecto en un entorno Windows, necesitas:

1.  Python 3.8 o superior.
2.  [Ollama para Windows](https://ollama.com/download/windows) instalado y corriendo en segundo plano.
3.  El modelo Gamma4 descargado en Ollama (`ollama run gamma4` o el nombre específico del tag que utilizaste).
4.  Un Token de Bot de Telegram (obtenido a través de @BotFather).

##  Instalación y Configuración

1. **Clonar el repositorio:**
```bash
   git clone [https://github.com/keefvampire/openclaw-telegram-agent.git](https://github.com/keefvampire/openclaw-telegram-agent.git)
   cd openclaw-telegram-agent

2. Instalar dependencias:

Bash
   pip install -r requirements.txt

Configurar variables de entorno:
Crea un archivo .env en la raíz del proyecto y añade tus credenciales:

TELEGRAM_BOT_TOKEN="TU_TOKEN_AQUI"
   OLLAMA_HOST="http://localhost:11434"

   4. Ejecutar agente
python main.py
