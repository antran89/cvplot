Matlab style plot functions for OpenCV.<br />
All included in 2 files.

---

Usage:
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

Result:<br />
http://cvplot.googlecode.com/files/graph.PNG

---

Use "clear" to remove previous plots on a named window:
```
#include "cvplot.h"

...
CvPlot::clear("RGB");

```

Welcome feedback!