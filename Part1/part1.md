# Part 1
## CHAPTER 1 스위프트
스위프트는 안전을 우선으로 하는 프로그래밍 패턴을 지향하고, 편리하며 고차원적인 언어, 컴파일 언어입니다.

1.2 스위프트의 언어적 특성

- 안정성 (Safe) : 옵셔널, guard 구문, 오류처리, 강력한 타입 통제 등을 통해 안전한 프로그래밍 구현.
- 신속성 (Fast) : 실행 속도의 최적화 뿐만 아니라 빠른 컴파일 성능을 구현해 나가고 있다.
- 더 나은 표현성 (Expressive) : 개발자들이 원하는 세련된 문법을 구현할 수 있다.

스위프트는 다중 패러다임 프로그래밍 언어 입니다. 크게 보면 명령형 프로그래밍(절차적 프로그래밍), 객체지향 프로그래밍, 함수형 프로그래밍, 프로토콜 지향 프로그래밍 패러다임을 차용했습니다. 가장 강조하는 부분은 함수형 프로그래밍과 프로토콜 지향 프로그래밍 패러다임입니다.

1.2.1 객체지향

객체지향 프로그래밍은 컴퓨터 프로그램을 명령어의 목록으로 보는 기존의 명령형 프로그래밍 (절차적 프로그래밍) 의 시각에서 벗어나 여러개의 독립된 단위인 객체의 모임으로 파악하고자 하는 시각입니다. 주요 특징으로는 자료 추상화, 상속, 다형성, 캡슐화 등이 있습니다.

클래스와 객체

- 클래스 : 같은 종류의 집단에 속하는 속성과 행위를 정의한 것입니다. 객체지향 프로그램의 기본 사용자정의 데이터 타입이라고 할 수 있습니다. 클래스는 다른 클래스 또는 외부 요소와 독립적으로 디자인되어야합니다.
- 객체 : 클래스의 인스턴스(실제로 메모리에 할당되어 동작하는 모양을 갖춘것, instance)입니다. 객체는 자신 고유의 속성을 가지며 클래스에서 정의한 행위를 수행할 수 있습니다. 스위프트에서는 객체라는 용어보다는 클래스의 인스턴스라는 표현을 사용합니다.
- 메서드 : 객체가 클래스에 정의된 행위를 실질적으로 수행하는 함수입니다. 메서드를 통해 객체의 명령을 전달할 수 있습니다. 객체 간에 명령 전달 또는 데이터 전달은 메서드를 통해 이루어지며 명령을 전달하거나 데이터를 전달하는 행위를 메서드를 호출한다라고 표현합니다.

1.2.2 함수형

함수형 프로그래밍은 최근 대세로 떠오르고 있습니다. 가장 큰 장점은 대규모 병렬처리가 굉장히 쉽다는 점입니다. 함수형 프로그래밍은 순수하게 함수에 전달된 인자 값만 결과에 영향을 주므로 상태 값을 갖지 않고 순수하게 함수만으로 동작합니다. 따라서 어떤 상황에서 프로그램을 실행하더라고 일정하게 같은 결과를 도출할 수 있습니다. 프로그램이 동작하는 흐름에서 상태(값)가 변화되지 않으면 함수 호출이 각각 상호 간섭없이 배타적으로 실행되므로 병렬처리를 할 때 부작용(side-effect)이 거의 없습니다. 

함수를 일급 객체로 다룬다는 점이 또다른 특징입니다.

- 전달인자(Argument) 로 전달할 수 있습니다.
- 동적 프로퍼티 할당이 가능합니다.
- 변수나 데이터 구조 안에 담을 수 있습니다.
- 반환 값으로 사용할 수 있습니다.
- 할당할 때 사용된 이름과 관계없이 고유한 객체로 구별할 수 있습니다.

```swift
func doSomething(){
	print("do something")
}

func doAnotherTing(){
	print("do another thing")
}

func excute( tasks: [ ()-> Void ] ){
	for task in tasks {
		task()
	}
}

excute( tasks: [doSomething, doAnotherTing] )

func sum(first: Int) -> ( (Int) -> Int ){
	return { second in first + second }
}

sum(first: 10)(5)

```

