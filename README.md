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

#### 배열 (Array) : 자료형의 집합

```
int[] odds={1,3,5,7,9};
String[] weeks={"월","화","수","목","금","토","일"};
```

배열의 길이는 고정, 배열 값 접근은 인덱싱

#### 리스트 (List) : 배열과 비슷하지만 크기가 정해져있지 않고 동적으로 변함

> ArrayList : 파이썬의 리스트와 비슷한듯?

```
import java.util.ArrayList;

public class Sample{
 public static void main(String[] args){
  ArrayList pitches = new ArrayList();
  pitches.add("138");
  ptiches.add("129");
  pitches.add("142");
  System.out.println(pitches.get(1)): // 129 출력됨
  System.out.println(pitches.size()); // 3 출력됨
  System.out.println(pitches.contains("142")); //true 출력됨
  System.out.println(pitches.remove("129")); // true 출력됨, 리스트에서 객체에 해당되는 항목 삭제하고 결과 리턴
  System.out.println(pitches.remove(0)); // 138 출력됨, 해당 인덱스의 항목 삭제하고 삭제된 항목 리턴
 }
}
```

*Tip* : **제네릭스**

```
ArrayList<String> pitches = new ArrayList<>(); // "ArrayList 안에 담을 수 있는 자료형은 String 타입 뿐"
```


```
import java.util.ArrayList;
import java.util.Arrays;

public class Samble{
 public static void main(String[] args){
  String[] data={"138","129","142"};
  ArrayList<String> pitches = new ArrayList<>(Arrays.asList(data));
  System.out.println(pitches); // [138,129,142] 출력됨
 }
}
```

다른 예시 : "138", "129","142" 로 이루어진 ArrayList 콤마로 구분하여 하나의 문자열로 만들기 (String.join 이용)

```
import java.util.ArrayList;
import java.util.Arrays;

public class Sample{
 public static void main(String[] args){
  ArrayList<String> pitches = new ArrayList<>(Arrays.asList("138","129","142"));
  String result = String.join(",",pitches);
  System.out.println(result); // 138, 129, 142 출력
 }
}
```

** 리스트 정렬하기 **

```
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Comparator;

public class Sample{
 public static void main(String[] args){
  ArrayList<String> pitches = new ArrayList<>(Arrays.asList("138","129","142"));
  pitches.sort(Comparator.naturalOrder()); // 오름차순으로 정렬, 내림차순은 reverseOrder
  System.out.println(pitches); // [129,138,142] 출력
 }
}

```

##  Day 4

---
자료형
---

#### 맵 (Map) : Key와 Value를 한 쌍으로 갖는 자료형

> HashMap
>> put : HashMap에 key와 value를 추가하는 메서드
```
import java.util.HashMap;
public class Main {
    public static void main(String[] args) {
        HashMap<String,String> map = new HashMap<>();
        map.put("people","사람");
        map.put("baseball","야구");
    }
}
```

>> get : key에 해당하는 value 값 얻을 때 사용하는 메서드

```
System.out.println(map.get("people")); // "사람" 출력됨
```

>> containsKey : 맵에 키가 있는지 조사하여 그 유무를 참, 거짓으로 리턴

```
System.out.println(map.containsKey("people")); // true 출력됨
```

>> remove : 맵의 항목을 삭제하는 메서드

```
System.out.println(map.remove("people")); // "사람" 출력됨, 삭제도 됨
```

>> size: 맵의 개수 리턴
```
System.out.println(map.size()); // 1 출력됨
```

>> keySet : 맵의 모든 Key를 모아서 리턴 ( Set 자료형으로 리턴)

**Tip** : LinkedHashMap은 입력된 순서대로 데이터를 저장, TreeMap은 입력된 key의 오름차순 순서로 데이터 저장

#### 집합 (Set) : 중복 X, 순서 X

> 집합 자료형 만들기

