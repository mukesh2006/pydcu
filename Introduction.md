#pydcu basic usage

# Introduction #

Pydcu is a python wrapper for Thorlabs DCU 200 camera series dll.

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