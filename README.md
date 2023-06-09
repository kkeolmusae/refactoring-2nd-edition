# Refactoring 2nd Edition

> 💡 <Refactoring 리팩터링 2판>을 읽으며 정리한 글입니다.

</br>

## 계획적이고 체계적인 리팩터링의 필요성

### 초판의 추천사

- 리팩터링에도 위험이 따른다. **리팩터링이란 동작하는 코드를 수정하는 것이고, 그 과정에서 미묘한 버그가 생길 수 있다.** 잘못 수행하면 오히려 며칠 혹은 몇 주간의 시간과 노력이 수포로 돌아갈 수 있다. **제대로 된 연습 없이 즉흥적으로 실시하는 리팩터링은 더욱 위험하다.** 코드를 분석하다가 새롭게 수정할 부분을 발견하면 즉흥적으로 더 깊이 파기 시작하는 사람이 많은데, 그럴수록 수정할 부분이 더 많아져 마침내 헤어날 수 없는 구렁텅이에 빠지게 된다. **자기 무덤을 파지 않으려면 리팩터링을 반드시 계획적이며 체계적으로 해야 한다.**
  </br>

### 들어가며

- **리팩터링**이란?
  리팩터링은 **겉으로 드러나는 코드의 기능(겉보기 동작)은 바꾸지 않으면서 내부 구조를 개선하는 방식으로 소프트웨어 시스템을 수정하는 과정**이다. 버그가 생길 가능성을 최소로 줄이면서 코드를 정리하는 정제된 방법이다. 리팩터링한다는 것은 코드를 작성하고 난 뒤에 설계를 개선하는 일이다.
- 리팩터링을 하면 일의 균형이 바뀐다. **처음부터 완벽한 설계를 갖추기보다는 개발을 진행하면서 지속적으로 설계**한다. 시스템을 구축하는 과정에서 더 나은 설계가 무엇인지 배우게 된다. 그 결과, 개발의 시작부터 끝날 때까지 프로그램은 줄곧 우수한 설계를 유지한다.
  </br>

### 한국어판 독자를 위한 안내

