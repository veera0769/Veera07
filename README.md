pip install virtualenv
python –m venv venv
pip install Flask
flask –version
from flask import Flask
app = Flask(__name__)
@app.route(‘/’)
def home():
return “Hello, Flask!”
if __name__ == ‘__main__’:
app.run(debug=True)
# On Windows (CMD)
set FLASK_APP=app.py
# On Windows (Powershell)
$env:FLASK_APP = “app.py”
flask run
export FLASK_ENV=development
