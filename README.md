# Automatización de Gestión de Leads (Diseño de Producto y Marca)

Este repositorio contiene la arquitectura, el flujo y las evidencias de un sistema automatizado creado para gestionar el ingreso, clasificación y respuesta de clientes potenciales (Leads) mediante inteligencia artificial.

## 🛠️ Stack Tecnológico
* **Trigger & Canal de Salida:** Gmail
* **Orquestador:** n8n
* **Inteligencia Artificial:** Modelo OpenRouter (Análisis de intención comercial)
* **Base de Datos:** Airtable
* **Control Humano (HITL):** Aprobación/Rechazo vía Email

## ⚙️ ¿Cómo funciona?
1. **Captura:** El flujo "escucha" nuevos correos entrantes, filtrando automáticamente el spam y notificaciones automatizadas.
2. **Procesamiento de IA:** Un agente de IA analiza el asunto y cuerpo del mensaje, extrayendo el nombre del cliente y clasificando la intención (VIP, Consulta, Cotización, Descartar, etc.).
3. **Drafting:** La IA redacta un borrador de respuesta totalmente personalizado según la categoría del lead.
4. **Alerta HITL (Human-in-the-loop):** El sistema pausa la ejecución y envía un correo interno con los datos del lead y el borrador propuesto.
5. **Decisión:** 
   * Si se responde **APROBADO**: El sistema genera el borrador en el hilo original de Gmail y actualiza Airtable a "Enviado".
   * Si se responde **RECHAZADO**: El sistema descarta el lead en Airtable.
   
## 📂 Estructura de este Repositorio
* `arquitectura.pdf`: Diagrama visual del ecosistema.
* `flujo/workflow.json`: El blueprint importable para n8n.
* `evidencias/`: Capturas de pantalla de los pasos clave y el camino infeliz (resiliencia).
* `enlaces.md`: Links a la base de datos en modo lectura y al video demostrativo.
