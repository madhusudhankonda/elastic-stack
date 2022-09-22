# elastic-stack

## Logstash

1. Download the Logstash binary from [Logstash binary](https://www.elastic.co/downloads/logstash) page
2. Unzip the binary/zip to your fav folder

## Running your first pipeline
1. Create a `sample.conf` in the root directory with the following pipeline info:

```
input {
  stdin{}
}

output {
  stdout{}
}
```

2. Issue the command: `./bin/logstash -f sample.conf`

4. On the console, input some sample text and expect a response printed out to the output, as shown in the image below:
```
![image](https://user-images.githubusercontent.com/1698230/191788287-8ee38237-5037-41df-b13c-16a7bee2034e.png)
```

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