명령형 프로그래밍과 함수형 프로그래밍의 비교.

|               | 명령형 프로그래밍 | 함수형 프로그래밍  |
| ------------- |:-------------:| -----:|
| 프로그래머가 초점을 두는 곳 | 작업 수행 알고리즘, 상태의 변경 추적 | 원하는 정보, 필요한 변환 |
| 상태 변경      | 중요      |   없음 |
| 실행 순서      | 중요      |   낮은 중요도 |
| 주요 흐름 제어  | 제어 구문, 함수 호출  | 재귀함수 호출 등 함수 호출로 제어 |
| 주요 조작 단위  | 클래스나 구조체의 인스턴스      |   함수 |

1.2.3 프로토콜 지향

프로토콜 지향 프로그래밍은 참조 타입인 클래스의 인스턴스보다 값 타입을 더 효율적으로 사용하며, 오류를 줄일 수 있는 방안입니다. 캡슐화, 추상화, 접근제어 등의 기능을 모두 구현할 수 있습니다. 프로토콜 익스텐션을 활용하여 가능해졌습니다.


## CHAPTER 2 스위프트 처음 시작하기

print() 함수, dump() 함수 : 콘솔 로그를 남기는 용도로 사용합니다. print 함수는 간략한 정보를 출력해 주는 반면, dump 함수는 조금더 자세한 정보를 출력해 줍니다.

```swift
// print
// BasicInformation(name: "khk", age: 26)
// dump
// BasicInformation
// - name : "khk"
// - age : 26

// print
// Person
// dump
// Person #0
// - height : 180
// - weight : 78
```

문자열 보간법 : 문자열 내에 \(변수나 상수) 의 형태로 표기하면 이 변수나 상수를 문자열로 치환해서 넣어줍니다. 
```swift
let name: String ="khk"
print("My name is \(name)")
```

변수와 상수 : 변수는 생성 후 데이터 값을 변경 가능, 상수는 변경 불가. 타입 추론 가능하다.

- 변수 : var [변수명] : [데이터 타입] = [값]*
- 상수 : let [상수명] : [데이터 타입] = [값]

## CHAPTER 3 데이터 타입 기본

#### Int 와 UInt
정수 타입. Int 는  +,- 부호를 포함한 정수를 뜻하며, - 부호를 포함하지 않는 0을 포함한 야으이 정수는 UInt (unsigned int) 로 표현합니다. max, min 프로퍼티로 최대,최소값을 알 수 있습니다. 각각 8비트, 16비트, 32비트, 64비트의 형태를 가지고 있습니다. Int8 ~ Int64, UInt8 ~ UInt64. 

진수

- 10진수: 평소 쓰던 방식
- 2진수 : 0b, ex) 0b11100
- 8진수 : 0o, ex) 0o34
- 16진수 : 0x, ex) 0x1C

#### Bool
true (참) or false (거짓)

#### Float 과 Double
Float 과 Double 은 부동소수점을 사용하는 실수형이며 부동소수 타입이라고 합니다.
64비트의 부동소수 표현하는 Double 과 32비트의 부동소수 표현을 하는 Float 입니다.
64비트 환경에서 Double 은 최소 15자리의 십진수를 표현할 수 있는 반면 Float 은 6자리의 숫자까지만 표현이 가능합니다. => Double 권장.

#### Character
단 하나의 문자를 의미한다. 유니코드 문자를 사용하므로
영어는 물론, 모든 언어 및 특수기호 등을 사용할 수 있습니다. 

#### String
문자열입니다. String 에는 많은 메서드와 프로퍼티가 있습니다.

#### Any, AnyObject 와 nil
Any 는 스위프트의 모든 데이터 타입을 사용할 수 있다는 뜻입니다.
AnyObject 는 Any 보다 조금 한정된 의미로 클래스의 인스턴스만 할당할 수 있습니다.

