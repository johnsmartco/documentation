---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Configuration

A manifest of additional resources and dependencies to run the pipeline.

Example of a data source that needs drivers as well as credentials:

```yaml
configuration:
  resources:
    - type: "datasource"
      name: "PGDataSource"
      configuration:
        service: "jdbc"
        driverClass: "org.postgresql.Driver"
        url: "jdbc:postgresql://postgresql.default.svc.cluster.local:5432/"
        user: "postgres"
        password: "xxxxxx"
  dependencies:
    - name: "PostGRES JDBC Driver"
      url: "https://jdbc.postgresql.org/download/postgresql-42.6.0.jar"
      sha512sum: "ec3b57d8377715ef6286d457b610a2e056aa99db….1"
      type: "java-library"
```

LangStream has built-in support for a few Databases and Vector databases (no need for dependency), for example:

[Cassandra (with Vector support)](configuration.md#cassandra-with-vector-support)

[DataStax AstraDB](configuration.md#datastax-astra-db)

[Pinecone](configuration.md#pinecone)

[OSS Milvus and Zillis](configuration.md#oss-milvus-and-zillis)

[Apache Solr](configuration.md#apache-solr)

#### Cassandra (with Vector support)

```yaml
configuration:
  resources:
    - type: "datasource"
      name: "Cassandra"
      configuration:
        service: "cassandra"
        username: ""
        password: ""
        contact-points: ""
        loadBalancing-localDc: ""
```

#### DataStax Astra DB

<pre class="language-yaml"><code class="lang-yaml"><strong>configuration:
</strong>  resources:
    - type: "vector-database"
      name: "AstraDBDatasource"
      configuration:
        service: "astra"
        secret: ""
        clientId: ""
        token: ""
        database: ""
</code></pre>

#### Pinecone

```yaml
configuration:
  resources:
    - type: "vector-database"
      name: "PineconeDatasource"
      configuration:
        api-key: ""
        environment: ""
        index-name: ""
        project-name: ""
```

#### OSS Milvus and Zillis

```yaml
 configuration:
  resources: 
  - type: "datasource"
    name: "MilvusDatasource"
    configuration:
      service: "milvus"
      ## OSS Milvus
      username: "${secrets.milvus.username}"
      password: "${secrets.milvus.password}"
      host: "${secrets.milvus.host}"
      port: "${secrets.milvus.port}"
      ## Set to "upsert" for OSS Milvus, on Zills use "delete-insert"
      write-mode: "${secrets.milvus.write-mode}"
      ## Zillis
      url: "${secrets.milvus.url}"
      token: "${secrets.milvus.token}"
```

#### Apache Solr

<pre class="language-yaml"><code class="lang-yaml">configuration:
<strong>  resources:
</strong>  - type: "vector-database"
    name: "SolrDataSource"
    configuration:
      service: "solr"
      user: "${secrets.solr.username}"
      password: "${secrets.solr.password}"
      host: "${secrets.solr.host}"
      port: "${secrets.solr.port}"
      collection-name: "documents"
      
</code></pre>

### Manifest

<table><thead><tr><th width="148">Root</th><th width="144">Node</th><th width="94">Type</th><th>Description</th></tr></thead><tbody><tr><td>configuration</td><td><br></td><td><br></td><td>Top level node</td></tr><tr><td><br></td><td>dependencies</td><td>object<br></td><td><p>A collection of artifacts that a pipeline step of resource may need to run. <a href="configuration.md#dependencies">Refer to the spec below.</a></p><p>Example collection:</p><ul><li>type: “xxx”<br>name: “xxx”<br>configuration:<br>…</li><li>type: “xxx”<br>name: “xxx”<br>configuration:<br>…</li></ul></td></tr><tr><td><br></td><td>resources</td><td><br>object</td><td><p>A collection of resources. <a href="configuration.md#dependencies">Refer to the spec below.</a></p><p>Example collection:</p><ul><li>type: “xxx”<br>name: “xxx”<br>sha: “xxx”<br>…</li><li>type: “xxx”<br>name: “xxx”<br>sha: “xxx”<br>…</li></ul></td></tr></tbody></table>

### dependencies

The given artifact will be downloaded, validated, and made available to the pipeline. \\

<table><thead><tr><th width="156.33333333333331">Label</th><th width="165">Type</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>string (required)</td><td><p>The type of dependency. Supported values are:</p><ul><li>java-library</li></ul><p>Example: “java-library”</p></td></tr><tr><td>name</td><td>string (required)</td><td><p>The name of the dependency. It is used for display and as a reference pointer.<br></p><p>Example: "Postgres JDBC Driver"</p></td></tr><tr><td>url</td><td>string (required)</td><td><p>A fully qualified URL to the dependency artifact.</p><p>Example: "https://jdbc.postgresql.org/download/postgresql-42.6.0.jar"</p></td></tr><tr><td>sha512sum</td><td>string (required)</td><td><p>The downloaded artifact is validated against this value.<br></p><p>Example: "ec3b57d8377715ef6286d457…”</p></td></tr></tbody></table>

These dependencies are downloaded by the LangStream CLI when you run "apps deploy", "docker run" and similar commands. This mechanism is especially useful for JDBC Drivers and for Kafka Connect connectors.

To handle Python dependencies, check out the documentation about developing [custom Python agents](../pipeline-agents/custom-agents/).

### resources

<table><thead><tr><th width="165.33333333333331">Label</th><th width="101">Type</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>string</td><td><p>The type of resource. Refer to the configuration resources reference for naming.</p><p>Example: “datasource”</p></td></tr><tr><td>name</td><td>string</td><td><p>The name of the resource. It is used for display and as a reference pointer.<br></p><p>Example: "PGDataSource"</p></td></tr><tr><td>configuration</td><td>object</td><td>Custom configuration for the given resource. Refer to the configuration resources reference for options.</td></tr></tbody></table>
