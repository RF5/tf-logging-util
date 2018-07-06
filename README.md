# tf-logging-util
#### A quick and easy utility for setting tensorflow's level of output logging

### Usage
TL;DR:
```python
from tf_logging_util import set_logging_level

set_logging_level('warn') 
# now tensorflow will only print log messages with severity greater than warn (i.e. errors and fatal messages)
```

The main function is `set_logging_level(level)` which sets the tensorflow logging ignore threshold.

`level`, a string, must be one of:
- 'all' : show all tensorflow logging messages
- 'info' : hide all debug and info messages.
- 'warn' : hide all debug, info, and warning mesasges
- 'error' : hide all debug, info, warning, and error messages

So only the tensorflow log messages with a severity/importance level
higher than the log type indicated by `level` will be printed to standard output.
Note: Fatal errors will always be shown.

You can call the function any number of times to change the logging level during a training session.

### Requirements
Tensorflow (just about any version) and python 3.

### Why was this needed?
Long story short, I couldn't find the answers I was looking for easily online and each answer seemed to only work on some versions or environments, so I decided to just make a single, easy to find and use utility which will work for a lot of tensorflow versions. So it probably wasn't necessary - it isn't too hard to dig deep and find the 2 lines you need to include in your tensorflow project with its versioning, but if you stumble upon this before you find those two lines, this utility will work too.


-- Matthew Baas
