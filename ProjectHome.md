PyDCU provides a Python package DCU that wraps the [Thorlabs](http://www.thorlabs.com/) DCU200 camera driver software for Python using [ctypes](http://docs.python.org/library/ctypes.html).

The package is tested with [DCU223M](http://www.thorlabs.com/thorProduct.cfm?partNumber=DCU223M) using windows XP.


# Basic Usage #
Code sample using matplotlib and numpy libraries.

```
import uc480
import numpy as np
import matplotlib.cm as cm
import matplotlib.mlab as mlab
import matplotlib.pyplot as plt

camera = uc480.camera()
camera.AllocImageMem()
camera.SetImageMem()
camera.SetImageSize()
camera.SetColorMode()
camera.CaptureVideo()
raw_input("enter to stop")
camera.CopyImageMem()
im = plt.imshow(camera.data, cmap=cm.gray, aspect='equal')
camera.StopLiveVideo()
camera.FreeImageMem()
camera.ExitCamera()
plt.show()
```