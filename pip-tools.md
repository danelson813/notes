## Install pip-tools

python -m venv venv
source venv/bin/activate
pip install pip-tools
touch requirements.in
add the direct dependencies
pip-compile ./requirements.in
to upgrade package:
    pip-compile --upgrade -package <filename>
to sync your venv with current requirements.txt file:
    pip-sync