```
import java.util.Arrays;
import java.util.HashSet;
public class Main {
    public static void main(String[] args) {
        HashSet<String> set=new HashSet<>(Arrays.asList("H","e","l","l","o"));
        System.out.println(set); // [e,H,l,o] 출력
    }
}
```

> 교집합 구하기

```
import java.util.Arrays;
import java.util.HashSet;
public class Main {
    public static void main(String[] args) {
        HashSet<Integer> s1=new HashSet<>(Arrays.asList(1,2,3,4,5,6));
        HashSet<Integer> s2=new HashSet<>(Arrays.asList(4,5,6,7,8,9));
        HashSet<Integer> intersection=new HashSet<>(s1);
        intersection.retainAll(s2); // 교집합 수행
        System.out.println(intersection); //[4,5,6] 출력
    }
}

```

> 합집합 구하기

```
import java.util.Arrays;
import java.util.HashSet;
public class Main {
    public static void main(String[] args) {
        HashSet<Integer> s1=new HashSet<>(Arrays.asList(1,2,3,4,5,6));
        HashSet<Integer> s2=new HashSet<>(Arrays.asList(4,5,6,7,8,9));
        HashSet<Integer> union=new HashSet<>(s1);
        union.addAll(s2); // 합집합 수행
        System.out.println(union); //[1,2,3,4,5,6,7,8,9] 출력
    }
}
```

> 차집합 구하기

```
import java.util.Arrays;
import java.util.HashSet;
public class Main {
    public static void main(String[] args) {
        HashSet<Integer> s1=new HashSet<>(Arrays.asList(1,2,3,4,5,6));
        HashSet<Integer> s2=new HashSet<>(Arrays.asList(4,5,6,7,8,9));
        HashSet<Integer> substract=new HashSet<>(s1);
        substract.removeAll(s2); //차집합 수행
        System.out.println(substract); //[1,2,3] 출력
    }
}
```

> 집합 자료형 관련 메서드 : add(값 추가), addAll(값 여러개 추가), remove(특정 값 제거)

**Tip** : TreeSet은 오름차순으로 값을 정렬하여 저장, LinkedHashSet은 입력한 순서대로 값을 정렬하여 저장

#### 상수집합 (Enum) : 서로 관련이 있는 여러 개의 상수 집합 정의할 때 사용, 장점-잘못된 값으로 인한 위험성 X, 매직넘버 사용할 때보다 코드 명확해짐

> Enum 만들기

```
public class Sample {
    enum CoffeeType {
        AMERICANO,
        ICE_AMERICANO,
        CAFE_LATTE
    };
    public static void main(String[] args) {
        for(CoffeeType type:CoffeeType.values()){ // CoffeeType.values()는 CoffeeType의 배열 리턴
         System.out.println(type); // AMERICANO,ICE_AMERICANO,CAFE_LATTE 출력됨
        }
    }
}
```

##  Day 5

---
자료형
---

#### 형변환

> 문자열을 정수로 바꾸기

```
public class Sample{
 public static void main(String[] args){
  String num="123";
  int n=Integer.parseInt(num); // Integer 클래스 사용
  System.out.println(n); // 123 출력됨
 }
}
```

> 정수를 문자열로 바꾸기

```
public class Sample{
 public static void main(String[] args){
  int n=123;
  
  String num="" + n; // 정수 앞에 빈 문자열 더해주기
  String num1= String.valueOf(n); 
  String num2= Integer.toString(n);
  
  System.out.println(num); // 123 출력됨
  System.out.println(num1); // 123 출력됨
  System.out.println(num2); // 123 출력됨
 }
}
```

> 소숫점 포함된 문자열을 실수로 바꾸기

```
public class Sample{
 public static void main(String[] args){
  String num="123.456";
  double d = Double.parseDouble(num); //Double.parseDouble 또는 Float.parseFloat 로 가능
  System.out.println(d); // 123.456 출력됨
 }
}
```

