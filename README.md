This configuration file achieves the following:

Input:
The Logstash Console Input Plugin reads data from standard input (stdin).

Filter:
The grok filter is used to parse the incoming log lines according to a pattern. It extracts fields like description, hostname, source_ip, and severity from the log message.
The mutate filter is used to modify the severity field to map numeric values to their corresponding textual representations (e.g., "1" becomes "High").

Output:
The Logstash Console Output Plugin sends the transformed data to standard output (stdout) in JSON format.

This configuration is designed to be flexible enough to handle different log messages structured similar to the sample below (used for this exercise) while producing a consistent output structure. 

Log Sample: 
<14>1 2016-12-25T09:03:52.754646-06:00 contosohost1 antivirus 2496 - - alertname="Virus Found" computername="contosopc42" computerip="216.58.194.142" severity="1"

For example, if another security log message contains the same fields (description, hostname, source_ip, severity) but with different data, this configuration will still parse and transform it accordingly.
