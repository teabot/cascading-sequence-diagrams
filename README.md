#Overview
Sequence diagrams describing the standard life-cycles in Cascading's `Tap` API. This should be considered an illustrative approximation that outlines the salient interactions that are usually of interest to `Tap` and `Scheme` developers.

Analysis was performed against Cascading's Hadoop platform classes for version 2.7.0. Note that this sequence may differ for different platforms and/or versions. Created with [seqdiag](http://blockdiag.com/en/seqdiag/) and excessive use of `^⌥H` in Eclipse, and hence prone to human error.

Note that within the diagrams the `<client>` and `<task>` components represent the tool and job-task in MapReduce nomenclature. These are considered an abstract boundary point because as Cascading developers we rarely care, understand, or know what these look like internally. They are considered black-boxes, implementing the Cascading runtime on some execution engine but exercising the public `Tap` API in a contractual manner. All other components map to their respective classes within the Cascading API.

#Usage
    seqdiag source.diag ; open -a "Preview" source.png
    seqdiag sink.diag ; open -a "Preview" sink.png 

#Source
![Source](source.png)

#Sink
Notes:

* It's odd that the sink is initialised when the `FlowDef` is connected and not when the `Flow` is constructed, as is the case with the source.
* If the flow fails then `rollbackResource()` is invoked instead of `commitResource()`.
![Sink](sink.png)

#Credits

Created by [Elliot West](https://github.com/teabot) with thanks to Ken Krugler.

#License
These diagrams are available under the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0.html).