> 정수와 실수 사이 형 변환

```
public class Sample{
 public static void main(String[] args){
  int n1=123;
  double d1 = n1; // 정수를 실수로 바꿀땐 캐스팅 필요 X
  System.out.println(d1); // 123.0 출력됨
  
  double d2=123.456;
  int n2=(int)d2; // 실수를 정수로 바꿀 땐 반드시 정수형으로 캐스팅
  System.out.println(n2); // 123 출력됨
 }
}
```

> 실수 형태의 문자열을 정수로 변경 : Double.parseDouble()로 실수로 바꾼 후에 정수로 변환해야함 !

#### final : 값을 한번 설정하면 다시 설정 불가 !

**Tip** : 리스트는 final로 선언 시 값을 더하거나 빼는 것은 가능, 재할당만 불가. 더하거나 빼는 것 불가능하게 하려면 List.of 사용

##  Day 6

---
제어문
---

#### if문

> if문의 기본구조

```
if(조건문){
 <수행할 문장1>;
 <수행할 문장2>;
}else{
 <수행할 문장A>;
 <수행 문장B>;
}
```

> 비교연산자 : C언어와 동일

> and, or, not 연산자 ( &&, ||, !)

> contains : List 자료형에서 해당 아이템이 있는지 조사할 때 사용

> else if

#### switch/case 문

기본 구조
```
switch(입력변수){
 case 입력값1:...
   break;
 case 입력값2:...
   break;
 ...
 default:...
   break;
}
```

**Tip** : switch 조건문에 들어갈 수 있는 입력변수 타입은 byte, short, char, int만 가능하다.

#### while문

기본 구조
```
while (조건문){
 <수행할 문장1>;
 <수행할 문장2>;
 <수행할 문장3>;
 ...
}
```

> 무한 루프

```
while (true){
 <수행할 문장1>;
 <수행할 문장2>;
 ...
}
```

> while문 빠져 나가기 (break)

ex)
```
public class practice2{
    public static void main(String[] args){
        int coffee=10;
        int money=300;
        while (money>=0){
            System.out.println("돈을 받았으니 커피 줌");
            coffee--;
            System.out.println("남은 커피의 양은 " + coffee);
            if (coffee==0){
                System.out.println("커피가 다 떨어졌습니다. 판매중지");
                break;
            }
        }
    }
}
```

> while문 조건문으로 돌아가기(continue)

ex)

```
int a=0;
        while (a<10){
            a++;
            if (a%2==0){
                continue;
            }
            System.out.println(a);
        }
```

#### for 문

> for문의 구조

```
String[] numbers= {"one","two","three"};
for(int i=0;i<numbers.length;i++){
 System.out.println(numbers[i]);
}
```

예시 : 5명의 학생이 시험 보았는데, 시험점수 60점 넘으면 합격, 아님 불합격인데 판단하여 출력

```
int[] marks={90,25,67,45,80};
        for (int i=0;i<marks.length;i++){
            if (marks[i]>=60){
                System.out.println((i+1)+"번 학생은 합격입니다.");
            }else{
                System.out.println((i+1)+"번 학생은 불합격입니다.");
            }
        }
```

> continue가 for 문에서도 동일하게 적용됨

> 이중 for문

구구단 출력해보기

```
for (int i=2;i<=9;i++){
           for (int j=1;j<=9;j++){
               System.out.print(i*j+" ");
           }
           System.out.println("");
       }
```

**Tip** : System.out.print는 줄바꿈문자(\n)을 포함하지 않고 출력함.


## Day 7

---
제어문
---

> for each

for (type var: iterate){
  body-of-loop
}


iterate : 루프를 돌릴 객체
itreate 객체에서 한 개씩 순차적으로 var에 대입됨
( iterate로 사용할 수 있는 자료형은 루프를 돌릴 수 있는 자료형만 가능 ex) 배열 및 ArrayList 등)

ex)

