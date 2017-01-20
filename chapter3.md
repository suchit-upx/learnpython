---
title       : Movie Details
description : Movie Graphs

--- type:NormalExercise lang:python xp:100 skills:1 key:642939b4ae
## Plot the movies yourself

Do you remember the plot of the last exercise? Let's make an even cooler plot!

A dataset of movies, `movies`, is available in the workspace.

*** =instructions
- The first function, `np.unique()`, uses the `unique()` function of the `numpy` package to get integer values for the movie genres. You don't have to change this code, just have a look!
- Import `pyplot` in the `matplotlib` package. Set an alias for this import: `plt`.
- Use `plt.scatter()` to plot `movies.runtime` onto the x-axis, `movies.rating` onto the y-axis and use `ints` for the color of the dots. You should use the first and second positional argument, and the `c` keyword.
- Show the plot using `plt.show()`.

*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

*** =pre_exercise_code
```{python}
import pandas as pd
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

import numpy as np
```

*** =sample_code
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot


# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints


# Show the plot

```

*** =solution
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot
import matplotlib.pyplot as plt

# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints
plt.scatter(movies.runtime, movies.rating, c=ints)

# Show the plot
plt.show()
```

*** =sct
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")

test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

test_import("matplotlib.pyplot", same_as = True)

test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```
