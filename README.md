<div align="center">

# Pathway AI Pipelines


Pathway's **AI Pipelines** allow you to quickly put in production AI applications that offer **high-accuracy RAG and AI enterprise search at scale** using the most **up-to-date knowledge** available in your data sources. It provides you ready-to-deploy **LLM (Large Language Model) App Templates**. You can test them on your own machine and deploy on-cloud (GCP, AWS, Azure, Render,...) or on-premises.

The apps connect and sync (all new data additions, deletions, updates) with data sources on your **file system, Google Drive, Sharepoint, S3, Kafka, PostgreSQL, real-time data APIs**. They come with no infrastructure dependencies that would need a separate setup. They include **built-in data indexing** enabling vector search, hybrid search, and full-text search - all done in-memory, with cache.


## Application Templates

The application templates provided in this repo scale up to **millions of pages of documents**. Some of them are optimized for simplicity, some are optimized for amazing accuracy. Pick the one that suits you best. You can use it out of the box, or change some steps of the pipeline - for example, if you would like to add a new data source, or change a Vector Index into a Hybrid Index, it's just a one-line change. 

| Application (template)                                                                           | Description                                                                                                                                                                                                                                                                                                                                                         |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`Question-Answering RAG App`](examples/pipelines/demo-question-answering/)    | Basic end-to-end RAG app. A question-answering pipeline that uses the GPT model of choice to provide answers to queries to your documents (PDF, DOCX,...) on a live connected data source (files, Google Drive, Sharepoint,...). You can also try out a [demo REST endpoint](https://pathway.com/solutions/rag-pipelines#try-it-out).              |
| [`Live Document Indexing (Vector Store / Retriever)`](examples/pipelines/demo-document-indexing/)     | A real-time document indexing pipeline for RAG that acts as a vector store service. It performs live indexing on your documents (PDF, DOCX,...) from a connected data source (files, Google Drive, Sharepoint,...). It can be used with any frontend, or integrated as a retriever backend for a [Langchain](https://pathway.com/blog/langchain-integration) or [Llamaindex](https://pathway.com/blog/llamaindex-pathway) application. You can also try out a [demo REST endpoint](https://pathway.com/solutions/ai-contract-management#try-it-out).         |
| [`Multimodal RAG pipeline with GPT4o`](examples/pipelines/gpt_4o_multimodal_rag/) | Multimodal RAG using GPT-4o in the parsing stage to index PDFs and other documents from a connected data source files, Google Drive, Sharepoint,...). It is perfect for extracting information from unstructured financial documents in your folders (including charts and tables), updating results as documents change or new ones arrive.|
| [`Unstructured-to-SQL pipeline + SQL question-answering`](examples/pipelines/unstructured_to_sql_on_the_fly/) | A RAG example which connects to unstructured financial data sources (financial report PDFs), structures the data into SQL, and loads it into a PostgreSQL table. It also answers natural language user queries to these financial documents by translating them into SQL using an LLM and executing the query on the PostgreSQL table. |
| [`Adaptive RAG App`](examples/pipelines/adaptive-rag/) | A RAG application using Adaptive RAG, a technique developed by Pathway to reduce token cost in RAG up to 4x while maintaining accuracy. |
| [`Private RAG App with Mistral and Ollama`](examples/pipelines/private-rag/) |  A fully private (local) version of the `demo-question-answering` RAG pipeline using Pathway, Mistral, and Ollama. |
| [`Slides AI Search App`](examples/pipelines/slides_ai_search/)                                        | An indexing pipeline for retrieving slides. It performs multi-modal of PowerPoint and PDF and maintains live index of your slides."|


## How do these AI Pipelines work?

The apps can be run as **Docker containers**, and expose an **HTTP API** to connect the frontend. To allow quick testing and demos, some app templates also include an optional Streamlit UI which connects to this API. 

The apps rely on the [Pathway Live Data framework](https://github.com/pathwaycom/pathway) for data source synchronization and for serving API requests (Pathway is a standalone Python library with a Rust engine built into it). They bring you a **simple and unified application logic** for back-end, embedding, retrieval, LLM tech stack. 

## Getting started

Each of the [App templates](examples/pipelines/) in this repo contains a README.md with instructions on how to run it.

You can also find [more ready-to-run code templates](https://pathway.com/developers/templates/) on the Pathway website.


## Some visual highlights

Effortlessly extract and organize table and chart data from PDFs, docs, and more with multimodal RAG - in real-time:

![Effortlessly extract and organize table and chart data from PDFs, docs, and more with multimodal RAG - in real-time](https://github.com/pathwaycom/llm-app/blob/main/examples/pipelines/gpt_4o_multimodal_rag/gpt4o_with_pathway_comparison.gif)

(Check out [`Multimodal RAG pipeline with GPT4o`](examples/pipelines/gpt_4o_multimodal_rag/) to see the whole pipeline in the works. You may also check out the [`Unstructured-to-SQL pipeline`](examples/pipelines/unstructured_to_sql_on_the_fly/) for a minimal example that works with non-multimodal models as well.)


Automated real-time knowledge mining and alerting:

![Automated real-time knowledge mining and alerting](examples/pipelines/drive_alert/drive_alert_demo.gif)

(Check out the [`Alerting when answers change on Google Drive`](https://github.com/pathwaycom/llm-app/tree/main/examples/pipelines/drive_alert) app example.)



