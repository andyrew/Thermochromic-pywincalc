# Thermochromic IGU simulations with pywincalc
This repo contains an example of using pywing calc to generate performance charts for a thermochromic IGU.

## Setup on Mac OSX
This requires a working installation of python 3 and git.
```
# Download the contents of this repo:
git clone https://github.com/andyrew/Thermochromic-pywincalc.git

# Create a python virtual environment
python3 -m venv pyenv_thermochromic

# Activate the python virtual environment
source pyenv_thermochromic/bin/activate

# Install the interactive python notebook jupyter
pip install notebook ipykernel

# Tell the interactive python environment to use the virtual environment
python -m ipykernel install --user --name=pyenv_thermochromic

# Install the python libraries used in the example
pip install pywincalc numpy matplotlib pysolar epw pandas scipy

#Launch the interactive notebook
jupyter notebook
```
