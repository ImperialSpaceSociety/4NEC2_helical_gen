# 4NEC2_helical_gen
source code to generate .nec files for helical wire antennas. Purpose is to generate simulations that will help with the mechanical design of the antenna. 

# Code Structure
Will have a class to handle creating the correct geometry for the antenna. Then we'll use a handler to translate the geometry into a .nec file for simulation.

will need following modules
- nec card gen (python script)
- nec parser (using necpp)
- output generator (using necpp, or shell script nec2++)
- parameter learner (some machine learning framework)
- graphic generator (python) DONE

[stuff on python-necpp](http://astroelec.blogspot.co.uk/2015/05/modeling-antennas-in-python-with-nec2.html)
[nec card generator](https://sourceforge.net/p/nec2pylib/wiki/Home/)

# NEC2 class
* Class description:
  Include a description of the parameters and a link to the relevant page in nec manual
* Initialisation:
  initialise the parameters for that nec line
* Construct:
  Function to create a string for that line of nec code
* Verification:
  Verify that the parameters in the class fit NEC2 specification
* (Optional) relevant functions:
  Any other functions relevant to that class

# Running command line NEC
you can use nec2++ to generate an output file from a given .nec file. example usage:
```
nec2++ -i example1.nec -o example1.out
```

Installing nec2++ is can be done using:

```
sudo apt-get install nec2++
```

# CPP install

1. clone the NECPP repo 
``` 
git clone https://github.com/tmolteno/necpp 
```
1. follow the instructions to install necpp [here](https://github.com/tmolteno/necpp/blob/master/INSTALL.md). make sure you are in the necpp folder. 

1. copy the configuration header into the 4NEC2... folder 
```
cp (necpp_location)/config.h (4NEC2_location)/
```
1. go to the src folder and export the NECPP_SRC_PATH environmental variable 
``` 
export NECPP_SRC_PATH=$PWD
```
1. to compile, just go into the cpp folder and call make
```
make
```
