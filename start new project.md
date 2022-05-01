## start new project

mkdir <project_name>

cd <project_name>

touch main.py

python -m venv venv

source venv/pip/activate

python -m pip install --upgrade pip

pip install jupyter

pip install ipykernel

python -m ipykernel install --user --name=venv

python -m ipykernel install --user --name=<project_name>
