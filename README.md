# elastic-stack

## Filebeat 

### Installation

1. Download the filebeat binary from [downloads](https://www.elastic.co/downloads/beats/filebeat) page
2. Unzip the binary/zip to your favourite folder
3. Create a sample file like `my.yml` in the root of the filebeat installation:

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

### Running
4. Run the filebeat by issuing the following command:
`./filebeat -c my.yml -e`

## Console input

Modify the `my.yml` to output the data to a console log. Comment the `output.elasticsearch` block and add the following:
```
output.console:
  pretty: true
```
Rerun the application - this time the logs will be output to console