```
String[] numbers = {"one","two","three"};
for(String number: numbers){
  System.out.println(numer);
}
```

**Tip** : 반복회수를 명시적으로 주는것이 불가능하고, 1스탭씩 순차적으로 반복할때만 사용가능

## Day 8

---
객체지향 프로그래밍
---

> 클래스

보통 클래스는 특별한 경우가 아니라면 파일 단위로 하나씩 작성.

클래스는 **객체를 만드는 기능**을 한다.

인스턴스라는 말은 특정 객체가 어떤 클래스의 객체인지 관계위주로 설명할 때 사용.

클래스에 의해 생성되는 것은 객체, 그 클래스에 선언된 변수는 객체 변수

객체 변수 접근 : 객체.객체변수

메서드 : 클래스 내에 구현된 함수

메서드 접근 : 객체.메서드

**객체 변수의 값은 독립적으로 유지된다. 즉 공유되지 않는다.**

> 메서드

메서드를 사용하는 이유 : 여러 번 반복해서 사용하는 것을 한번에 !

매개변수: 메서드에 입력으로 전달된 값을 받는 변수

인수 : 메서드를 호출할 때 전달하는 입력값

**메서드의 구조**

```
리턴자료형 메서드명(입력자료형1 매개변수1, 입력자료형2 매개변수2, ...){
  ...
  return 리턴값; // 리턴자료형 void면 return 필요 없음
}
```

**메서드 내에서 선언된 변수의 효력 범위**

ex)
```
public class Sample {
    void varTest(int a) {
        a++;
    }

    public static void main(String[] args) {
        int a = 1;
        Sample sample = new Sample();
        sample.varTest(a);
        System.out.println(a); // 1 출력됨
    }
}
```

증가시키기 위해선

```
public class Sample {
    int varTest(int a) {
        a++;
        return a;
    }

    public static void main(String[] args) {
        int a = 1;
        Sample sample = new Sample();
        a = sample.varTest(a);
        System.out.println(a); // 2 출력됨
    }
}
```

또는 

```
public class Sample{
  int a;
  
  void varTest(){
    this.a++;
  }
  
  public static void main(String[] args){
    Sample sample = new Sample();
    sample.a=1;
    sample.varTest();
    System.out.println(sample.a); // 2 출력됨
  }
}
```

## Day 9

---
객체지향 프로그래밍
---

> Call by value

값을 전달하는 경우

```
class Updater{
  void update(int count){
    count++;
  }
}

class Counter{
  int count=0;
}

class Main {
  public static void main(String[] args){
    Counter myCounter = new Counter();
    System.out.println(myCounter.count); // 0 출력됨
    Updater myUpdater = new Updater();
    myUpdater.update(myCounter.count);
    System.out.println(myCounter.count); // 0 출력됨
  }
}
```

객체를 전달하는 경우

```
class Updater{
  void update(Counter counter){
    counter.count++;
  }
}

class Counter{
  int count=0;
}

class Main {
  public static void main(String[] args){
    Counter myCounter = new Counter();
    System.out.println(myCounter.count); // 0 출력됨
    Updater myUpdater = new Updater();
    myUpdater.update(myCounter);
    System.out.println(myCounter.count); // 1 출력됨
  }
}

```

**메서드에 객체를 전달할 경우 메서드에서 객체의 객체변수 값을 변경할 수 있다**

> 상속

자식 클래스가 부모 클래스의 기능을 그대로 물려받을 수 있는 기능

```

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Dog extends Animal {
  void sleep() {
    System.out.println(this.name + " zzz");
  }
}

class Main {
  public static void main(String[] args) {
    Dog dog = new Dog();
    dog.setName("puppy");
    System.out.println(dog.name);
    dog.sleep();
  }
}

```

> IS-A 관계 : Animal dog = new Dog(); // Dog is a Animal, 개로 만든 객체는 동물 자료형이다.

