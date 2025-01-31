# Table of contents

* [LangStream Documentation](README.md)
* [❤ Langstream.ai](https://langstream.ai)
* [⭐ LangStream GitHub Repo](https://github.com/LangStream/langstream)

## about

* [What is LangStream?](about/what-is-langstream.md)
* [License](about/license.md)

***

* [Get Started](get-started.md)

## installation

* [Minikube (mini-langstream)](installation/get-started-minikube.md)
* [Kubernetes](installation/kubernetes.md)
* [Docker](installation/docker.md)
* [LangStream CLI](installation/langstream-cli.md)
* [Build and install from source](installation/build-and-install-source.md)

## Building Applications

* [Vector Databases](building-applications/vector-databases.md)
* [Application structure](building-applications/development-environment.md)
  * [Pipelines](building-applications/pipelines.md)
  * [Instances](building-applications/instances.md)
  * [Configuration](building-applications/configuration.md)
  * [Topics](building-applications/topics.md)
  * [Assets](building-applications/assets.md)
  * [Secrets](building-applications/secrets.md)
  * [YAML templating](building-applications/yaml-templates.md)
  * [Error Handling](building-applications/error-handling.md)
  * [.langstreamignore](building-applications/langstreamignore.md)
* [Sample App](building-applications/build-a-sample-app.md)
* [Develop, test and deploy](building-applications/development-workflow.md)
* [Application Lifecycle](building-applications/application-lifecycle.md)
* [Expression Language](building-applications/expression-language.md)
* [API Gateways](building-applications/api-gateways/README.md)
  * [Websocket](building-applications/api-gateways/websocket.md)
  * [Message filtering](building-applications/api-gateways/message-filtering.md)
  * [Gateway authentication](building-applications/api-gateways/gateway-authentication.md)
* [API Reference](building-applications/api-reference/README.md)
  * [Agents](building-applications/api-reference/agents.md)
  * [Resources](building-applications/api-reference/resources.md)
  * [Assets](building-applications/api-reference/assets.md)

## LangStream CLI

* [CLI Commands](langstream-cli/langstream-cli-commands.md)
* [CLI Configuration](langstream-cli/langstream-cli-configuration.md)

## Integrations

* [Large Language Models (LLMs)](configuration-resources/large-language-models-llms/README.md)
  * [OpenAI](configuration-resources/large-language-models-llms/open-ai-configuration.md)
  * [Hugging Face](configuration-resources/large-language-models-llms/hugging-face-configuration.md)
  * [Google Vertex AI](configuration-resources/large-language-models-llms/vertex-configuration.md)
* [Data storage](configuration-resources/data-storage/README.md)
  * [Astra](configuration-resources/data-storage/astra.md)
  * [Cassandra](configuration-resources/data-storage/cassandra.md)
  * [Pinecone](configuration-resources/data-storage/pinecone.md)
  * [Milvus](configuration-resources/data-storage/milvus.md)
  * [Solr](configuration-resources/data-storage/solr.md)
  * [JDBC](configuration-resources/data-storage/jdbc.md)

## Pipeline Agents

* [Agent Messaging](pipeline-agents/agent-messaging.md)
* [Builtin agents](pipeline-agents/builtin-agents.md)
  * [Input & Output](pipeline-agents/input-and-output/README.md)
    * [webcrawler-source](pipeline-agents/input-and-output/webcrawler-source.md)
    * [s3-source](pipeline-agents/input-and-output/s3-source.md)
    * [azure-blob-storage-source](pipeline-agents/input-and-output/azure-blob-storage-source.md)
    * [sink](pipeline-agents/input-and-output/sink.md)
    * [vector-db-sink](pipeline-agents/input-and-output/vector-db-sink.md)
  * [AI Agents](pipeline-agents/ai-actions/README.md)
    * [ai-chat-completions](pipeline-agents/ai-actions/ai-chat-completions.md)
    * [ai-text-completions](pipeline-agents/ai-actions/ai-text-completions.md)
    * [compute-ai-embeddings](pipeline-agents/ai-actions/compute-ai-embeddings.md)
    * [flare-controller](pipeline-agents/ai-actions/flare-controller.md)
  * [Text Processors](pipeline-agents/text-processors/README.md)
    * [document-to-json](pipeline-agents/text-processors/document-to-json.md)
    * [language-detector](pipeline-agents/text-processors/language-detector.md)
    * [query](pipeline-agents/text-processors/query.md)
    * [query-vector-db](pipeline-agents/text-processors/query-vector-db.md)
    * [re-rank](pipeline-agents/text-processors/rerank.md)
    * [text-normaliser](pipeline-agents/text-processors/text-normaliser.md)
    * [text-extractor](pipeline-agents/text-processors/text-extractor.md)
    * [text-splitter](pipeline-agents/text-processors/text-splitter.md)
    * [http-request](pipeline-agents/text-processors/http-request.md)
  * [Data Transform](pipeline-agents/data-transform/README.md)
    * [cast](pipeline-agents/data-transform/cast.md)
    * [compute](pipeline-agents/data-transform/compute.md)
    * [drop](pipeline-agents/data-transform/drop.md)
    * [drop-fields](pipeline-agents/data-transform/drop-fields.md)
    * [merge-key-value](pipeline-agents/data-transform/merge-key-value.md)
    * [unwrap-key-value](pipeline-agents/data-transform/unwrap-key-value.md)
  * [Flow control](pipeline-agents/flow-control/README.md)
    * [dispatch](pipeline-agents/flow-control/dispatch.md)
* [Custom Agents](pipeline-agents/custom-agents/README.md)
  * [Agent Developer Guide](pipeline-agents/agent-developer-guide/README.md)
    * [Agent Types](pipeline-agents/agent-developer-guide/agent-types.md)
    * [Agent Creation](pipeline-agents/agent-developer-guide/agent-creation.md)
    * [Configuration and Testing](pipeline-agents/agent-developer-guide/configuration-and-testing.md)
  * [Python sink](pipeline-agents/custom-agents/python-sink.md)
  * [Python source](pipeline-agents/custom-agents/python-source.md)
  * [Python processor](pipeline-agents/custom-agents/python-function.md)

## Messaging

* [Messaging](configuration-resources/messaging/README.md)
  * [Apache Pulsar](configuration-resources/messaging/pulsar.md)
  * [Apache Kafka](configuration-resources/messaging/kafka.md)

## Patterns

* [RAG pattern](patterns/rag-pattern.md)
* [FLARE pattern](patterns/flare-pattern.md)

## Examples

* [LlamaIndex Cassandra sink](examples/llamaindex-cassandra-sink.md)
