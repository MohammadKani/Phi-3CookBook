# Usa OpenAI SDK con Phi-3 en Azure AI y Azure ML

Usa `openai` SDK para consumir implementaciones de Phi-3 en Azure AI y Azure ML. La familia de modelos Phi-3 en Azure AI y Azure ML ofrece una API compatible con la API de Chat Completion de OpenAI. Permite a los clientes y usuarios pasar sin problemas de los modelos de OpenAI a los LLMs de Phi-3.

La API puede usarse directamente con las bibliotecas cliente de OpenAI o herramientas de terceros, como LangChain o LlamaIndex.

El ejemplo a continuación muestra cómo hacer esta transición utilizando la Biblioteca de Python de OpenAI. Nota que Phi-3 solo soporta la API de chat completions.

Para usar el modelo Phi-3 con el SDK de OpenAI, necesitarás seguir algunos pasos para configurar tu entorno y hacer llamadas a la API. Aquí tienes una guía para ayudarte a comenzar:

1. **Instalar el SDK de OpenAI**: Primero, necesitarás instalar el paquete de Python de OpenAI si aún no lo has hecho.
   ```bash
   pip install openai
   ```

2. **Configurar tu clave API**: Asegúrate de tener tu clave API de OpenAI. Puedes configurarla en tus variables de entorno o directamente en tu código.
   ```python
   import openai

   openai.api_key = "your-api-key"
   ```

3. **Hacer llamadas a la API**: Usa el SDK de OpenAI para interactuar con el modelo Phi-3. Aquí tienes un ejemplo de cómo hacer una solicitud de completación:
   ```python
   response = openai.Completion.create(
       model="phi-3",
       prompt="Hello, how are you?",
       max_tokens=50
   )

   print(response.choices[0].text.strip())
   ```

4. **Manejar las respuestas**: Procesa las respuestas del modelo según sea necesario para tu aplicación.

Aquí tienes un ejemplo más detallado:
```python
import openai

# Set your API key
openai.api_key = "your-api-key"

# Define the prompt
prompt = "Write a short story about a brave knight."

# Make the API call
response = openai.Completion.create(
    model="phi-3",
    prompt=prompt,
    max_tokens=150
)

# Print the response
print(response.choices[0].text.strip())
```

Esto generará una historia corta basada en el prompt proporcionado. Puedes ajustar el parámetro `max_tokens` para controlar la longitud de la salida.

[Ver un ejemplo completo de Notebook para modelos Phi-3](https://github.com/Azure/azureml-examples/blob/main/sdk/python/foundation-models/phi-3/openaisdk.ipynb)

Revisa la [documentación](https://learn.microsoft.com/azure/ai-studio/how-to/deploy-models-phi-3?WT.mc_id=aiml-137032-kinfeylo) de la familia de modelos Phi-3 en AI Studio y ML Studio para obtener detalles sobre cómo aprovisionar puntos finales de inferencia, disponibilidad regional, precios y referencia de esquema de inferencia.

**Descargo de responsabilidad**: 
Este documento ha sido traducido utilizando servicios de traducción automática basados en inteligencia artificial. Si bien nos esforzamos por lograr precisión, tenga en cuenta que las traducciones automatizadas pueden contener errores o imprecisiones. El documento original en su idioma nativo debe considerarse la fuente autorizada. Para información crítica, se recomienda la traducción humana profesional. No somos responsables de ningún malentendido o interpretación errónea que surja del uso de esta traducción.