- 한국어판 출간 후 갱신되는 내용, 공지, 기타 유용한 정보가 있으면 아래 깃허브 페이지를 통해 공유한다.
- 이 책은 공식 소스코드를 제공하지 않으며, 대신 다른 독자가 많은 코드의 링크가 깃허브 페이지에 있으니 필요하면 참고한다.
- [리팩터링 2판 지원 github](https://github.com/WegraLee/Refactoring)

</br>

### 공부 계획

- 2023년도 2분기동안 최소 1번은 정독할 **계획**이다.

</br>

### 공부 목표

- 코드 퀄리티 향상 시키기

</br>

### 책 구조 간단 설명

- 1장: 리팩토링이 뭔지 모를 때 읽자. 리팩토링 진행 절차를 간단하게 보여준다.
- 1장, 2장: 리팩토링이 무엇이고, 왜 필요한지 설명해준다.
- 3장: 리팩토링이 필요한 곳을 찾는데 도움을 준다. (악취 찾기)
- 4장: 테스트 구축하는 것에 대해 설명해준다.
- 5장이후: 어떤 기법이 있는지 알려준다. (카탈로그)

</br>

### 리팩토링을 해야하는 유형

#### 기이한 이름
- 함수 선언 바꾸기(6.5)
- 변수 이름 바꾸기(6.7)
- 필드 이름 바꾸기(9.2)


#### 중복 코드
- 함수 추출하기(6.1)
- 문장 슬라이드하기(8.6)
- 메서드 올리기(12.1)


#### 긴 함수
- 함수 추출하기(6.1)
- 임시변수를 질의 함수로 바꾸기(7.4)
- 매개변수 객체 만들기(6.8)
- 객체 통째로 넘기기(11.4)
- 함수를 명령으로 바꾸기(11.9)
- 조건문 분해하기(10.1)
- 조건부 로직을 다형성으로 바꾸기(10.4)
- 반복문 쪼개기(8.7)


#### 긴 매개변수 목록
- 매개변수를 질의 함수로 바꾸기(11.5)
- 객체 통쨰로 넘기기(11.4)
- 매개변수 객체 만들기(6.8)
- 플래그 인수 제거하기(11.3)
- 여러 함수를 클래스로 묶기(6.9)


#### 전역 데이터
- 변수 캡슐화하기(6.6)


#### 가변 데이터
- 변수 캡슐화하기(6.6)
- 변수 쪼개기(9.1)
- 문장 슬라이드하기(8.6)
- 함수 추출하기(6.1)
- 질의 함수와 변경 함수 분리하기(11.1)
- 세터 제거하기(11.7)
- 파생 변수를 질의 함수로 바꾸기(9.3)
- 여러 함수를 클래스로 묶기(6.9)
- 여러 함수를 변환 함수로 묶기(6.10)
- 참조를 값으로 바꾸기(9.4)


#### 뒤엉킨 변경
- 단계 쪼개기(6.11)
- 함수 옮기기(8.1)
- 함수 추출하기(6.1)
- 클래스 추출하기(7.5)


#### 산탄총 수술
- 함수 옮기기(8.1)
- 필드 옮기기(8.2)
- 여러 함수를 클래스로 묶기(6.9)
- 여러 함수를 변환 함수로 묶기(6.10)
- 함수 인라인하기(6.2)
- 클래스 인라인하기(7.6)


#### 기능 편애
- 함수 옮기기(8.1)
- 함수 추출하기(6.1)


#### 데이터 뭉치
- 클래스 추출하기(7.5)
- 매개변수 객체 만들기(6.8)
- 객체 통째로 넘기기(11.4)


#### 기본형 집착
- 기본형을 객체로 바꾸기(7.3)
- 타입 코드를 서브클래스로 바꾸기(12.6)
- 조건부 로직을 다형성으로 바꾸기(10.4)
- 클래스 추출하기(7.5)
- 매개변수 객체 만들기(6.8)


#### 반복되는 switch문
- 조건부 로직을 다형성으로 바꾸기(10.4)


#### 반복문
- 반복문을 파이프라인으로 바꾸기(8.8)


#### 성의 없는 요소
- 함수 인라인하기(6.2)
- 클래스 인라인하기(7.6)
- 계층 합치기(12.9)


#### 추측성 일반화
- 계층 합치기(12.9)
- 함수 인라인하기(6.2)
- 클래스 인라인하기(7.6)
- 함수 선언 바꾸기(6.5)
- 죽은 코드 제거하기(8.9)


#### 임시 필드
- 클래스 추출하기(7.5)
- 함수 옮기기(8.1)
- 특이 케이스 추가하기(10.5)


#### 메시지 체인
- 위임 숨기기(7.7)
- 함수 추출하기(6.1)
- 함수 옮기기(8.1)


#### 중개자
- 중개자 제거하기(7.8)
- 함수 인라인하기(6.2)


#### 내부자 거래
- 함수 옮기기(8.1)
- 필드 옮기기(8.2)
- 위임 숨기기(7.7)
- 서브클래스를 위임으로 바꾸기(12.10)
- 슈퍼클래스를 위임으로 바꾸기(12.11)


#### 거대한 클래스
- 클래스 추출하기(7.5)
- 슈퍼클래스 추출하기(12.8)
- 타입 코드를 서브클래스로 바꾸기(12.6)


#### 서로 다른 인터페이스의 대안 클래스들
- 함수 선언 바꾸기(6.5)
- 함수 옮기기(8.1)
- 슈퍼클래스 추출하기(12.8)


#### 데이터 클래스
- 레코드 캡슐화하기(7.1)
- 세터 제거하기(11.7)
- 함수 옮기기(8.1)
- 함수 추출하기(6.1)
- 단계 쪼개기(6.11)


#### 상속 포기
- 서브클래스를 위임으로 바꾸기(12.10)
- 슈퍼클래스를 위임으로 바꾸기(12.11)


#### 주석
- 함수 추출하기(6.1)
- 함수 선언 바꾸기(6.5)
- 어서션 추가하기(10.6)
