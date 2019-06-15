# Go Backend Template
> golang中使用echo框架、MongoDB、JWT搭建REST API

## 依赖

- labstack/echo

- gopkg.in/mgo.v2

- dgrijalva/jwt-go

## 运行

1. 启动 mongoDB
2. 运行 `main.go`

## 测试

**用户注册**

```bash
curl -X POST http://localhost:1323/signup -H "Content-Type:application/json" -d '{"email" :"leonwangchn@163.com", "password":"test"}'
```

**登录**

```bash
curl -X POST http://localhost:1323/login -H "Content-Type:application/json" -d '{"email" :"leonwangchn@163.com", "password":"test"}'
```

返回

```json
{"id":"5d0466b98f1ce9576b28d12a",
 "email":"leonwangchn@163.com",
 "token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1NjA4Mjg3MzcsImlkIjoiNWQwNDY2Yjk4ZjFjZTk1NzZiMjhkMTJhIn0.Hs8fVDRz0KkTuiBVlhKrw045Bg9zyf2rMfOatZsr7bw"}
```

**Follow用户**

```bash
curl -X POST http://localhost:1323/follow/5d0466b98f1ce9576b28d12a -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1NjA4Mjg3MzcsImlkIjoiNWQwNDY2Yjk4ZjFjZTk1NzZiMjhkMTJhIn0.Hs8fVDRz0KkTuiBVlhKrw045Bg9zyf2rMfOatZsr7bw"
```

**发送消息（邮件）**

```bash
curl -X POST http://localhost:1323/posts -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1NjA4Mjg3MzcsImlkIjoiNWQwNDY2Yjk4ZjFjZTk1NzZiMjhkMTJhIn0.Hs8fVDRz0KkTuiBVlhKrw045Bg9zyf2rMfOatZsr7bw" -H "Content-Type: application/json" -d '{"to":"5d0466b98f1ce9576b28d12a","message":"hello"}'
```

**数据库视角**

1. twitter.users

    ![users](readme/users.png)

2. twitter.posts

    ![posts](readme/posts.png)

