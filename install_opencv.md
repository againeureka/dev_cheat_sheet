



딥러닝-Slicon-M1-Mac에-TensorFlow-OpenCV-설치하기


```bash
$ pip install opencv-contrib-python

```


```python

import numpy as np
import cv2
import matplotlib.pyplot as plt
%matplotlib inline

#img = cv2.imread('./test.png')
rgb = np.random.randint(255, size=(900,800,3),dtype=np.uint8)

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
```
