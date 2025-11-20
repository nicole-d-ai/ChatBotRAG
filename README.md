# ✨ Chatbot RAG con Mistral + ChromaDB

Este proyecto implementa un chatbot inteligente utilizando la arquitectura RAG (Retrieval-Augmented Generation), donde un modelo LLM genera respuestas basadas en mi propia base de conocimientos.

Fue desarrollado como trabajo práctico de la materia Procesamiento del habla.

🚀 ¿Qué hace este proyecto?

✔️ Construye un chatbot capaz de responder preguntas sobre una app de oficios
✔️ Usa una base de Q&A creada manualmente
✔️ Implementa RAG para recuperar información relevante
✔️ Compara dos modelos de embeddings
✔️ Evalúa la calidad del chatbot con métricas de recuperación
✔️ Genera respuestas usando un modelo LLM de HuggingFace

🧠 Arquitectura utilizada
🔍 1. Recuperación (Retrieval)

Se utiliza ChromaDB como base vectorial.
Los textos se vectorizan usando dos modelos:

🟢 MiniLM-L6-v2

🟣 Jina Embeddings v2 Base ES

Cada uno genera una colección distinta para poder compararlos.

📝 2. Generación (Generation)

Para generar las respuestas finales se usa:

🦙 Mistral-7B-Instruct v0.2

El LLM recibe:

la pregunta del usuario

📚 Dataset

Se construyeron dos datasets:

* Base de conocimiento: ~20 preguntas reales de clientes y profesionales

* Dataset de evaluación: nuevas preguntas creadas para testear recuperación

📦 Librerías principales

* transformers — modelos LLM y tokenizers

* sentence-transformers — embeddings

* chromadb — base de datos vectorial

* torch — tensores y device mapping

* numpy, pandas — soporte general

🧪 Evaluación del Chatbot

Se midieron:

* Context Precision

* Context Recall

* Resultados promedio (k=3):

* Precision ≈ 0.28

* Recall ≈ 0.85

📌 MiniLM y Jina recuperaron chunks con rendimiento similar, pero MiniLM generó respuestas más naturales y útiles, por lo que se eligió como embedding final.

🏁 Conclusión

El proyecto demuestra cómo integrar:

* una base de conocimiento propia

* modelos de embeddings

* ChromaDB

* un LLM moderno

…para construir un chatbot funcional con arquitectura RAG.
La mejor combinación encontrada fue:

👉 MiniLM-L6-v2 + Mistral-7B-Instruct

🙌 Autor

Nicole Desire Ferreyra — Ciencia de Datos e IA
GitHub: nicole-d-ai

los k chunks más relevantes recuperados

un prompt instructivo para responder claro y corto
