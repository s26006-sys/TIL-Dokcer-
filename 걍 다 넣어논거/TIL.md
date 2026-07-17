# 자바 프로그램 실행
Java 프로그램의 기본 구조
```
public class Hellojava {
    public static void main(String[] args) {
        System.out.println("hello java");
    }
}
```
# 주석
주석은 소스코드가 복잡해 그 코드에 대한 설명을 쓰고 싶을떄나 특정 코드를 지우지 않고 잠시 실행을 막아두고 싶을때 사용한다.
<br><br>
한줄 주석 넣는법
`//`기호로 시작해서 쓰면 이후 텍스트는 주석으로 처리된다
<br>
예시 - //주석
<br><br>
여러줄 주석 넣는법
`/*`로 시작해서 `*/` 로 끝낸다. 
<br>
예시 - /* 여러줄 주석 */

# 변수
변수란?
<br>
이름 그대로 변할 수 있는 값이란 뜻
<br>
## 변수 선언
`int a`
숫자 정수를 보관할 수 있는 이름이 `a`라는 데이터 저장소를 만든다, 이것을 변수라 한다
## 변수 값에 대입
변수에 값 대입 하는법
<br>
`a =10`
<br>
## 변수 값 읽기
`system.out.println(a)`->변수 a의 값을 읽음
## 변수 타입
```
int -> 정수  예시 / 100
double -> 실수  예시 / 10.5
boolean -> Ture나 False 입력 가능  예시 / ture
char -> 문자하나  예시 / 'A'
string -> 문자열을 다루기 위한 특별한 타입  예시 / "Hello java"
```
```
        정수
byte b = 127; //-128 ~ 127
        short s = 32767; // -32,768 ~ 32,767
        int i = 2147483647; //-2,147,483,648 ~ 2,147,483,647 (약 20억)

        //-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807
        long l = 9223372036854775807L;

        실수
        float f = 10.0f;
        double d = 10.0;
```
# 변수 명명 규칙

## 규칙
변수 숫자로 시작 안됨<br>
이름에 공백 못 들어감<br>
예약어는 변수 이름 x<br>
변수 이름에는 영문자 숫자 믿줄만 사용 가능

## 관례
변수 이름은 소문자로 시작하는게 일반적
그 이후 단어는 대문자로 시작하는 표기법(낙타 표기법)
예시)orderDetail
<br>
자바에서 클래스는 대문자로 시작 그리고 나머지는 모두 첫 글자를 소문자로 시작.
상수는 전부 대문자
패키지는 모두 소문자
*변수는 이름이 의미 있고 그 용도를 명확히 설명해야함

# 연산자

## 연산자 종류
산술 `+`,`-`,`*`,`/`,`%`<BR>
증감(증가 및 감소)`++`,`--`<BR>
비교 연산자 `==`,`!=`,`>`,`<`,`>=`,`<=`<BR>
논리 연산자 `&&`(AND),`||`(OR),`!`(NOT)<BR>
대입 연산자 `=`,`+=`,`-=`,`*=`,`/=`,`%=`<BR>
삼항 연산자 `?`,`:`<BR>

## 연산자와 피연산자
```
3 + 4
a + b
```
연산자 : 연산 기호 - 예)`+`,`-`
피연산자 : 연산 대상 - 예)`3`,`4`,`a`,`b`

## 산술 연산자
`+`,`-`,`*`,`/`,`%` 
<br>주의 0으로 나눌수없음
<br>`ex) 10/0`
## 문자열 더하기
```
1. string result1 ="hello" + "world"
->hello world
2.string result2 = s1 + s2
```
## 문자열과 숫자 더하기
```
1. "a+b = " +10
2. 변수가 담겨도 문자와 숫자를 더하면 문자가 된다
```
## 연산자 우선 순위
덧셈보다 곱셉이 우선
<br>
예시)1+(2*3)=7
<br>
연산자 우선 순위 바꿀려면 () 괄호 사용<br>
코드가 많으면 괄호 사용하면 읽기 편함

## 우선순위
1.괄호<br>
2.단항 연산자<br>
3.산술 연산자<br>
4.shift 연산자<br>
5.비교 연산자<br>
6.등식 연산자<br>
7.비트연산자<br>
8.논리연산자<br>
9.삼항 연산자<br>
10.대입 연산자<br>

대부분 상식선에서 생각하면 문제가 없다

## 증감 연산자

