# Lycan Elasticsearch Configuration

## Changes to Schema for ES

 - Any description object in the schema has a key for the associated language eg: `{ "en": { ...descriptionObject } }`. This makes mapping it hard due to the amount of langauges, these should be converted into an array of objects eg: `{ [ ...descriptionObject ] }`. The description object already has the `locale: "en"` field anyway.
 
## Config Changes

In `/etc/elasticsearch/elasticsearch.yml` the following needs to be added/modified:

 - Add `script.painless.regex.enabled: true` to allow the splitting of strings (waiting upon native painless support for the `String.split()` function.
 
## Index Naming Conventions

For indexes, the convention is as follows where {} denotes a variable eg {name}: `org.{name}.{indexType}`. For example, `org.foo_cottages.properties`.
