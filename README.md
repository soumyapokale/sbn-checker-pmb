# sbn-checker-pmb
this is the program which will check if pmb gold sentences are checked with respect to english and german 
#How to create virtual environment in Ubuntu:
- >A s a pre-requisite,on your system python and pip package manager for python should be pre-installed (which is there in versions of Ubuntu greater than 18.04). You can also check whether python is installed in your system or not using command-> "python3 -V"

- > Then follow the below steps in order to create virtual environment using python:-
'''
          pip install virtualenv #To install virtualenv library available in python
          virtualenv <env_name>  # To create virtual environment
          source <env_name>/bin/activate  # To activate virtual environment created in previous step
'''
- > After activating you will see environment name in braces in terminal. Python is installed automatically while creating environment along with pip package manager along with some libraries like, os, sys,wheel that you can check using command-> "pip list"

- > But, you require one package to be installed in your virtual environment for working of project called "sfst" that can be installed using command-> "pip install sfst". Then you can setup project in virtual environment.

- > To come out of virtual environment, we can use "deactivate" command.


#Files in package

1. german_sent: Text file containing german sentence that we will pass as output from  our program.
2. sbnmismatchdeeng : Text file containing the files which doesnt have same german and english sbn file or english sbn file is missing 
3. automatesbn.py : Python file to compare sbn files between german  and english and provide us details about the errors .
4. sbnfileall : Text file in which all the sbn notation part of the rawsbn file will be inputed for all the files .
5. scriptp.sh : Bash file to run the code 

#How to run module:

NOTE: i) Before running this script file, you might need to change the paths inside the automatesbn.py according to your personal pc or laptop 
2) Extract pmb-4.0.0-en-de-gold.tgz into PMB-4.0.0-de-gold  and PMB-4.0.0-en-gold folders

1. scriptp.sh 
2. python3 automatesbn.py  

#Understand the flow of program

The existing system present used was giving output using a dictionary containing two words i.e., English root word and their equivalent German word. But the existing system was giving output for some of the files that are incorrect for sbn notation. So we have created a python code that will compare the sbn files of german and English accordingly and will specify the error on which file is not correct. 

First, we have extracted a list of files inside the raw-sbn folder. then we sorted it according to the file name. we pulled folder name and file name for ex - p00/d072 . we then used this folder and file name to extract the sbn files from both PMB-4.0.0-de-gold  and PMB-4.0.0-en-gold folders.  we wanted a left-hand side of the sbn notation of eng and german sbn files so we used string manipulation to get a string which is having left-hand side part. then we compared both the strings. if both strings were equal we input it to sbnfileall and else we output it as an error to sbnmismatchdeeng file 
