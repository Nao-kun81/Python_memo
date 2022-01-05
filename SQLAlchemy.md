# データベース構築
## モデル作成
```
from flask import Flask
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:////tmp/test.db'
db = SQLAlchemy(app)

class User(db.Model):
  id = db.Column(db.Integer, primary_key=True)
  username = db.Column(db.String(80), unique=True)
  email = db.Column(db.String(120), unique=True)
  
  def __init__(self, username, email):
    self.username = username
    self.email = email
    
  def __repr__(self):
    return '<User %r>' % self.username
    
```
### 詳細
Integer = 数字  
String = 文字列  
primary_key = 自動生成される数列  
unique = データベース内の重複  
null = 空白  
## データベース作成
Pythonの対話モード
```
from app import db
db.create_all()
```
# CRUD操作
## C=create
```
user = User('name', 'mailadress@gmail.com')
db.session.add(user)
db.session.commit()
```
## R=read
```
users = User.query.all()
```
## U=update/R=read
```
user = db.session.query(User).filter_by(name='name').first()
user.email = 'mailadress@gmail.com'
db.session.add(user)
db.session.commit()
```
## D=delete/R=read
```
user = db.session.query(User).filter_by(name='name').first()
db.session.delete(user)
db.session.commit()
```
