---
title       : Getting Started
description : First hands on excercise for learning Python

import pandas as pd
import matplotlib.pyplot as plt
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

plt.scatter(movies.runtime, movies.rating)
plt.show()
```