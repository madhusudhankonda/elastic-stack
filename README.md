# elastic-stack

## Filebeat 

1. Download the filebeat binary from [downloads](https://www.elastic.co/downloads/beats/filebeat) page
2. Unzip the binary/zip to your favourite folder
3. Create a sample yml file like `my.yml` in the root of the filebeat installation:

```
filebeat.inputs:

- type: log
  enabled: true

  # Paths that should be crawled and fetched. Glob based paths.
  paths:
    - /Users/mkonda/DEV/OLT/ELASTIC_STACK/elastic-stack/*.log

output.elasticsearch:
  hosts: ["localhost:9200"]
```


