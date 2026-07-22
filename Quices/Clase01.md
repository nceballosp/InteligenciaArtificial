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

**Sensors:**
- Imagen de entrada 
- Prompt del usuario
- Informacion espacial de la nueva imagen

### 4. Clasificación del entorno

**Observable:** Total, el agente tiene acceso completo a todo el entorno en el momento de tomar la decision.

**Determinista:** No, dada la misma entrada, el modelo producira variaciones distintas en cada ejecucion

**Episódico:** Sí, cada solicitud de outpainting es un episodio independiente.

**Estático:** Sí, el entorno no cambia mientras el agente está procesando la salida.

**Discreto:** Sí, la entrada y salida son estructuras matriciales con valores numéricos discretos.

**Conocido:** Sí, las reglas del entorno son conocidas por los creadores.

### 5. ¿Qué tipo de programa de agente creen que es?

**Agente basado en objetivos**
- Tiene un objetivo explicito para alcanzar, toda el modelo se dirige a hacer el lienzo con las especificaciones dadas.
- Para rellenar los bordes, el agente debe analizar la estructura interna de la imagen de entrada. Utiliza esto para que el resultado sea consistente.
- No opera con reglas fijas precalculadas.
- El modelo evalua que pixeles son mejores según la guía, buscando maximizar la calidad.


### 6.Reto adicional
**Totalmente observable, determinista y episódico:** https://huggingface.co/spaces/baidu/Unlimited-OCR (Unlimited OCR)

- Observable: El agente tiene acceso a toda la informacion relevante de la tarea de forma inmediata. No existen variables del documento mientras procesa.

- Determinista: Dadas las mismas entradas del modelo, el resultado siempre será identico. Los algoritmos OCR no usan semillas de aleatorio en su inferencia.

- Episódico: Cada archivo subido es independiente. El procesamiento del documento actual no afecta la lectura del siguiente.

**Parcialmente observable, estocástico y secuencial:** https://huggingface.co/spaces/mlabonne/chessllm (Chess LLM)

- Parcialmente Observable: Aunque el tablero de ajedrez es completamente visible, la estrategia y plan a largo plazo del jugador humano estan ocultos para la IA. 

- Estocástico: El entorno incluye a un oponente humano cuya conducta no es predecible. Los LLMs aplicados a juegos suelen incluir un margen de aleatoriedad para que no jueguen siempre la misma partida.

- Secuencial: Cada movimiento que realiza el agente altera el estado del tablero para los turnos siguientes.