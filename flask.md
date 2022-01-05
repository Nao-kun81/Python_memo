# jinja
## htmlファイルにpythonの変数を扱う
```
{{ 変数名 }}
```
## for文
```
{% for a in b%}
{% for a in range(5) %}

{% endfor %}
```
## if文
```
{% if a == b %}
{% endif %}
```
## block
```
{% block contents %}
{% endblock %}
```
# html継承
```
{% extends 'index.html' %}
```
# サーバ起動
## PowerShell
```
$env:FLASK_APP = "app"
$env:FLASK_ENV = "development"
flask run
```
## CMD
```
set FLASK_APP=app
set FLASK_ENV=development
flask run
```
