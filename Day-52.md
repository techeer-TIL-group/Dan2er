부트캠프 때 공부했었던 JWT  (Json Web Token) 에 대하여 찾아보면서 부트캠프 당시 코드들을 살펴보았다. 

인코딩이 되지 않은 토큰은

`eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c`

이런 형식으로 존재한다.

해더(Header) 에서 해쉬 알고리즘과 토큰의 타입을 정할 수 있으며 

Base 64 로 인코딩 했을 때

```
{
  "sub": "1234567890",
  "name": "Daehee Kim",
  "iat": 1516239022
}
```

와 같은 Payload Data 를 불러올 수 있는 것이다. 

여기서 Key 와 Value 값을 확인해 볼 수 있다.
