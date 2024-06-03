# datafun-06-eda
Module 6 Project
Melissa Stone Rogers, June 3, 2024

## Introduction
Professional project to create an exploratory data analysis (EDA) project using GitHub, Git, Jupyter, pandas, Seaborn and other popular data analytics tools.
Commands were used on a Mac machine running zsh.  

## How to Install and Run the Project
Create project repository in Github and clone to your machine.

```
git clone project.url
```

```
python3 -m venv .venv
source .venv/bin/activate
```

Create requirements.txt in the root project folder. 
```
touch requirements.txt
```
Add the following packages to your requirements.txt file:
- jupyterlab
- pandas
- pyarrow
- matplotlib
- seaborn

Install requirments.txt. 
```
python3 -m pip install -r requirements.txt
```

## Freeze Requirements

```
python3 -m pip freeze > requirements.txt
```

## Add .gitignore File
Add .gitignore file to the root project folder. 
```
touch .gitignore
```
Add the following to your .gitignore file: 
- .venv/
- .vscode/
- .ipynb_checkpoints/

## Import Dependencies 

```
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
import pyarrow as pa
```

## Initial Project Save
```
git add .
git commit -m "initial"                         
git push origin main
```

## PROJECT START


## Complete Your Project
Save your project and push back to your repository. 
```
git add .
git commit -m "final"                         
git push origin main
```

## Project Summary


## Specification

This project was built to the following specification:
https://github.com/denisecase/datafun-06-spec