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

##  Day 3
---
자료형
---
#### StringBuffer : 문자열을 추가하거나 변경 할 때 사용하는 자료형 (StringBuilder 자료형은 똑같이 쓰되 동기화 고려할 필요 없을때)

메서드
> append : 문자열을 추가하는 메서드

ex)

```
StringBuffer sb = new StringBuffer();
sb.append("hello");
sb.append(" ");
sb.append("jump to java");
String result=sb.toString();
System.out.println(result); //"hello jump to java" 출력됨
```
위와 동일한 출력값 내는 코드

```
String result="";
result+="hello";
result+=" ";
result+="jump to java";
System.out.println(result); // "hello jump to java" 출력됨
```

차이점 : 첫번째는 StringBuffer 객체가 한번만 생성되는 반면, 두번째는 String 자료형에 + 연산 있을때마다 객체 생성돼 총 4개

String 자료형은 immutable, StringBuffer는 mutable

*Tip* : StringBuffer 자료형은 String 자료형보다 무거운 편이므로, 문자열 추가나 변경이 많으면 StringBuffer, 거의 없으면 String

> insert : 특정 위치에 원하는 문자열 삽입 가능
```
StringBuffer sb = new StringBuffer();
sb.append("jump to java");
sb.insert(0,"hello");
System.out.println(sb.toString()); // "hello jump to java" 출력됨
```

> substring : String의 substring 메서드와 동일
```
StringBuffer sb = new StringBuffer();
sb.append("Hello jump to java");
System.out.println(sb.substring(0,4)); // "Hell" 출력됨
```
