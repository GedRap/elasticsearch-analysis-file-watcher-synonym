File watcher synonym for ElasticSearch
======================================

The file watcher synonym plugin adds a synonym token filter that reloads the synonym file at given intervals (default 60s).

Example:

	{
	    "index" : {
	        "analysis" : {
	            "analyzer" : {
	                "synonym" : {
	                    "tokenizer" : "whitespace",
	                    "filter" : ["synonym"]
 	               }
	            },
	            "filter" : {
	                "synonym" : {
	                    "type" : "file_watcher_synonym",
	                    "synonyms_path" : "analysis/synonym.txt"
	                    "interval" : "10s"
	                }
	            }
	        }
	    }
	}

## Installation

To build the plugin, run 
```
mvn clean package
```

The plugin can be installed by:
```
bin/plugin -install analysis-file-watcher-synonym  -url https://github.com/lindstromhenrik/elasticsearch-analysis-file-watcher-synonym/releases/download/v0.90.9-0.1.0/elasticsearch-file-watcher-synonym-0.90.9-0.1.0.zip
```

### Compatibility

This version is tested and built for elasticsearch 0.90.4 only.