*주의해야할 점* : Dog 객체를 Animal 자료형으로 사용할 경우 Dog 클래스에 존재하는 메서드 사용불가. Animal 클래스에 구현된 메서드만 사용가능

Dog dog = new Animal(); //이런 코드는 컴파일 에러뜸, 동물로 만든 객체는 개 자료형이다. <- 조금 이상함


> 메서드 오버라이딩 : 메서드 덮어쓰기 개념으로 부모클래스의 메서드를 자식클래스가 동일한 형태로 또다시 구현하여 더 높은 우선순위를 갖게 되는것

```

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Dog extends Animal {
  void sleep() {
    System.out.println(this.name + " zzz");
  }
}

class HouseDog extends Dog {
  void sleep() {
    System.out.println(this.name + " zzz in house");
  }
}

class Main {
  public static void main(String[] args) {
    HouseDog houseDog = new HouseDog();
    houseDog.setName("happy");
    houseDog.sleep(); /// happy zzz in house 출력됨
  }
}

```

> 메서드 오버로딩 : 메서드의 입력항목이 다른 경우 동일한 이름의 메서드를 만들 수 있다.

```

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Dog extends Animal {
  void sleep() {
    System.out.println(this.name + " zzz");
  }
}

class HouseDog extends Dog {
  void sleep() {
    System.out.println(this.name + " zzz in house");
  }

  void sleep(int hour) {
    System.out.println(this.name + " zzz in house for " + hour + " hours");
  }
}

class Main {
  public static void main(String[] args) {
    HouseDog houseDog = new HouseDog();
    houseDog.setName("happy");
    houseDog.sleep();
    houseDog.sleep(5);
  }
}

```

> 다중 상속 : 자바는 **지원안함** !!!

> 생성자(Constructor)

객체 변수에 값을 무조건 설정해야만 객체가 생성되도록 할 때 생성자를 이용하면 된다 !!

객체 생성 방법이 생성자의 규칙과 맞아야지만 생성가능하다.

**생성자의 규칙**

1. 클래스명과 메서드명이 동일하다.
2. 리턴타입을 정의하지 않는다.

```

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Dog extends Animal {
  void sleep() {
    System.out.println(this.name + " zzz");
  }
}

class HouseDog extends Dog {
  HouseDog(String name) { // 생성자 추가 !!
    this.setName(name);
  }

  void sleep() {
    System.out.println(this.name + " zzz in house");
  }

  void sleep(int hour) {
    System.out.println(this.name + " zzz in house for " + hour + " hours");
  }
}

class Main {
  public static void main(String[] args) {
    HouseDog dog = new HouseDog("happy");
    System.out.println(dog.name);
  }
}

```

> 디폴트 생성자 : 생성자의 입력 항목이 없고 생성자 내부에 아무 내용이 없는 생성자

클래스에 생성자가 하나도 없다면 컴파일러는 자동으로 디폴트 생성자 추가. 하지만 생성자가 하나라도 구현되어있으면 추가 X

```
class Dog extends Animal{
  Dog(){
  }
  void sleep(){
    System.out.println(this.name+" zzz");
  }
}
```

> 생성자 오버로딩: 메서드에 오버로딩 처럼 생성자에도 오버로딩 가능

```

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Dog extends Animal {
  Dog() {

  }

  void sleep() {
    System.out.println(this.name + " zzz");
  }
}

class HouseDog extends Dog {

  HouseDog(String name) { // 여기선 String 자료형을 입력으로 받는 생성자
    this.setName(name);
  }

  HouseDog(int type) { // 여기선 int 자료형을 입력으로 받는 생성자
    if (type == 1) {
      this.setName("york");
    } else if (type == 2) {
      this.setName("bulldog");
    }
  }

  void sleep() {
    System.out.println(this.name + " zzz in house");
  }

  void sleep(int hour) {
    System.out.println(this.name + " zzz in house for " + hour + " hours");
  }
}

class Main {
  public static void main(String[] args) {
    HouseDog happy = new HouseDog("happy");
    HouseDog york = new HouseDog(1);
    System.out.println(happy.name);
    System.out.println(york.name);
  }
}

```