nil 은 특정 타입이 아니라 '없음' 을 나타내는 스위프트의 키워드 입니다. nil 인 변수 또는 상수에 접근하면 잘못된 메모리 접근으로 인해 런타임 오류가 발생합니다. ( Null Point Exception ).

## CHAPTER 4 데이터 타입 고급

스위프트는 타입에 굉장히 민감하고 엄격합니다. 서로 다른 타입끼리의 데이터 교환은 꼭 타입캐스팅을 거쳐야 합니다. 

#### 타입 추론
변수나 상수를 선언할 때 특정 타입을 명시하지 않아도 컴파일러가 할당된 값을 기준으로 그 변수나 상수의 타입을 결정합니다.

#### 타입 별칭(typealias)
데이터 타입에 임의로 다른 이름(별칭)을 부여할 수 있습니다. 

```swift
typealias MyInt = Int

let age :MyInt = 100
var year :Int = 2017

year = age

```

#### 튜플
튜플은 타입의 이름이 따로 지정되어 있지 않은, 프로그래머 마음대로 만드는 타입입니다.
'지정된 데이터의 묶음'이라고 표현할 수 있습니다.

```swift
// 기본 튜플
var person : (String, Int, Double) = ("khk", 100, 180.4)
print("이름 : \(person.0) , 나이 : \(person.1) , 신장 : \(person.2) ")

// 튜플 요소 이름 지정
var person : (name : String, age: Int, height: Double) = ("khk", 100, 180.4)
print("이름 : \(person.name) , 나이 : \(person.age) , 신장 : \(person.height) ")

// 타입 별칭 이용
typealias PersonTuple = (name : String, age: Int, height: Double) 

let khk : PersonTuple = ("khk",100,120.3)
print("이름 : \(khk.name) , 나이 : \(khk.age) , 신장 : \(khk.height) ")
```

#### 배열
배열은 같은 타입의 데이터를 일렬로 순서대로 저장하는 형태의 컬렉션 타입입니다.
각기 다른 위치에 같은 값이 들어갈 수 있다. isEmpty , count 프로퍼티를 사용할 수 있습니다.
스위프트의 배열은 연결리스트(Linked-List) 형태를 띄고 있습니다.

배열은 각 요소에 인덱스를 통해 접근할 수 있습니다. 잘못된 인덱스로 접근하려고 하면 익셉션 오류가 발생합니다. 맨 처음과 맨 마지막 요소는 first 와 last 프로퍼티를 통해 가져올 수 있습니다. index(of:) 메서드를 사용하면 해당 요소의 인덱스를 알아낼 수도 있습니다. 만약, 중복된 요소가 있다면 제일 먼저 발견된 요소의 인덱스를 반환합니다. 맨 뒤에 요소를 추가하려면 append( _ : ) 메서드를 사용합니다. 중간에 요소를 추가하려면 insert( _ : at :) 메서드를 사용하면 됩니다. 삭제는 remove( _ : )

```swift
var names : Array<String> = ["gd", "top" , "zico" , "beenzino"]
var names : [String]  = ["gd", "top" , "zico" , "beenzino"]

var emptyArray : [Any] = [Any]()
var emptyArray : [Any] = Array<Any>()
var emptyArray : [Any] = []

print(emptyArray.isEmpty)
print(names.count)

names[4] = "top"
names.append("elsa")
names.append(contentsOf: ["abc","max"])
names.insert("happy", at: 2)
names.insert(contentsOf: ["jkjk","aaa"], at 5)

print(names[4])

print(names.index(of: "gd")

let firstItem : String = names.removeFirst()
let indexOneItem : String = names.remove(at : 1)

print(names[1...3])

```

