#Overview
Created with [seqdiag](http://blockdiag.com/en/seqdiag/) and excessive use of `^⌥H` in Eclipse.

Note that within the diagrams the 'client' and 'task' components represent the tool and job-task in MapReduce nomenclature. These are considered an abstract boundary point because as Cascading developers we rarely care, understand, or know what these look like internally. They are considered black-boxes, implementing the Cascading runtime on some execution engine but execrising the public `Tap` API in a contractual manner. All other components map to their respective classes within the Cascading API.

#Usage
    seqdiag source.diag ; open -a "Preview" source.png
    seqdiag sink.diag ; open -a "Preview" sink.png 

#Source
![Source](source.png)

#Sink
![Sink](sink.png)
