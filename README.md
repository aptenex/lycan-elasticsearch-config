# Lycan Elasticsearch Configuration

## Changes to Schema for ES

 - Any description object in the schema has a key for the associated language eg: `{ "en": { ...descriptionObject } }`. This makes mapping it hard due to the amount of langauges, these should be converted into an array of objects eg: `{ [ ...descriptionObject ] }`. The description object already has the `locale: "en"` field anyway.
