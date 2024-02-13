# Linux

## 🚩 Shell에서의 return

- shell script에서는 `return` 반환값이 d없다.
  - `exit`을 통해 상태 종료 표시만을 프로세스 실행 결과로 반환할 수 있음
  - 일반적으로 `0`은 성공, 나머지인 `1 ~ 255`는 에러
- Shell 스크립트 함수에서 결과값 받기
  - `$(명령어 or 쉘 스크립트 실행 or 쉘 스크립트 함수)`와 같이 `$`와 `()`안에 명령어, 쉘 스크립트 또는 쉘 스크립트 함수를 넣으면 해당 부분들을(명령어, 쉘 스크립트 또는 쉘 스크립트 함수) 실행할 subshell을 호출
  - 해당 `$()`를 통한 subshell 생성은 부모 shell의 변수나 값들을 가져오기 때문에 함수도 변수도 다 사용할 수 있습니다. 다만, subshell의 결과가 부모 shell에 영향을 주지는 않습니다.

[쉘 스크립트 함수나 실행에서 반환값(Return Value) 얻기](https://twpower.github.io/134-how-to-return-shell-scipt-value)