## Day 10

---
객체지향 프로그래밍
---


> 인터페이스는 왜 필요한가? : 귀찮음을 극복하고자

```

interface Predator { // 육식동물 인터페이스

}

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Tiger extends Animal implements Predator {

}

class Lion extends Animal implements Predator {

}

class ZooKeeper {
  void feed(Predator predator){
    System.out.println("feed apple");
  }
}

class Main {
  public static void main(String[] args) {
    ZooKeeper zooKeeper = new ZooKeeper();

    Tiger tiger = new Tiger();
    Lion lion = new Lion();
    zooKeeper.feed(tiger);
    zooKeeper.feed(lion);
  }
}

```


상속에서 본 IS-A 관계가 인터페이스에서도 마찬가지로 적용됨.

ex) tiger - Tiger 클래스의 객체, Predator 인터페이스의 객체

    lion - Lion 클래스의 객체, Predator 인터페이스의 객체
    
    
이런식으로 어떤 육식동물이 추가되더라도 ZooKeeper는 feed 메서드를 추가할 필요 없이 Predator 인터페이스를 구현한 클래스를 작성하기하면 하면 된다.

```
class Crocodile extends Animal implements Predator{}
```


위의 코드는 항상 feed apple 만을 출력하므로 인터페이스에 메서드를 추가 !!

```
interface Predator{
	String getFood();
}
```

인터페이스 메서드는 몸통이 없음 !

getFood라는 메서드는 인터페이스를 implements한 클래스들이 구현해야 한다.

**인터페이스의 메서드는 항상 public으로 구현해야함**

```
interface Predator { // 육식동물 인터페이스
  String getFood();
}

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Tiger extends Animal implements Predator {
  public String getFood() {
    return "apple";
  }
}

class Lion extends Animal implements Predator {
  public String getFood() {
    return "banana";
  }
}

class ZooKeeper {

  void feed(Predator predator) {
    System.out.println("feed " + predator.getFood());
  }
}

class Main {
  public static void main(String[] args) {
    ZooKeeper zooKeeper = new ZooKeeper();

    Tiger tiger = new Tiger();
    Lion lion = new Lion();
    zooKeeper.feed(tiger);
    zooKeeper.feed(lion);
  }
}
```

인터페이스를 구현함으로써 ZooKeeper 클래스가 동물들의 종류에 의존적인 클래스에서 동물들의 종류와 상관없는 독립적인 클래스가 되었다!

물리적 세계 - 자바 세계

컴퓨터 - ZooKeeper

USB포트 - Predator

하드디스크, 디지털카메라 - Tiger,Lion,…

>  디폴트 메서드 : 인터페이스의 메서드는 몸통을 가질 수 없지만 디폴트 메서드를 사용하면 실제 구현된 형태의 메서드를 가질 수 있다.

ex)

```
interface Predator{
	String getFood();

	default void printFood(){
		System.out.printf(“my food is %s\n”, getFood());
}
}
```

디폴트 메서드는 메서드명 가장 앞에 “default”라고 표기해야함.

디폴트 메서드는 오버라이딩이 가능하다.

> 스태틱 메서드 : 인터페이스명.스태틱메서드명 형식으로 사용가능

```
interface Predator { // 육식동물 인터페이스
  String getFood();
  default void printFood()
  {
    System.out.printf("my food is %s\n", getFood());
  }

  int LEG_COUNT=4; //인터페이스 상수
  static int speed(){
    return LEG_COUNT * 30;
  }
}
```

Predator.speed();  // 이런식으로 사용가능


## Day 11

---
객체지향 프로그래밍
---


> 다형성

