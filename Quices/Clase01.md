## Actividad de Clase: Analizando Agentes de IA con Hugging Face Spaces

### 1. Nombre del Space
**Nombre:** Krea 2 Outpaint

**Enlace:** https://huggingface.co/spaces/yijunwang2/krea2-outpaint

### 2. ¿Qué hace el agente?
La funcion principal del agente es extender los bordes de una imagen existente para que quede mas amplia.
A diferencia de una generacion de imagen normal, el agente mantiene los pixeles de la foto que fue enviada como input, y a partir del prompt amplia la immagen al ratio deseado.

### 3. Análisis PEAS
**Performance:**
- Que los pixeles nuevos de la imagen se integren bien con la original.
- Que la extension de la imagen cumpla con el ratio y el prompt enviado por el usuario.
- Que no haya distorsiones en la imagen generada.
- Que el tiempo de respuesta no sea muy largo.

**Environment:**
- Con la interfaz de hugging face y servidores.
- Con los archivos enviados por el usuario.
- Con el prompt del usuario

**Actuators:**
- Genera una nueva imagen con mayores dimensiones que la original manteniendo los pixeles.
- Duevuelve la imagen al usuario a traves de la interfaz 

### 4. Clasificación del entorno
Complete la siguiente tabla y justifique brevemente cada respuesta.

Propiedad Clasificación Justificación

Observable Total / Parcial
Determinista Sí / No
Episódico Sí / No
Estático Sí / No
Discreto Sí / No
Conocido Sí / No

### 5. ¿Qué tipo de programa de agente creen que es?
Seleccione la opción que consideren más adecuada y explique por qué.

Agente de reflejo simple
Agente basado en modelo
Agente basado en objetivos
Agente basado en utilidad
Agente con aprendizaje
Importante: No existe una única respuesta correcta. Lo importante es justificar la elección a partir del comportamiento observado.

Discusión en clase
Después de las presentaciones, discutiremos preguntas como:

¿Dos Spaces diferentes pueden compartir el mismo tipo de entorno?
¿Es posible saber con certeza qué tipo de agente implementa un Space únicamente observándolo?
¿Qué diferencia existe entre el comportamiento observable de un agente y su implementación interna?
Reto adicional
Encuentre un Space que pueda clasificarse como:

Totalmente observable, determinista y episódico.
Parcialmente observable, estocástico y secuencial.
Justifique su respuesta.