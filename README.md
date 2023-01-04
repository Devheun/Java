# Java
To practice Java (Beginner)


##  Day 1
---
#### 자바 소스코드의 구조

클래스 블록{
메서드 블록{
명령문
}
}

ex.
```
public class Sample{
 public static void main(String[] args){
  System.out.println("Hello Java");
 }
}
```

#### 변수와 자료형

변수는 C언어 규칙과 동일

자주 쓰이는 자료형 : int, long, double, String, StringBuffer, List, Map, Set 등등

사용자 정의 자료형  
```
class Desk{}

Desk chair;
```

##  Day 2
---
자료형
---
#### 숫자 (Number)
- 정수 : int, long (int 최댓값 넘을 때 L 접미사 붙여줘야함)
- 실수 : float, double (디폴트가 double이므로 float에 대입할 땐 F 붙여줘야함)
- 8진수와 16진수 (int 자료형으로 표시, 0으로 시작하면 8진수, 0x로 시작하면 16진수)
- 사칙연산, 증감연산(++,--)

#### 불 (boolean)
- boolean a=true; boolean b=false;

#### 문자 (char)
- 한 개의 문자 값 : char 자료형 이용

#### 문자열 (String)
- ex) String a = 'Hello Friend"

문자열 내장 메서드
 > equals : 두개의 문자열이 동일한지를 비교하여 결과값 리턴 ex: (a.equals(b))
 
 > indexOf : 문자열에서 특정 문자열이 시작되는 인덱스 리턴 ex: a.indexOf("Java")
 
 > contains : 문자열에서 특정 문자열이 포함되어 있는지 여부 리턴 ex: a.contains("Java")
 
 > charAt : 문자열에서 특정 위치의 문자 리턴 ex: a.charAt(6)
 
 > replaceAll : 문자열 중 특정 문자열을 다른 문자열로 바꿀 때 ex: a.replace("Java","World")
 
 > substring: 문자열 중 특정 부분 뽑아낼 경우 ex : a.substring(0,4)
 
 > toUpperCase : 문자열을 모두 대문자로 변경할 때 ex: a.toUpperCase()
 
 > split : 문자열을 특정 구분자로 나누어 문자열 배열로 리턴 ex: a.split(":")
 
 > 문자열 포매팅
 
  - ex) System.out.println(String.format("I eat %d apples.",3));
  
  - ex) System.out.println(String,format("I eat %s apples.","five"));
  
  - ex) int number=3; System.out.println(String.format("I eat %d apples.",number));
  
  

위에서 살펴본 int,long,double,float,boolean,char 자료형은 원시(primitive) 자료형이라 부른다.
(원시 자료형은 new 키워드로 값 생성 불가)



