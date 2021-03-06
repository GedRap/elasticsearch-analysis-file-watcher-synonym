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
bin/plugin -install analysis-file-watcher-synonym  -url https://github.com/GedRap/elasticsearch-analysis-file-watcher-synonym/blob/master/releases/v0.90.4-0.1.0/elasticsearch-file-watcher-synonym-0.90.4-0.1.0.zip?raw=true
```

### Compatibility

This version is tested and built for elasticsearch 0.90.4 only.