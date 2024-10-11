# Thermochromic IGU simulations with pyWinCalc
This repo contains an example of using pywing calc to generate performance charts for a thermochromic IGU.

I've found LBNL's python wrapper for their C++ window calculation engine (https://github.com/LBNL-ETA/pyWinCalc) to be extremely powerful for running Window simulations. Being freed from the confines of the Window user interface allows users to do so much more!

I decided to upload this example of simulations for a thermochromic window to show how it is possible to leverage the Window calculation engine to generate data and plots that were not previously possible with window.

### Chart of Thermochromic IGU Properties
The optical and thermal properties of a thermochromic IGU is dependant on the temperature of the thermochromic laminate. This means that the outside air temperature, wind speed, solar radiation, solar incident angle, and IGU properties influence the visible light transmission and the solar heat gain coefficient. The charts below show for a give wind speed (0 m/s) and solar incidence angle (0°) what the thermochromic layer temperature would be for different exterior air temperatures (x-axis) and solar insolation (y-axis). These calculations were performed with pywincalc by creating 108 custom environments (12 exterior temperature x 9 solar radiation) and layer performance for 19 laminate temperatures (5°C - 95°C, in 2.5°C increments). For each environmental condition the temperature of the laminate was calculated using the absorption properities of the 18 thermochromic layer temperatures. The correct result for the environmental condition is where the simulated laminate temperature matches the themperature of the optical properties.



![falsecolor plot of thermochromic properties for various solar irradiance and exterior temperaturees](plots/Thermochromic_Temp+SHGC_ws0_LoE272.png)

### Chart of Annual Thermochromi IGU properties for a south facing facade in Chicago
Taking this a step further, we can read environmental conditions from a weather file, including wind speed, wind direction, exterior temperature, solar radiation and solar incident angle and calculate the equilibrium temperature of the thermochromic laminate for every hour of the year. The charts below are an annual plot of temperature, solar heat gain coefficent, and visible light transmission of the thermochromic IGU.



![Annual plot of thermochromic laminate temperature for Chicago](plots/Annual_Thermochromic_Temperature_Chicago_South.png)
![Annual plot of thermochromic SHGC for Chicago](plots/Annual_Thermochromic_SHGC_Chicago_South.png)
![Annual plot of thermochromic Tvis for Chicago](plots/Annual_Thermochromic_Tvis_Chicago_South.png)

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
