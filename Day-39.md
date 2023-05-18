오늘은 파이썬 query 문을 이용하여 회원가입 기능 구현을 복기해 보았다.

```

from flask import Flask, render_template, request
import mysql.connector

app = Flask(**name**)

db = mysql.connector.connect(
host="localhost",
user="username",
password="password",
database="database_name"
)

@app.route('/')
def signup():
return render_template('signup.html')

@app.route('/signup', methods=['POST'])
def signup_post():
# 회원 정보 받아오기
name = request.form['name']
email = request.form['email']
password = request.form['password']

cursor = db.cursor()
query = "INSERT INTO users (name, email, password) VALUES (%s, %s, %s)"
values = (name, email, password)
cursor.execute(query, values)
db.commit()

return '회원가입이 완료되었습니다.'

if **name** == '**main**':
app.run()
```

참고 링크는 

[[FLASK 클론코딩] 추가강의 - 로그인 구현하기! (파이썬으로 웹사이트 만들기)](https://www.youtube.com/watch?v=SaDHmBerx7o)
