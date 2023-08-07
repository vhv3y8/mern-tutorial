# Summary

> [MERN Stack Crash Course Tutorial (The Net Ninja, youtube)](https://www.youtube.com/playlist?list=PL4cUxeGkcC9iJ_KkrkBZWZRHVwnzLIoUE)

영상을 따라가면서 만들거고, 새로 배운 점이나 정리하고 싶은 점들을 아래에 정리할 예정이다.

## #2

```bash
$ node server.js
```

이렇게 해줘도 되지만 파일 내용을 바꿨을 때 적용이 안됨

```bash
$ npm i -g nodemon
```

`nodemon`이라는 패키지를 global로 설치해서 사용하자

```json
{
  ...
  "dev": "nodemon server.js",
  ...
}
```

```bash
$ npm run dev
```

---

`.env` => `.gitignore`에 추가하면 github 같은 데에 올릴 때 private 됨

여기선 PORT 번호만 했지만 access token 같은 걸 할 때 이렇게 하면 공개되지 않게 쓸 수가 있다.

```bash
$ npm i dotenv
```

`dotenv`라는 패키지를 쓰면 됨

```js
require("dotenv").config()
```

```js
app.listen(4000, () => {
  console.log("listening on port 4000!")
})
```

여기서 4000 대신에

```js
app.listen(process.env.PORT, () => {
  console.log("listening on port 4000!")
})
```

이렇게 써주면 똑같이 동작함

## #3

router, middleware나 request, response가 어떤 원리인지 같은 express 개념들은 따로 공부해야할듯

## #4

[https://www.mongodb.com/atlas/database](https://www.mongodb.com/atlas/database)

mongoDB를 로컬에 설치해서 쓸 수도 있지만 온라인으로도 제공함 = mongoDB atlas

```bash
$ npm i mongoose
```

connection string 주는 페이지에서는 `mongodb` 설치하라고 하는데 여기서는 `mongoose`를 사용하는듯함

이유도 설명했는데 잘 이해가 안되서 못알아들음

아이디나 비번이 다르면 `npm run dev` 했을 때 에러나고,

맞으면 `"connected to db & listening on port 4000!"` 라고 뜨는 것까지 확인함

## #5

mongodb만 있으면 schemaless, mongoose가 model이랑 schema를 만들게 해주는 것임

workout document 저장할 때 schema를 enforce 해줄 것이다

모델이 하는 건 스키마를 특정 모델에 적용시키는거.

postman에서 POST 보내보고, 필드 없으면 없어서 안된다는 에러 봤음

그리고 mongoDB 사이트 > Browse Collections로 들어가서 저장된 걸 봤다.