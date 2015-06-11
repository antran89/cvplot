# cvplot
Automatically exported from code.google.com/p/cvplot

Description
-----------
Matlab style plot functions for OpenCV.

I ported cvplot example to OpenCV 3.0 code and create CMakeLists.txt file.

License
-------
Apache 2.0.

Usage
-----
C++ code, need OpenCv 3.0. Including header file and src file in your project, and there you go.

```
#include "cvplot.h"

...
CvPlot::plot("RGB", pb  , width, 3);
CvPlot::label("B");
CvPlot::plot("RGB", pb+1, width, 3, 0, 255, 0);
CvPlot::label("G");
CvPlot::plot("RGB", pb+2, width, 3, 255, 0, 0);
CvPlot::label("R");
```

Use "clear" to remove previous plots on a named window:
```
#include "cvplot.h"

...
CvPlot::clear("RGB");
```
