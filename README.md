# Welcome to my Streamlit project
* I decided to check out streamlit as an app deployment tool. 
* I wanted to understand how app deployment would work in combination with using uv as the package manager. 
* This project may not launch a particularly useful app, but is meant to serve as a template that I can refer to.

# Project setup
1. Initiate an empty github repo
2. With uv installed on my system, run `uv init`
3. Get uv into my env with `uv add streamlit`
3.1 this will add streamlit  and its dependencies to `pyproject.toml` and `uv.lock`
4. create a script like hello.py that runs streamlit
5. actiate the virtual environment with `source .venv/bin/activate`
5.1 Usually you can run uv scripts with `uv run hello.py`, but You'll se this does not work because  streamlit is its own executable.
6. So, with your uv- managed venv active, run `streamlit run hello.py`
6.1 this should launch a local host in your terminal with whatever you've printed to streamlit.
7. In order to build more apps with streamlit, I'll set up more structure..
7.1 Add this to `pyproject.toml`
`
  [build-system]
  requires = ["setuptools>=42"]
  build-backend = "setuptools.build_meta"

  [tool.setuptools.packages.find]
  where = ['src']
  include = ['expansion1']
  `
8. I'll set up framework for testing with `uv add pytest`, and create a tests folder