#### 딕셔너리 ( Dictionary )
딕셔너리는 요소들이 순서 없이 키와 값의 쌍으로 구성되는 컬렉션 타입입니다. 단, 하나의 딕셔너리 안의 키는 그 안에서는 유일해야 합니다. 즉, 키가 두 번 쓰일 수 없다라는 뜻. 타입 별칭(typealias) 를 통해 더 단순하게 이용 가능하다. 내부에 없는 키로 접근해도 오류가 발생하지 않고 nil 을 반환합니다.
삭제는 removeValue(forKey: ) 메서드를 이용합니다.

```swift
typealias StringIntDictionary = [String: Int]

var nfn: Dictionary<String, Int> = Dictionary<String, Int>()
var nfn: [String: Int] = [String: Int]()
var nfn: [String: Int] = [:]

var nfn:StringIntDictionary = StringIntDictionary()

var nfn: [String: Int] = ["khk":10, "dfd":200]

print(nfn.isEmpty)
print(nfn.count)

print(nfn["khk"])

```

#### 세트 ( Set )
세트는 보통 순서가 중요하지 않거나 각 요소가 유일한 값을 가져야하는 경우 사용됩니다.
같은 타입의 데이터를 순서 없이 하나의 묶음으로 저장하는 형태의 컬렉션 타입입니다.
세트 내의 값은 모두 유일한 값을 가집니다. 즉, 중복된 값이 존재하지 않습니다.
배열과 달리 줄여서 표현할 수 있는 축약형이 없습니다. 
isEmpty , count 프로퍼티가 있고,
insert( _ : ) , remove( _ : ) 메서드가 있습니다.

```swift
var names: Set<String> = Set<String>()
var names: Set<String> = ["a","b","c"]

var numbers = [1,2,3]

print(type(of: numbers))
print(type(of: names))

names.insert("dkfj")
names.remove("a")
```

두 세트의 교집합, 합집합 , 포함관계 연산하기에도 매우 용이합니다.
sorted() 메서드를 통하여 정렬된 배열을 반환할 수도 있습니다.

```swift
//
```

#### 열거형 (enum)
열거형은 연관된 항목들을 묶어서 표현할 수 있는 타입.

- 제한된 선택지를 주고 싶을 때
- 정해진 값 외에는 입력받고 싶지 않을 때
- 예상된 입력 값이 한정되어 있을 때

```swift
enum School {
	case primary
	case elementary
	case middle
}
```

원시값 : 특정 타읍으로 지정된 값을 가질 수 있다. rawValue 라는 프로퍼티를 통해 가져온다.


```swift
enum School : String {
	case primary = "유치원"
	case elementart = "초등학교"
}
```

원시 값 정보를 통해 열거형 변수 또는 상수를 가져올 수 있습니다. 만약 올바르지 않은 원시값이라면 
nil 을 반환합니다.

연관값 : 열거형 내의 항목이 자신과 연관된 값을 가질 수 있습니다. 소괄호를 묶어서 표현

```swift
//
```

순환 열거형 : 순환 열거형은 열거형 항목의 연관 값이 열거형 자신의 값이고자 할 때 사용합니다. indirect 키워드를 사용합니다. 열거형 전체에 적용하고 싶다면 enum 키워드 앞에 indirect 키워드를 붙입니다.

```swift
//
```


## CHAPTER 5 연산자

스위프트에서는 띄어쓰기도 중요한 문법 중 하나입니다.

ex) 

- A != B , A! = B 
- A>B?A:B , A>B ?A:B

#### 참조 => A === B , A !== B
A와B 가 참조(레퍼런스) 타입일때 같은 인스턴스를 가리키고 있는지 비교.

#### 범위 연산자
- A...B : A 부터 B 까지의 수
- A..<B : A 부터 B 미만까지의 수

#### nil 병합 연산자 => A ?? B
A 가 nil 이 아니면 A 반환, nil 이면 B 반환

#### 옵셔널 강제 추출 연산자 => A!
A의 값을 강제로 추출합니다. nil 이면 에러 발생.
=> A != nil ? A : 0

## CHAPTER 6 흐름 제어

소괄호를 생략할 수 있습니다. 중괄호는 생략할 수 없습니다.

### 조건문