증감 연산자란 증가 및 연산자를 줄여서 증감 연산자라 한다.
`++`,`--`로 표현 되고 이들은 변수 값을 1만큼 증가 시키거나 감소시킴

예시
```
++a; = a = a+1
```
증감 연산자는 피연산자 앞에 두거나 뒤에 둘수 있으면,연산자의 위치에 따라 연산이 수행되는 시점이 달라진다.<br>
`++a`값을 먼저 증가<br>
`a++`변수를 쓰고 마지막에 증가

예시.1 (++a)
```
int a = 1;
int b = 0;

b = ++a;
system.out.println("a =" + a + ",b =" +b);

->  a의 값을 먼저 증가시키고, 그 결과를 b에 대입 [ a =2 , b =2 ]
```
예시.2 (a++)
```
a = 1;
b = 0;

b = a++;
system.out.println("a =" + a + ",b =" +b);

->a의 현재 값을 b에 먼저 대입하고, 그 후 a 값을 증가시킴 (a = 2,b =1)
```
단독으로 사용하는 경우에는 다른 연산이 없기 때문에 본인 값만 증가한다.
전위든 후위든 똑같음

## 비교 연산자
`==` 동등성<BR>
`!=` 불일치<BR>
`>` 크다<BR>
`<` 작다<BR>
`>=` 크거나 같다<BR>
`<=` 작거나 같다<BR>
`=` 대입 연산자 <BR>
`==` 동등<BR>
## 논리 연산자
`&&`  ,AND (그리고)<BR>
`||`  ,OR (또는) <BR>
`!`  ,NOT (부정)

## 대입 연산자
`=`오른쪽의 값을 왼쪽 변수에 넣음<BR>
`+=`더해서 대입<BR>
`-=`뺴서 대입<BR>
`*=`곱해서 대입<BR>
 `/=`나뉘서 대입<BR>
 `%=` 나눈 나머지를 대입

# 조건문

```
만약에(나이 >= 18)면 "성인"
만약 (나이 < 18>)"미성년자"
```
이렇게 특정 조건에 따라 다른 코드를 실행하는것을 '조건문'이라고 한다

## if문
예시)
```
int age = 20;

int(age >= 18) {
    system.out.println("성인") }

int(age  18) {
    system.out.println("미성년자")}
    -> 성인이라고 출력됨
```

## else
`else`문은 `if`문에서 만족하는 조건이 없을 때 실행하는 코드를 제공한다.
(생략 가능)
## else if
else if문은 앞선 if문의 조건이 거짓일 때 다음 조건을 검사한다. 만약에 앞선 if문이 참이라면 else if를 실행하지 않는다.

## switch문
switch문은 여러 개의 if-else문을 거치는 대신, **"이 값은 어디로 가야 하는지를 결정해서 해당 위치로 바로 점프하는 정거장 같은 역할이에요.

`break;`는 멈추게 하는 역할
이게 없으면 전부 출력된다

```
int medal = 1;

switch (medal) {
    case 1:
        System.out.println("금메달입니다! 축하해요.");
        break; // 여기서 멈추지 않으면 아래 case까지 다 실행돼요!
    case 2:
        System.out.println("은메달입니다! 멋져요.");
        break;
    case 3:
        System.out.println("동메달입니다! 잘했어요.");
        break;
    default:
        System.out.println("완주하신 것만으로도 충분히 가치 있어요.");
        break;
        -> "금메달입니다! 축하해요."가 출력된다
}
```
if문 vs switch문
switch문의 조건식을 넣는 부분은 단순히 값만 넣을수있다.<br>
switch문은 특정case와 같은지만 체크 가능<br>
반면 if문은 참 거짓 결과가 나오는 조건식을 자유롭게 적을 수 있다.<br>

## 새로운 switch문
기존보다 훨씬 간결하고 실수를 줄여주는 화살표 연산자(->)를 사용하는 새로운 스위치문
break 일일이 사용하지않아도됨

: 대신 -> , break 사용 X
```
int score = 95;

// 스위치문의 결과를 바로 grade 변수에 저장!
String grade = switch (score / 10) {
    case 10, 9 -> "A학점";
    case 8 -> "B학점";
    case 7 -> "C학점";
    default -> "F학점";
}; // 변수에 대입하는 거라 끝에 세미콜론(;)이 붙어요.

System.out.println("당신의 성적은 " + grade + "입니다.");
-> 당신의 성적은 A 입니다 라고 산출됨
```

