# Interview

๐ฉ ์ฃผ์ ํ๋ก์ ํธ ๊ด๋ จํ์ฌ ๊ธฐ์ , ๊ด์ ์ ๋ํ ์ค๋ช

- ์ธ์ฆ์ด๋ ๊ถํ ๊ด๋ฆฌ๋ ์ด๋ค ๋ฐฉ์์ผ๋ก ์ด๋ฃจ์ด์ง๋์ง

- ์ฌ์ฉํ๋ ์๋ฐ ๋ฒ์ 

- ๋ฆฌ์ปค๋ฒ๋ฆฌ ๊ด๋ฆฌ๊ฐ ์ด๋ป๊ฒ ๋๊ณ  ์๋์ง

๐ฉ ์ด์ง ์ฌ์ 

๐ฉ ํ์คํธ ์ฝ๋์์ mock/stub ๊ตฌ๋ถ ๋ฐ ์ค์ 

```text
Test Double :
- ํ์คํธ ํ๋ ค๋ ๊ฐ์ฒด๊ฐ ๋ค๋ฅธ ๊ฐ์ฒด๋ค๊ณผ ์ฌ๋ฌ ๊ด๊ณ๊ฐ ์ฎ์ฌ์์ด ์ฌ์ฉํ๊ธฐ ์ด๋ ค์ธ ๋, ๋์ฒดํ  ์ ์๋ ๊ฐ์ฒด
- Dummy, Stub, Spy, Mock, Fake

mock : 
- ํ์ ๊ฒ์ฆ (๋ฉ์๋์ ๋ฆฌํด ๊ฐ์ผ๋ก ํ๋จํ  ์ ์๋ ๊ฒฝ์ฐ ํน์  ๋์์ ์ํํ๋์งํ์ธํ๋ ๊ฒ์ฆ๋ฒ)
- ํธ์ถ์ ๋ํ ๊ธฐ๋๋ฅผ ๋ช์ธํ๊ณ , ๋ด์ฉ์ ๋ฐ๋ผ ๋์ํ๋๋ก ํ๋ก๊ทธ๋๋ฐ ๋ ๊ฐ์ฒด (์์ ํ  ๊ฒ์ผ๋ก ์์๋๋ ๊ธฐ๋๊ฐ์ ๋ฏธ๋ฆฌ ์ ์)
- ํ์คํธ ์์ฑ์ ์ํ ํ๊ฒฝ ๊ตฌ์ถ์ด ์ด๋ ค์ธ ๋, ํ์คํธํ๊ณ ์ ํ๋ ์ฝ๋์ ์ฎ์ธ ๊ฐ์ฒด๋ค์ ๋์ ํ๊ธฐ ์ํด ๋ง๋ค์ด์ง ๊ฐ์ฒด

stub : 
- ์ํ ๊ฒ์ฆ (๋ฉ์๋๊ฐ ์ํ๋ ํ, ๊ฐ์ฒด์ ์ํ๋ฅผ ํ์ธํ์ฌ ์ฌ๋ฐ๋ฅด๊ฒ ๋์ํ๋์ง๋ฅผ ํ์ธํ๋ ๊ฒ์ฆ๋ฒ)
- ์ธ์คํด์คํํ์ฌ ๊ตฌํํ ๊ฐ์ง ๊ฐ์ฒด(=Dummy. ๊ธฐ๋ฅ ๊ตฌํ X)๋ฅผ ์ด์ฉํด ์ค์ ๋ก ๋์ํ๋ ๊ฒ์ฒ๋ผ ๋ณด์ด๊ฒ ๋ง๋๋ ๊ฐ์ฒด
- ํด๋น ์ธํฐํ์ด์ค or ํด๋์ค๋ฅผ ์ต์ํ์ผ๋ก ๊ตฌํ
- ํ์คํธ์์ ํธ์ถ๋ ์์ฒญ์ ๋ํด "๋ฏธ๋ฆฌ ์ค๋นํด๋ ๊ฒฐ๊ณผ๋ฅผ ์ ๋ฌ"
- ํ์คํธ๋ฅผ ์ํด ํ๋ก๊ทธ๋๋ฐ๋ ๊ฒ ์ธ์๋ ์๋ตํ์ง ์์
- ํ๋ ฅ๊ฐ์ฒด์ ํน์  ๋ถ๋ถ์ด ํ์คํธํ๊ธฐ ํ๋ค ๊ฒฝ์ฐ stub์ ์ฌ์ฉํ๋ฉด ์์ํ๊ฒ ํ์คํธ ๊ฐ๋ฅ
```