```
interface Predator { // 육식동물 인터페이스
  String getFood();
  default void printFood()
  {
    System.out.printf("my food is %s\n", getFood());
  }

  int LEG_COUNT=4; //인터페이스 상수
  static int speed(){
    return LEG_COUNT * 30;
  }
}

interface Barkable{
  void bark();
}

class Animal {
  String name;

  void setName(String name) {
    this.name = name;
  }
}

class Tiger extends Animal implements Predator, Barkable {
  public String getFood() {
    return "apple";
  }
  public void bark(){
    System.out.println("어흥");
  }
}

class Lion extends Animal implements Predator,Barkable {
  public String getFood() {
    return "banana";
  }
  public void bark(){
    System.out.println("으르렁");
  }
}

class Bouncer{
  void barkAnimal(Barkable animal){
    animal.bark();
  }
}

class ZooKeeper {

  void feed(Predator predator) {
    System.out.println("feed " + predator.getFood());
  }
}

class Main {
  public static void main(String[] args) {
    Tiger tiger = new Tiger();
    Lion lion = new Lion();

    Bouncer bouncer = new Bouncer();
    bouncer.barkAnimal(tiger);
    bouncer.barkAnimal(lion);
  }
}

```

위의 코드에서 보듯이 인터페이스는 콤마를 이용하여 여러개를 implements 할 수 있다.

tiger, lion 객체는 각각 Tiger, Lion 클래스의 객체이면서 Animal 클래스의 객체이기도 하고 Barkable, Predator 인터페이스의 객체이기도 하다.

이렇게 하나의 객체가 여러개의 자료형 타입을 가질 수 있는 것을 다향성(Polymorphism)이라고 한다.

알아두어야 할 점은 Predator로 선언된 predator 객체와 Barkable로 선언된 barkable 객체는 사용할 수 있는 메서드가 서로 다르다!

만약 getFood 메서드와 bark 메서드를 모두 사용하고 싶다면 ??

Predator, Barkable 인터페이스를 구현한 Tiger 로 선언된 tiger 객체를 그대로 사용하거나, getFood, bark 메서드를 모두 포함하는 새로운 인터페이스를 새로 만들면 됨!

ex)
```
interface BarkablePredator extends Predator, Barkable{}
```

인터페이스는 일반 클래스와 달리 extends를 이용하여 여러개의 인터페이스를 동시에 상속 가능! ( 다중 상속 지원, 일반 클래스는 단일상속만 가능)

```
class Lion extends Animal implements BarkablePredator{
  public String getFood() {
    return "banana";
  }
  public void bark(){
    System.out.println("으르렁");
  }
}
```


결과는 동일하게 출력됨.

Bouncer 클래스의 barkAnimal 메서드의 입력 자료형이 Barkable 이더라도 BarkablePredator를 구현한 lion 객체를 전달 할 수 있음.

왜냐? 상속을 받은 자식 인터페이스이기때문

> 추상클래스 : 인터페이스 역할도 하면서 클래스의 기능도 가지고 있는 클래스


```
abstract class Predator extends Animal { 
  abstract String getFood();
  void printFood()
  {
    System.out.printf("my food is %s\n", getFood());
  }

  static int LEG_COUNT=4; // 추상 클래스의 상수는 static 선언이 필요
  static int speed(){
    return LEG_COUNT * 30;
  }
}
```


추상클래스를 만들기 위해선 class 앞에 abstract 표기.

메서드에도 역시 abstract 표기 (getFood method)

abstract 메서드도 인터페이스의 메서드처럼 몸통 X, 즉, abstract 클래스를 상속하는 클래스에서 해당 abstract 메서드를 구현해야만 함!!

인터페이스의 디폴트 메서드 더 이상 사용할 수 없으므로 삭제하여 일반 메서드로 변경.

추상 클래스는 명시적으로 상수에 static 이라고 적어주어야함

