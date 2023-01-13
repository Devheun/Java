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





