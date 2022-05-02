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

json file: saving a json file with secrets.
cd <project-dir>
touch secrets.json
echo "secrets.json >> .gitignore'


example:
{
'DB_HOST': ",
'DB_PORT': 0,
'DB_NAME': "",
'DB_USER': "",
'DB_PASSWORD': "",
'PURCHASES_REPORT_KEY': "",
'APP_AUTH_KEY': "",
'APP_CLIENT_KEY': ""
}

To read the file and import this function from other parts of your project
import os
import json
def read_secrets() -> dict:
    filename = os.path.join('secrets.json')
    try:
        with open(filename, mode="r") as f:
            return json.loads(f.read())
    except FileNotFoundError:
        return {}

secrets = read_secrets()