๐ฉ ๋ณธ์ธ์ด Java ์ฝ๋ฉ์ ์ ํ๋ค๊ณ  ์๊ฐํ๋์ง?

- ๋ณ๋ ฌ Stream ๋์ ๋ฐฉ์์ ๋ํ ์ค๋ช
- [Modern Java In Action](https://jihunparkme.github.io/Modern_Java_In_Action/#%EB%B3%91%EB%A0%AC-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B2%98%EB%A6%AC%EC%99%80-%EC%84%B1%EB%8A%A5)

๐ฉ ์ธ์ด ๊ด์ ์์ ์ ๋์ฝ๋์ ๋ํด ์ค๋ช

```text
- ๊ตญ์ ์ ์ผ๋ก ์ ์ธ๊ณ ์ธ์ด๋ฅผ ๋ชจ๋ ํ์ํ  ์ ์๋ ํ์ค์ฝ๋
- ๊ธ์์ ์ฝ๋๊ฐ 1:1๋งคํ๋์ด ์๋ โ์ฝ๋ํ'
- ํ๊ธ '๊ฐ'๋ ์ ๋์ฝ๋๋ก 'U+AC00'
```

๐ฉ ๋ฒ์  ๊ด๋ฆฌ ํด์ ์ด๋ค ๊ฒ์ ์ฌ์ฉํ๋์ง

- [Gogs](https://gogs.io/) : ๊ฐ์ธ github ๊ตฌ์ฑ

๐ฉ Github reset, revert ๊ตฌ๋ถ

```text
reset : ์๊ฐ์ ์์ ๊ณผ๊ฑฐ์ ํน์  ์ฌ๊ฑด(commit)์ผ๋ก ๋๋๋ฆฐ๋ค.

revert : ํ์ฌ์ ์์ผ๋ฉด์ ๊ณผ๊ฑฐ์ ํน์  ์ฌ๊ฑด(commit)๋ค๋ง ์๋ ์ผ๋ก ๋ง๋ ๋ค.
```

๐ฉ Github์์ ์ถ์ ์ด ๊ฐ๋ฅํ๊ฒ ํ๋ ค๋ฉด ๋ฌด์์ ์ฌ์ฉํด์ผ ํ๋์ง

```text
Git์์ ์ถ์ ํ๋ค๋ ์๋ฏธ๋ ๊ทธ ํ์ผ์ ๊ด๋ฆฌํ๋ค๋ ์๋ฏธ
ํ๋ก์ ํธ ์์ํด๋์๋ Tracked ํ์ผ๊ณผ Untracked ํ์ผ์ด ์กด์ฌํ๋๋ฐ
Tracked ์ํ์ ํ์ผ์ Unmodified, Modified, Staged ์ค์ ํ ์ํ๋ก ์กด์ฌ

Tracked(๊ด๋ฆฌ๋์์ด ๋ ํ์ผ, ์ถ์ ๋๊ณ  ์๋ ์ํ)
- Unmodified : ํ์ผ ๋ด์ฉ ์์ ์ด ์๋ ์ํ
- Modified : ํ์ผ ๋ด์ฉ์ด ์์ ๋ ์ํ
- Staged : ์ปค๋ฐ์ผ๋ก Git ์ ์ฅ์์ ๊ธฐ๋ก๋  ์ค๋น๊ฐ ๋ ์ํ

UnTracked(๊ด๋ฆฌ๋์์ด ์๋ ํ์ผ, ์ฆ ์ถ์ ์ด ์๋ ์ํ)

Commit(์ปค๋ฐ) : ํ์ผ์ Git ์ ์ฅ์์ ๊ธฐ๋กํ๋ ๊ฒ, ์ด๋ค ์์์ธ์ง์ ๋ํ ๋ฉ์์ง๋ฅผ ๊ธฐ๋กํจ
```

๐ฉ IntelliJ๋ก ๋ฆฌํํฐ๋ง๋ ๋ง์ด ํ๋์ง

๐ฉ IntelliJ๊ฐ ์ดํด๋ฆฝ์ค๋ณด๋ค ํธํ ์ 

๐ฉ IntelliJ์์ ํธ๋ฆฌํ๊ฒ ์ฌ์ฉํ๋ ํ๋ฌ๊ทธ์ธ

๐ฉ heap ์๋ฃ๊ตฌ์กฐ์ ๋ํ ์ค๋ช

```text
- ์ต๋๊ฐ ๋ฐ ์ต์๊ฐ์ ์ฐพ์๋ด๋ ์ฐ์ฐ์ ๋น ๋ฅด๊ฒ ํ๊ธฐ ์ํด ๊ณ ์๋ ์์ ์ด์งํธ๋ฆฌ๋ฅผ ๊ธฐ๋ณธ์ผ๋ก ํ ์๋ฃ๊ตฌ์กฐ
- A๊ฐ B์ ๋ถ๋ชจ๋ธ๋(parent node) ์ด๋ฉด, A์ ํค(key)๊ฐ๊ณผ B์ ํค๊ฐ ์ฌ์ด์๋ ๋์๊ด๊ณ๊ฐ ์ฑ๋ฆฝ
```

๐ฉ CQS์ ๋ํ์ฌ ๋ค์ด๋ณด์๋์ง. ์ด๋ค ์๋ฏธ์ธ์ง

- Command Query Separation
- ์ง์(query)์ ๋ช๋ น(command)์ ์ ํํ ๋ถ๋ฆฌํ๋ ๊ฒ์ ๋ชฉ์ 
- query(์ง์)๋ ๊ฒฐ๊ณผ๊ฐ์ ๋ฐํํ๊ณ , ์์คํ์ ์ํ๋ฅผ ๋ณํ์ํค์ง ์๋๋ค. ์ฆ ๋ถ์์ฉ์์ ์์ ๋กญ๋ค.(free of side effets)
- command(๋ช๋ น)์ ๊ฒฐ๊ณผ๋ฅผ ๋ฐํํ์ง ์๊ณ , ์์คํ์ ์ํ๋ฅผ ๋ณ๊ฒฝํ๋ค.

๐ฉ @Transactional ์์ฑ์ ๋ํ ์ค๋ช

- [Spring @Transactional ์ ์ฌ์ฉํด๋ณด๊ธฐ](https://data-make.tistory.com/738)

๐ฉ ์ด์ปค๋จธ์ค ์๋ฌด ์ค์ ์ด๋ค ์๋ฌด๋ฅผ ๋ณด๊ณ  ์ง์์ ํ ๊ฒ์ธ์ง

๐ฉ ๋ณต์กํ ๋น์ฆ๋์ค ์์ฒญ ํน์ ์ด๋ ค์ด ๋ฌธ์ ๋ฅผ ์ค์ค๋ก ํด๊ฒฐํด๋ณธ ๊ฒฝํ

๐ฉ ๋ ๊ฑฐ์ ์ฝ๋๊ฐ ์ด๋ค ๊ฒ์ด๋ผ๊ณ  ์๊ฐํ๋์ง

- ์ดํดํ๊ธฐ ์ด๋ ต๊ณ  ์ ์ง๋ณด์ํ๊ธฐ ์ด๋ ค์ด ์ฝ๋
- ํ๋์ ๋ฉ์๋ ์์ ์ฌ๋ฌ ์ญํ ์ด ํฌํจ๋์ด ์๋ ๊ฒ

๐ฉ Front ์ชฝ์ ์ด๋์ ๋ ํด๋ณด์๋์ง

---

๐ฉ 2์ฐจ

- 
