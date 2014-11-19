---
layout: index
---

## Sign Consistency on Influence Graphs - Diagnosis, Repair, Prediction

For many biological systems knowledge bases are available that describe the interaction of its components usually in terms of causal networks and influence graphs. In particular signed influence graphs where edges indicate either positive or negative effect of one node upon another. Building upon a notion of consistency between biochemical/genetic regulations and high-throughput profiles of cell activity. We present an approach to check the consistency of large-scale data sets, provide explanations for inconsistencies by determining minimal representations of conflicts. In practice, this can be used to identify unreliable data or to indicate missing reactions. Further, we address the problem of repairing networks and corresponding yet often discrepant measurements in order to re-establish their mutual consistency and predict unobserved variations even under inconsistency. 
[![DOI](https://zenodo.org/badge/5393/bioasp/iggy.png)](http://dx.doi.org/10.5281/zenodo.11098)

### Installation

You can install iggy by running:

	$ pip install --user iggy

On Linux the executable scripts can then be found in ``~/.local/bin``

and on MacOS the scripts are under ``/Users/YOURUSERNAME/Library/Python/2.7/bin``.


### Usage

Typical usage is:

	$ iggy.py network.sif observation.obs --show_colorings 10 --show_predictions

For more options you can ask for help as follows:

	$ iggy.py -h 		
	usage: iggy.py [-h] [--no_zero_constraints]
               [--propagate_unambigious_influences] [--no_founded_constraint]
               [--autoinputs] [--scenfit] [--show_colorings SHOW_COLORINGS]
               [--show_predictions]
               networkfile observationfile

	positional arguments:
	  networkfile           influence graph in SIF format
	  observationfile       observations in bioquali format

	optional arguments:
	  -h, --help            show this help message and exit
	  --no_zero_constraints
				turn constraints on zero variations OFF, default is ON
	  --propagate_unambigious_influences
				turn constraints ON that if all predecessor of a node
				have the same influence this must have an effect,
				default is ON
	  --no_founded_constraint
				turn constraints OFF that every variation must be
				explained by an input, default is ON
	  --autoinputs          compute possible inputs of the network (nodes with
				indegree 0)
	  --scenfit             compute scenfit of the data, default is mcos
	  --show_colorings SHOW_COLORINGS
				number of colorings to print, default is OFF, 0=all
	  --show_predictions    show predictions



The second script contained is opt_graph.py
Typical usage is:

	$ opt_graph.py network.sif observations_dir/ --show_repairs 10

For more options you can ask for help as follows:

	$ opt_graph.py -h 	
	usage: opt_graph.py [-h] [--no_zero_constraints]
		    [--propagate_unambigious_influences]
		    [--no_founded_constraint] [--autoinputs]
		    [--show_repairs SHOW_REPAIRS] [--opt_graph]
		    networkfile observationfiles

	positional arguments:
	  networkfile           influence graph in SIF format
	  observationfiles      directory of observations in bioquali format

	optional arguments:
	  -h, --help            show this help message and exit
	  --no_zero_constraints
				turn constraints on zero variations OFF, default is ON
	  --propagate_unambigious_influences
				turn constraints ON that if all predecessor of a node
				have the same influence this must have an effect,
				default is ON
	  --no_founded_constraint
				turn constraints OFF that every variation must be
				explained by an input, default is ON
	  --autoinputs          compute possible inputs of the network (nodes with
				indegree 0)
	  --show_repairs SHOW_REPAIRS
				number of repairs to show, default is OFF, 0=all
	  --opt_graph           compute opt-graph repairs (allows also adding edges),
				default is only removing edges


### Samples

Sample files available here: [iggy_demo_data.tar.gz](http://www.cs.uni-potsdam.de/~sthiele/bioasp/downloads/samples/iggy_demo_data.tar.gz)

### Related publications

* Detecting Inconsistencies in Large Biological Networks with Answer Set Programming. (2011). Theory and Practice of Logic Programming. [DOI](http://dx.doi.org/10.1007/978-3-540-89982-2_19)

* Repair and Prediction (under Inconsistency) in Large Biological Networks with Answer Set Programming.(2010). 12th International Conference on the Principles of Knowledge Representation and Reasoning.[DOI](http://aaai.org/ocs/index.php/KR/KR2010/paper/view/1334/1660)
