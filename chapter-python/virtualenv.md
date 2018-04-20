## Install and use virtual environment

Install virtualenv via pip:

1. Make sure you have python and pip installed
```
pip install virtualenv
```
If your using version control, dont forget to add your venv to your gitignore
```
touch .gitignore
```
open file and write 
**venv/**

2. Create a virtual environment
```
virtualenv venv
```
3. Activate virtual environment
```
source venv/Scripts/activate
```
4. Deactivate your virtual environment
```
deactivate
```
5. Freeze your environment so you can create a file with all the libs you have installed in your virtual environment
```
pip freeze > requirements.txt
```
6. Install requirements
```
pip install -r requirements.txt
```
