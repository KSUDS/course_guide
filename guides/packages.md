---
layout: default
nav_order: 'D'
parent: User Guides
---

## Packages in R and Python

The history of Python and R both start in the early 90s.  R has been a programming language for statisticians, and Python was created for developers.  Neither language comes with the tools data scientists need for their day-to-day work. To handle those limitations, we will need to find packages that others have built to facilitate data science programming.

Both languages require a two-step process.

1. Install the package from the internet or a local file (once per language installation)
2. Initiate the library (once per script)

### Installation

#### Python

Python uses [pip](https://pip.pypa.io/en/stable/) for its package manager.  It runs outside of Python and has a history of being a little picky when new Python programmers want to install packages.  [Conda](https://docs.conda.io/en/latest/) is built for the scientific computing community to get tools installed on their computer without the headache of pip. 

I prefer to stay with pip.  Some of you may get the terminal to work with a simple `pip install pandas`.  Those who have problems getting pip to install packages into your Python environment should use the following command within interactive Python in VScode.

```Python
import sys
!{sys.executable} -m pip install pandas
```

#### R 

R uses `install.packages()` and requires you to type the package name in quotes.  This function is run within the R console. 

```R
install.packages("tidyverse")
```

### Initiation

#### Python

Python provides a few methods to initiate a library or functions from a library. We will use `import ___ as ___` and `from ____ import ____`. Many of the data science Python packages have standard abbreviations that are used.  The code below provides some standard examples.

1. The first three that use `import ___ as ___` will all require that you start your package command with the abbreviation to access the respective functions (For example, `pd.read_csv()`). 
2. For `from plotnine import *` will initiate all the functions with plotnine without requiring the abbreviation or package name to be typed. This will allow you to write `ggplot2` code in Python.
3. For `from sklearn.tree import DecisionTreeClassifier` we are only importing one function or set of methods from a package.

```Python
import pandas as pd 
import altair as alt
import numpy as np

from plotnine import *
from sklearn.tree import DecisionTreeClassifier
```

#### R 

Unlike Python, R users load the entire library.  Once the library initiates, the functions from the library overwrite any base R functions and previously loaded libraries.

```R
library(tidyverse)
```

I prefer to use the [pacman](https://github.com/trinker/pacman) package to initiate the packages for my script.  It provides a couple of advantages.  If the package is not installed, it automatically installs the package before starting the library. Additionally, I don't have to remember whether to put the name in quotes.

```R
pacman:p_load(tidyverse, httpgd)
```
