# Summary

> [MERN Stack Crash Course Tutorial (The Net Ninja, youtube)](https://www.youtube.com/playlist?list=PL4cUxeGkcC9iJ_KkrkBZWZRHVwnzLIoUE)

영상을 따라가면서 만들 예정이고, 새로 배운 점이나 정리하고 싶은 점들을 아래에 정리할 예정이다.

## #2

```bash
$ node server.js
```

이렇게 해줘도 되지만 새로고침 했을 때 적용이 안됨

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

