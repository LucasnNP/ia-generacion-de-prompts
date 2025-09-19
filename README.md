# Proyecto Final – Inteligencia Artificial: Generación de Prompts

**Alumno:** Lucas Prat  
**Comisión:** [86185]  
**Nombre del Proyecto:** Kalma – Generación de menús y recursos visuales con IA

---

## Introducción

El presente proyecto se desarrolla en el marco del curso **Inteligencia Artificial: Generación de Prompts**.  
El objetivo es resolver una problemática real: el tiempo que los nutricionistas dedican a la creación de **menús personalizados** y de **materiales visuales atractivos** para sus pacientes.

Esto se conecta con **Kalma**, una plataforma digital en desarrollo para nutricionistas.

Para la solución utilizaremos:

- **Gemini** como modelo de Texto → Texto.
- **Stable Diffusion** como plataforma de Texto → Imagen.

Se aplicará la técnica de **Fast Prompting**, optimizando la generación de menús y prompts visuales en un solo flujo.

---

## Presentación del problema

En la práctica clínica de los nutricionistas, una de las tareas más demandantes y repetitivas es la
creación de menús personalizados para sus pacientes. Cada menú debe adaptarse a variables
como: edad, peso, condición de salud, cultura alimentaria, preferencias personales, objetivos
nutricionales y restricciones económicas.

Actualmente, muchos profesionales dedican tiempo excesivo a esta tarea, lo que reduce las horas
disponibles para la atención personalizada y el acompañamiento del paciente.

Además, los pacientes suelen recibir estos planes en formato texto, lo que dificulta la comprensión o
la motivación para seguirlos. La falta de recursos visuales y de una comunicación clara afecta la
adherencia a los tratamientos.

Por estas razones, existe una necesidad concreta de herramientas que automaticen la generación de
menús, hagan más eficiente el trabajo del nutricionista y ofrezcan una experiencia más clara,
atractiva y motivadora para el paciente.

---

## Desarrollo de la propuesta de solución

La propuesta es integrar en Kalma (plataforma digital para nutricionistas) un sistema basado en
generación de prompts, que permita:

1. Generación de menús personalizados (texto-texto):
   A partir de los datos del paciente, un modelo de IA podrá generar un menú adaptado:

   - Datos clínicos: edad, peso, patologías, objetivos (ej. bajar colesterol).
   - Contexto cultural: comidas típicas de la región.
   - Preferencias personales: vegetarianismo, intolerancias, presupuesto disponible.
   - El nutricionista recibe una propuesta inicial que puede ajustar antes de entregar al paciente.

2. Representación visual de menús (texto-imagen):Generar ilustraciones o imágenes de los platos sugeridos, para que el paciente pueda visualizar cómo luce una porción balanceada. Crear infografías sencillas (ej. plato saludable dividido en proteínas, carbohidratos y vegetales).

---

## Objetivos

- Generar menús personalizados de forma automática y contextualizada.
- Crear prompts optimizados para generar imágenes educativas en Nightcafe.
- Implementar la técnica de **Fast Prompting** para reducir la cantidad de consultas necesarias.
- Validar la viabilidad técnica de la propuesta en un flujo simple y replicable.

---

## Metodología

El proyecto se llevará a cabo en un entorno de trabajo basado en **Jupyter Notebook**, alternando celdas de Markdown (para la explicación conceptual) con celdas de código en Python (para la implementación práctica). La metodología se estructura en cinco etapas principales:

1. **Definición del problema y contexto**  
   Se presenta la problemática de los nutricionistas que requieren generar menús personalizados y materiales visuales educativos para sus pacientes. Esta etapa incluye la justificación de la relevancia del problema y la conexión con la plataforma Kalma.

2. **Diseño y experimentación de prompts en Gemini (Texto → Texto)**  
   Se diseñarán distintos tipos de prompts para la generación de menús:

   - **Zero-shot prompting**: se da únicamente la instrucción, sin ejemplos previos.
   - **One-shot prompting**: se incluye un ejemplo de menú como guía.
   - **Few-shot prompting**: se incluyen varios ejemplos de menús como referencia.

   Esto permitirá comparar qué metodología produce resultados más relevantes y consistentes para el caso de uso de nutricionistas.

3. **Generación de imágenes con Stable Diffusion (Texto → Imagen)**  
   A partir de los menús generados en Gemini, se construyen prompts optimizados en inglés y se utilizan con el modelo **Stable Diffusion**, integrado mediante la librería **diffusers**. Esto permitirá producir representaciones visuales **realistas, educativas y coherentes** con los menús generados.

