# [Amin M. Boulouma Blog](https://amboulouma.com)

## Spark with Python

> [Reminder] 🔔
- Help the creator channel reach 20k subscribers. He will keep uploading quality content for you: [Amin M. Boulouma Channel](https://www.youtube.com/channel/UCOZbokHO727qeStxeYSKMUQ?sub_confirmation=1)
- This tutorial is best understood following the video playlist: [Data Engineering with Python](https://www.youtube.com/watch?v=ma3BC8aPBfE&list=PLpMTHmi814W1FxjWZQ6dylKrTnGYiO-gM&index=1)


Hosted by Amin M. Boulouma, contact and questions: [amine.boulouma.com](https://amine.boulouma.com)
- Spark with Python tutorial made simple: https://youtu.be/vQqisFjAnsE
- Source code with documentation: https://amboulouma.com/spark-workshop
- Github: https://github.com/amboulouma/spark-workshop

### Spark Installation


```python
pip install pyspark
```


```python
import random

from pyspark import SparkContext
```


```python
sc = SparkContext()
```


```python
def inside(p):     
  x, y = random.random(), random.random()
  return x*x + y*y < 1
```


```python
num_samples = 1000000000

count = sc.parallelize(range(0, num_samples)).filter(inside).count()

pi = 4 * count / num_samples
print(pi)

sc.stop()
```

Ref: https://www.sicara.ai/blog/2017-05-02-get-started-pyspark-jupyter-notebook-3-minutes
