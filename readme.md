## Flask Tutorial
https://flask.palletsprojects.com/en/stable/tutorial/

### 1 - Criar/Resetar Sqlite3
```bash
flask --app flaskr init-db
```

### 2 - Install
```bash
pip install -e .
```

### 3 - RUN DEBUG
```bash
flask --app flaskr run --debug
```

### 4 - Testes
```bash
pytest
pytest -v
coverage run -m pytest
coverage report
```

### 5 - DEPLOY
```bash
pip install build
python -m build --wheel
```
copiar o dist/flaskr-1.0.0-py3-none-any.whl para outra maquina (onde sera rodado o código)
```bash
pip install flaskr-1.0.0-py3-none-any.whl
flask --app flaskr init-db
flask --app flaskr init-db
```
gerar uma key aleatória (para usar em vez de 'dev')
```bash
python -c 'import secrets; print(secrets.token_hex())'
```
production WSGI server
```bash
pip install waitress
waitress-serve --call 'flaskr:create_app'
```