#### if
정수, 실수 등 0이 아닌 모든 값을 참으로 취급하던 언어들과는 달리 스위프트의 if 구문은
조건의 값이 꼭 Bool 타입이어야 합니다.

#### switch
break 키워드는 선택사항입니다. 즉, case 내부의 코드를 모두 실행하면 break가 없어도 switch 구문이 종료됩니다. break 하지 않고 그대로 흘려보내려면 fallthrough 키워드를 사용해야합니다.
따라서 case xxx : 아래에 꼭 실행 가능한 코드가 위치해야합니다.

switch 구문의 입력값으로 튜플도 사용 가능합니다. 또한 와일드 카드 식별자(_) , 값 바인딩을 통해서 응용할 수 있습니다.


where 키워드를 사용하여 case 의 조건을 더욱 확장할 수 있습니다.

```swift
//
```

### 반복문

#### for-in
swift3 에서 c 스타일의 for 구문이 사라졌습니다.

```swift
for 임시 상수 or 와일드카드 식별자(_) in 시퀀스 아이템 or 범위(0..<100) {
	실행코드
}
```

추후 map, filter, flatMap 등을 다룬다.

#### while

#### repeat-while

#### 구문 이름표
break , continue 가 어떤 범위에 적용해야하는지 애매하거나 큰 범위의 반복문에 적용하고 싶을때 사용.

```
loopname : for num in numbers {
	loopname2 : for char in strings {
		if char == 'a'{
			break loopname
		}	
	}
}
```

## CHAPTER 7 함수

스위프트의 함수는 소괄호를 생략할 수 없습니다. 함수의 오버라이드 , 오버로드는 모두 지원합니다.

```swift
func 함수 이름(매개변수...) -> 반환 타입 {
	실행 구문
	return 반환 값
}
```

전달인자 레이블 : 전달인자 레이블을 지정하면 함수 내부에서 매개 변수의 역할을 좀 더 명확히 할 수 있습니다. 매겨변수이름 전달인자 레이블 : 매개변수 타입 (순서)

default 값 : 기본값을 지정하여 매개변수가 전달되지 않으면 기본값을 가지게 합니다.

참조 타입 매개변수 : inout 매개변수 , 전달될 변수나 상수 앞에 & 붙여준다.

```swift
func referenceParameter(_ arr: inout [Int]){
	arr[1] = 1
}

var numbers : [Int] = [10,11,12]

referenceParameter( &numbers )

print(numbers[1])
```

Void : 값의 반환이 굳이 필요하지 않다면 Void 로 표시하거나 아예 표현을 생략하면 된다.

전달인자로 함수를 전달 받는 함수

```swift
func printMathResult(_ mF: CalculateTwoInts, _ a:Int, _ b:Int){
	print("Result : \(mF(a,b)")
}

printMathResult(add,3,6)
```

중첩 함수 : 스위프트는 데이터 타입의 중첩이 자유롭습니다. 열거형 안에 또하나의 열거형, 클래스 안에 또 다른 클래스, 함수 안에 또다른 함수가 가능합니다. 일반적인 위치에 선언되어진 함수는 전역함수입니다. 그러나 함수 안의 함수로 구현된 중첩함수는 상위 함수의 내부에서만 사용할 수 있습니다. 그러나 상위 함수가 중첩 함수를 반환하면 밖에서도 사용할 수 있습니다.

#### 종료되지 않는 함수 (Never)
비반환 함수, 비반환 메서드, Never 라고 표현합니다. 정상적으로 끝날 수 없는 함수입니다.
비반환 함수는 어디서든 호출이 가능하고, guard 구문 등에서 사용 됩니다.
Never 타입에서 사용되는 표준함수는 fatalError("") 입니다.

## CHAPTER 8 옵셔널

#### 옵셔널 바인딩
nil 체크의 안전적이고 세련된 방식

```swift
var name : String? = "khk"

if let n = name {
	print(n)
} else {
	print("nil")
}

name = nil

if let n = name {
	print(n)
} else {
	print("nil")
}

```
