4. **Implementación de Fast Prompting**  
   Se aplica la técnica de **Fast Prompting**, integrando en un único prompt tanto la generación del menú como la creación de los prompts visuales. De este modo se reduce la cantidad de consultas al modelo, optimizando tiempos y recursos.

   Finalmente, se validan los resultados comparando:

   - Zero-shot, One-shot y Few-shot prompting.
   - Prompts separados vs. Fast Prompting.

   Esto permitirá determinar la configuración más eficiente y precisa para el problema planteado.

### Justificación de la metodología

Este enfoque permite:

- **Evaluación comparativa**: probar distintas metodologías de prompting asegura elegir la más adecuada para el caso de uso.
- **Replicabilidad**: cualquier usuario puede ejecutar la notebook y obtener resultados personalizados.
- **Optimización**: el uso de Fast Prompting minimiza la cantidad de consultas al modelo, reduciendo costos y tiempos de procesamiento.

---

## Comparativa

La comparativa es mostrada en el POC que se incluye en este proyecto.

---

## Herramientas y Tecnologías

En este proyecto se utilizan las siguientes herramientas:

- **Gemini (Texto → Texto)**: modelo de lenguaje de Google para generar menús personalizados y prompts de imágenes.
- **Stable Diffusion (Texto → Imagen)**: plataforma para transformar los prompts generados en representaciones visuales educativas de los platos.

### Técnicas de prompting utilizadas

1. **Zero-shot prompting**  
   Útil para obtener resultados rápidos sin ejemplos. Permite evaluar la capacidad base del modelo.  
   _Limitación_: la consistencia no siempre es alta.

2. **One-shot prompting**  
   Se incluye un ejemplo de referencia, lo cual ayuda a orientar mejor el formato de salida.  
   _Ventaja_: resultados más consistentes y alineados con la estructura deseada.

3. **Few-shot prompting**  
   Al dar múltiples ejemplos, el modelo entiende mejor el estilo esperado.  
   _Ventaja_: mayor control sobre el resultado.  
   _Limitación_: mayor extensión en el prompt, lo que puede aumentar costos.

4. **Fast Prompting**  
   Se integra en un único prompt la generación de menús y de los prompts para Stable Diffusion.  
   _Ventaja_: reduce la cantidad de consultas, optimiza tiempo y recursos.

### Justificación

Se utilizan estas técnicas en conjunto para:

- Evaluar cuál entrega resultados más relevantes y consistentes para el caso de uso.
- Optimizar la generación de menús y materiales visuales en un único flujo.
- Asegurar la viabilidad del proyecto con la menor cantidad de consultas posibles.

---

## Implementación

La implementación es mostradaa en el POC que se incluye en este proyecto luego de la comparativa.

---

## Resultados

La implementación permitió integrar la generación de contenidos con inteligencia artificial (Gemini) y la creación de imágenes realistas con Stable Diffusion en un flujo automatizado.

- Se logró que el modelo genere menús personalizados para un perfil de paciente con hipertensión y, a partir de ese contenido, se obtengan prompts optimizados en inglés adecuados para la generación de imágenes.
- Las imágenes producidas, si bien presentaron algunos ajustes necesarios en los prompts para mejorar la coherencia, reflejan de manera atractiva y educativa la propuesta alimenticia.
- El sistema cumple con la solución esperada, ya que automatiza el proceso de:
  1.  Obtener recomendaciones nutricionales.
  2.  Transformarlas en prompts de calidad.
  3.  Generar imágenes que complementan y enriquecen la presentación de esas recomendaciones.

Esto demuestra que la implementación es viable, funcional y escalable hacia un producto digital aplicado a nutrición.

---

## Conclusiones

- Se cumplieron los objetivos propuestos: integrar un modelo de lenguaje y un generador de imágenes en un flujo de trabajo coherente, con un enfoque educativo y visualmente atractivo.
- El proyecto permitió comprobar la importancia de diseñar prompts claros y específicos (fast prompting) para obtener resultados de mayor calidad y evitar ambigüedades en las imágenes.
- Trabajar con entornos (Jupyter, Visual Studio Code, Anaconda) mostró la necesidad de tener una correcta gestión de dependencias y compatibilidades técnicas, lo cual es clave en proyectos de IA.
- Como conclusión general, el proyecto demuestra el potencial de la IA para apoyar a profesionales de la salud, ofreciendo materiales personalizados que combinan texto e imagen para mejorar la comprensión y el impacto en los pacientes.

---

## Referencias

- Google AI Studio – Documentación oficial de Gemini.
- Hugging Face – Diffusers Library (Stable Diffusion Pipeline).
- Documentación de Anaconda y Visual Studio Code para gestión de entornos de Python.
- Recursos recomendados para generación de imágenes: Stable Diffusion, Crayion, Nightcafe.
