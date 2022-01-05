# Deploy
## Procfile Python
```
worker: python ファイル名.py
```
## Procfile Flask
```
web: gunicorn app:ファイル名
```
## requirements.txt
```
pip freeze > requirements.txt
```
## CMD
```
heroku login
heroku create プロジェクト名

git init
git add .
git remote add heroku https://---
git commit -m'commit_name'
git push heroku master
```
## settings
Buildpacks

## Chromedriver
### code
```
driver_path = '/app/.chromedriver/bin/chromedriver'
options = webdriver.ChromeOptions()
options.add_argument('--headless')
driver = webdriver.Chrome(options=options, executable_path=driver_path)
```
### Buildpacks
https://github.com/heroku/heroku-buildpack-chromedriver.git  
https://github.com/heroku/heroku-buildpack-google-chrome.git

## json
### code
```
./ファイル名.json
```
### file
same directory
