# Logstash

A data collection engine with real-time pipelining capabilities.

Set temporary path of JDK in Windows

```sh
JAVA_HOME
C:\Program Files\Java\jdk1.8.0_162

PATH
%JAVA_HOME%\bin

echo %JAVA_HOME%
```

The -e flag enables you to specify a configuration.
```sh
cd logstash-6.1.3
bin/logstash -e 'input { stdin { } } output { stdout {} }'
```

Verify your configuration
```sh
logstash -f first-pipeline.conf --config.test_and_exit
```

start Logstash and enable automatic config reloading
```sh
logstash -f first-pipeline.conf --config.reload.automatic
```

Template
The filter part is optional.
The # character at the beginning of a line is a comment.
```sh
input {}
filter {}
output {}
```