## 삼항 연산자(조건 연산자)
삼항 연산자는 말 그대로 항이 3개라는 뜻.`조건`,`참_표현식`,`거짓_표현식`
이렇게 항이 3개다.
조건에 만족하면 `참_표현식`이 실행되고, 조건에 만족하지 않으면`거짓_조건식`이 실행된다.
단순 표현식만 넣을수있다.

# 반복문
반복문은 while,for문이 있다.

## while문
while문은 조건에 따라 코드를 반복해서 실행할떄 사용한다.

```
package variable2;

public class fafs {

    public static void main(String[] args) {
        int count = 0;

        while (count < 3) {
            count = count + 1;
            System.out.println("현재 숫자는:" + count);
        }
    }
}
->현재 숫자는:1
  현재 숫자는:2
  현재 숫자는:3
```
endNum 사용해서도 할수있음

## do while
조건에 상관없이 무조건 한번은 코드를 실행한다.

## break,continue
break 반복문을 즉시 종료
continue 반복문의 나머지 부분을 건너뛰고 다음 반복을 진행하는데 사용
# for문
for문은 주로 반복 횟수가 정해져 있을떄 사용한다
```
for(1.초기식; 2.조건식; 4.증감식;) {
    // 3. 코드
}

for (int i =1;,i < 10;,i++){
    system.out.println(i);
}
``` 
반복문 안에 중첩 가능

# 지역변수와 스코프

지역변수는 이름 그대로 특정 지역에서만 사용 가능한 변수
(여기서 말하는 지역이 바로 변수가 선언된 코드 블록`{}`이다)

스코프는  변수가 접근 가능한 범위


# Scanner

자바에서 제공하는 `Sytem.in`을 통해서 사용자 입력을 받으면 너무 복잡함<br>
-> 그래서 자바는 이러한 문제를 해결하기 위해 `Scanner`라는 클래스를 제공한다

예제
```
package scanner;

import java.util.Scanner;

public class Scanner2 {

    public static void main(String[] args) {
        Scanner scanner =  new Scanner(System.in);

        System.out.println("첫번쨰 숫자를 입력하세요:");
        int num1 = scanner.nextInt();

        System.out.println("두번째 숫자를 입력하세요:");
        int num2 = scanner.nextInt();

        int sum = num1 + num2;
        System.out.println("두 숫자의 합:"+sum);
    }
}

두개의 숫자를 입력하고 두 숫자의 합을 출력하는 코드예제
```

`Scanner scanner =  new Scanner(System.in);`은 `scanner`의 기능을 사용하기 위해 `new`를 사용해 scanner를 만든다.

 `Scanner scanner`는  `Scanner` 변수를 선언하는것

 scanner.nextInt();은 엔터(\n)를 입력할 때 까지 문자를 가져옴

print는 그대로 출력
println은 출력하고 엔터

## scanner 반복예제
`exit`라는 문자를 입력되면 프로그램 종료

# 배열 시작

배열은 같은 타입의 변수를 사용하기 편하게 하나로 묶어둔것이다.

배열이 필요한 이유
예를 들어 코드를 짜고 거기에 몇가지만 추가하고 싶을떄 양이 많으면 힘들지만배열을 쓰면 편하게 해결 가능


예시
```
package array;

public class Array1 {

    public static void main(String[] args) {
        int student1 = 90;
        int student2 = 80;
        int student3 = 70;
        int student4 = 60;
        int student5 = 50;

        System.out.println("학생1 점수: " + student1);
        System.out.println("학생2 점수: " + student2);
        System.out.println("학생3 점수: " + student3);
        System.out.println("학생4 점수: " + student4);
        System.out.println("학생5 점수: " + student5);
    }
}
```

## 배열 변수 선언
  
`int[] students;` 배열 변수 선언
`new int[]` 배열 생성

## 배열 사용
배열은 변수 사용법과 비슷한데 배열은 `[]`사이에 숫자번호를 넣는다<BR><BR>
배열위치를 나타내는 숫자를 인덱스라고 한다.

    java
int[] students = new int[5]; `배열생성`<br>
int[] students = x001; `nwe int[5]의 결과로 x001 참조값 반환`<br>
syudents = x001 `최종결과`<br>

# 기본형과 참조형
- 기본형 -> 사용하는 값을 직접 넣을 수 있는 기본형<br>
- 참조형 -> 위에서 본 배열변수와 같이 메모리의 참조값을 넣을수 있는 참조형
객체나 클래스를 담을수있는 변수도 모두 참조형

#  