**
추상 클래스는 일반 클래스와 달리 단독으로 객체 생성할 수 없음. 반드시 추상 클래스를 상속한 실제 클래스를 통해서만 생성 가능!!**


추상 클래스에는 abstract 메서드 외에 실제 메서드도 사용할 수 있다. 추상 클래스에 실제 메서드를 추가하면 Tiger, Lion 등으로 만들어진 객체에서 그 메서드들을 모두 사용할 수 있음 !!

여기선 원래 인터페이스에서 default 메서드로 사용했던 printFood가 추상클래스의 실제 메서드에 해당됨.

## Day 12

---
객체지향 프로그래밍
---

연습문제 풀이 !

## Day 13

---
입출력
---

> 콘솔 입출력

**InputStream**

```
package project;
import java.io.IOException;
import java.io.InputStream;

public class Inout{
    public static void main(String[] args) throws IOException{
        InputStream in=System.in;
        
        int a;
        a=in.read(); // 'a' 입력
        
        System.out.println(a); //97
    }
}
```

위의 코드에서 InputStream은 자바의 내장클래스, java.lang 패키지에 속하지 않은 클래스는 필요할 때 항상 import해주어야함

System.in은 InputStream의 객체이다.

InputStream의 read메서드는 1 byte의 사용자의 입력을 받아들인다. ( 1 byte의 데이터는 byte자료형이 아니라 int 자료형으로 저장됨, 아스키 코드 값으로 !!)

위의 코드에서 "a"를 입력해도 97, "abc"를 입력해도 97이 나옴. Why? read메서드는 1 byte만 읽기 때문이다.

3 byte 입력했을 때 3 byte 전부 읽고 싶다면 ?

```
package project;
import java.io.IOException;
import java.io.InputStream;

public class Inout{
    public static void main(String[] args) throws IOException{
        InputStream in=System.in;
        byte[] a = new byte[3];
        in.read(a); // "abc" 입력
        
        System.out.println(a[0]); //97
        System.out.println(a[1]); //98
        System.out.println(a[2]); //99
    }
}
```

**InputStreamReader** : 우리가 입력한 문자값을 그대로 출력하고싶을 때 !

```
package project;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;

public class Inout{
    public static void main(String[] args) throws IOException{
        InputStream in=System.in;
        InputStreamReader reader=new InputStreamReader(in);
        char[] a = new char[3]; //byte 대신 char 배열 사용가능
        reader.read(a); //"abc" 입력
        
        System.out.println(a); "abc" 출력
    }
}
```

InputStreamReader 객체를 생성할 때는 생성자의 입력으로 InputStream 객체가 필요함!

ex) InputStreamReader reader = new InputStreamReader(in);

**BufferedReader** : 고정된 길이 말고 가변적으로 !!

```
package project;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.io.BufferedReader;

public class Inout{
    public static void main(String[] args) throws IOException{
        InputStream in=System.in;
        InputStreamReader reader=new InputStreamReader(in);
        BufferedReader br= new BufferedReader(reader);
        
        String a = br.readLine(); // "Hello World" 입력
        System.out.println(a); // "Hello World"
    }
}
```

BufferedReader는 객체 생성 시 생성자의 입력으로 InputStreamReader의 객체가 필요함!

**Scanner** : J2SE 5.0부터 클래스 추가됨. 보다 콘솔 입력 쉽게

```
package project;
import java.util.Scanner;

public class Inout{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        System.out.println(sc.next());
    }
}
```

Scanner 클래스는 생성자의 입력으로 System.in, 즉 콘솔입력인 InputStream 필요 !

sc.next()는 단어 하나, sc.nextLine()은 라인 한 줄, sc.nextInt()는 정수 하나 읽음.

**콘솔 출력**

이때까지 써 온 System.out.println 메서드에서 System.out은 PrintStream 클래스의 객체이다.

(System.err 는 System.out과 동일한 역할을 하지만 오류메시지를 출력할 경우 사용된다!)







