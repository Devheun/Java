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
