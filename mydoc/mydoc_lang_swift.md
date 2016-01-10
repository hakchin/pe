---
title: Swift Language
tags:
  - "getting_started"
keywords: "swift, language"
last_updated: "December 25, 2015"
summary: "Swift Howto"
published: true
---

Doc Writer <sn2ro@me.com>

An introduction to [swift](https://developer.apple.com/swift/ "Title").

## Reference Sites
* [Swift Tutorial](http://www.tutorialspoint.com/swift/index.htm)

## Basic

### swift 뜻
제비를 닮은 심볼은 해안과 산지의 바위절벽에 서식하며 여름에 우리나라에 찾아오는 "칼새"를 의미합니다.
"신속한", "빠른" 이라는 뜻을 가진 단어이기도 합니다.

### 특징
SAFE, MODERN, POWER

### Constants and Variables
```swift
var version: Double = 1.0
let languageName: String = "Swift"
let introduced: Int = 2014
let isAwesome: Bool = true
```

가장 기초가 되는 변수와 상수는 어떻게 선언할까요?
변수는 var, 상수는 let 키워드를 사용합니다.
정수, 실수, 문자열, 배열, 사전, 클래스 등 모든 타입들에 적용되는 일관되면서 심플한 규칙을 따릅니다.
(편리성을 위해 3문자 키워드로 맞추는 섬세함까지!)

### Type Inference
```swift
var version = 1.0   // inferred as Double
let languageName = "Swift" // inferred as String
let introduced = 2014   // inferred as Int
let isAwesome = true    // inferred as Bool
```

Swift의 두드러진 특징 중의 하나로 타입추론을 꼽을 수 있습니다.
타입추론이란 할당되는 값(Value)을 통해 변수의 타입을 예측하는 것을 의미합니다.
똑똑한 컴파일러는 변수에 타입을 명시하지 않아도 할당되는 값을 보고
이 변수가 "Int 혹은 String" 타입으로 예측하고 이후부터 해당타입으로 변수를 취급합니다.

### Unicode Names
```swift
let 🚠 = 3.1415927
let 👻👻 = "dogcow"
```

Swift는 유니코드문자를 변수이름으로 사용할 수 있습니다.
이모티콘으로도 변수이름을 지을 수 있으니 재미있을 따름입니다.

### String
```swift
let someString = "I appear to be a string"
let components = "~/Documents/Swift".pathComponents
// ["~", "Documents", "Swift"]
```

"" 쌍따옴표로 감싼 문자열을 String 타입으로 인식합니다.

### Character
```swift
for character in "🐭🐭🐭🐭🐭🐭"{
  print(character)
}
```

for-each 구문을 사용해서 문자열(String)을 이루는 문자(Character)를 간편하게 순회할 수 있습니다.

### Combining String and Characters
```swift
let dog: Character = "🐶"
let cow: Character = "🐮"
let dogcow = dog + cow
// dogcow is "🐶🐮"
```

```swift
let instruction = "Beware of the " + dog
// instruction is "Beware of the 🐶"
```


스터디를 진행했던 Xcode6 Beta 버전에서는 문자+문자, 문자열+문자 의 접합연산이 가능했는데,
swift 1.0 정식 버전에서는 불가능해졌습니다.
배열과 배열, 문자열과 문자열의 접합연산만이 가능하다는 점! 주의하세요.

### String Interpolation
```swift
let a = 3, b = 5
let mathResult = "\(a) times \(b) is \(a * b)"
// "3 times 5 is 15"
```

포맷팅 문자열은 어떻게 만들까요?
문자열 내부에 \(변수) 구문을 사용해서 원하는 값으로 치환이 가능합니다.

### String Mutability
```swift
var variableString = "Horse"
variableString += " and carriage"
// variableString is no "Horse and carriage"
```

```swift
let constantString = "Highlander"
constantString += " and another Highlander"
// error - constantString cannot be changed
```

앞서 언급했던 Swift의 간결함 중 한 가지! 기억하나요?
var 키워드를 사용하면 수정 가능한 문자열.
let 키워드를 사용하면 수정 불가능한 문자열을 정의할 수 있습니다.

### Array and Dictionary
```swift
var names = ["Anna", "Alex", "Brian","Jack"]
var numberOfLegs = ["ant":6, "snake":0, "cheetah":4]
```

Array와 Dictionary에 대해서 알아볼까요?
Objective-C의 NSArray, NSDictionary와 대응하는 클래스로, 대괄호[]를 사용하여 선언합니다.
array는 값의 순서리스트를, Dictionary는 Key:Value 쌍으로 초기화 할 수 있습니다.

### Typed Collections
```swift
var names = ["Anna", "Alex", "Brian", "Jack"]
//an array of String values
```

```swift
var names:[String] = ["Anna", "Alex", "Brian", "Jack"]
var numberOfLegs = ["ant":6, "snake":0, "cheetah":4]
//a Dictionary with String keys and Int values
```

Objective-C에서는 NSObject를 상속하는 어떤 클래스도 포함할 수 있었습니다.
반면 swift에서는 Array는 동일한 타입의 값들만 포함될 수 있고,
Dictionary는 문자열 키에 동일한 타입의 값들만 포함해야 한다는 제약이 추가되었습니다.

### Loops
```swift
while !sated {
  eatCake()
}
for var doctor = 1; doctor <=13; ++doctor {
  exterminate(doctor)
}
```

일반적인 while과 for 루프문을 사용할 수 있습니다.
루프 조건문에서는 ()를 사용할 수 있지만 일반적으로 사용하지 않는 게 관례입니다.

### for - in : Ranges
```swift
var number: Int? = 2
for number in 1...5 {
    print("\(number) times 4 is \(number * 4)")
}
for number in 0..<5 {
    print("\(number) times 4 is \(number * 4)")
}
```

Objective-C에서는 볼 수 없었던 Range 루프문입니다.
1...5는 1부터 5를 포함하여 5번의 루프를,
0..<5는 0부터 5를 포함하지 않고 5번의 루프를 반복합니다.
(마치 for 조건문에 i<5와 i<=5를 사용하는 것처럼)


### for - in Arrays
```swift
for name in ["Anna", "Alex", "Brian", "Jack"]{
    print("Hello, \(name)!")
}
let numberOfLegs = ["ant":6, "snake":0, "cheetah":4]
for (animalName, legCount) in numberOfLegs{
    print("\(animalName)s have \(legCount) legs")
}
```

for-each 구문으로 Arrany를 순회할 수 있습니다.
Dictionary도 아직 배우지 않았지만 튜플을 사용하여 (Key, Value)쌍으로 순회할 수 있습니다.

### Optionals
```swift
let numberOfLegs = ["ant":6, "snake":0, "cheetah":4]
let possibleLegCount: Int? = numberOfLegs["aardvark"]
if possibleLegCount == nil {
    print("Aardvark wasn't found")
} else {
    let legCount = possibleLegCount!
    print("An aardvark has \(legCount) legs")
}
```

Swift의 변수는 디폴트로 nil 이 될 수 없습니다.
즉 선언과 동시에 반드시 초기화가 이루어져야 하지요.
null과 같이 아직 값을 갖지 않는 변수가 필요할 때는 어떻할까요?
그래서 필요한 것이 Optional 타입입니다. 변수의 타입 뒤에 ?를 붙여 옵셔널 타입으로
선언하면, 변수는 nil (null)값을 가질 수 있습니다.
"optional 타입"의 자세한 내용은 다음 강의에서 설명하겠습니다.

### Unwrapping an Optional
```swift
if let legCount = possibleLegCount {
    print("An aardvark has \(legCount) legs")
}
```

Optional로 선언된 변수는 그냥 사용할 수 없습니다.
컴파일 에러에서 벗어나기 위해 optional 타입을 벗겨야(unwrapping) 하는데요
위와 같은 구문을 사용해서 optional 타입을 unwrapping 할 수 있습니다.
"possibleLegCount가 nil 아니면 그 값을 상수 letCount에 할당하고 if 문으로.."
처럼 해석할 수 있습니다. 역시 자세한 설명은 다음 강의에서.

### switch-case
```swift
switch legCount {
case 0:
    print("It slithers and slides around")
case 1,3,5.7,9,11,13:
    print("It limps")
default:
    print("It walks")
}
```

switch 구문입니다. Objective-C와 다른 점을 눈치 채셨나요?
그렇습니다. case 조건안에 ,를 구분으로 여러 값을 명시할 수 있습니다.
또 switch 문에 정수형 외에 다른 타입들도 사용이 가능합니다.

## 지난 주 요약
.Ordered
. 변수 선언은 var 키워드를, 상수 선언은 let 키워드를 사용합니다.
. Swift 컴파일러는 변수에 할당되는 값을 통해 타입을 추론합니다.
. 유니코드에서 지원하는 다양한 문자를 변수 이름에 사용할 수 있습니다.
. 문자열 타입 String, 문자 타입 Character를 지원합니다.
. Array, Dictionary 컬렉션의 요소들은 동일한 타입으로 선언합니다.
. foreach 구문을 사용할 수 있고, for-range 루프 문을 지원합니다.
. nil이 될 수 있는 변수는 ? 연산자를 붙여 optional 타입으로 선언합니다.
. optional 변수는 사용하기 전에 ! 연사자를 사용하여 unwrapping 해야 합니다.

### Optional Overview
```swift
var message:String = "Objective-C will never die!"
message = nil // compile-time error
var message:String? = "Objective-C will never die!"
message = nil
```

optional 에 대하여 다시 한 번 정리하고 갈까요?
optional 타입은 런타임에 발생할 수 있는 nil 에러를
컴파일 타임에 발견할 수 있도록 해 줍니다.
보다 안전한 프로그램을 개발할 수 있도록 Swift 언어에서 제공하는 키워드 이지요.

### Unwrapping Optionals
```swift
var stockCode:String? = findStockCode("Facebook")
let text = "Stock Code -"
if stockCode {
  let message = text + stockCode!
}
```

optinal 타입을 사용하기 전에는 반드시 옵션널 타입을 상쇄해야 하는데, unwrapping 한다고 표현합니다.
unwrapping 하는 방법은 if 문을 사용하여 nil 인 경우에, ! 연산자를 사용하여 optinal을 상쇄합니다.
if 문을 사용하는 이유는, nil 인 경웨 ! 연산자를 사용하면 런타임 에러가 발생하기 때문입니다.
nil이 아닌라는 것을 보장하는 경우에 unwrapping 해서 사용하라는 의미이지요.

이 구문은 swift에서 관용구처럼 사용되는데, optional binding 이라 하는 좀 더 세련된 방법을 제공합니다.

### Optional Binding
```swift
var stockCode:String? = findStockCode("Facebook")
let text = "Stock code - "
if let tempStockCode = stockCode {
  let message = text + tempStockCode
  print(message)
}
```

정확히 이전 구문예제와 동일한 역할을 하는 optional binding 구문입니다.
! 연산자 대신에 let 상수 키워드를 사용하여 unwrapping 하는 것이 유일한 차이입니다.
자주 사용하게 될 구문이니 꼭 기억하세요.

```swift
let text = "Stock Code - "
if var stockCode = findStockCode("Apple") {
  let message = text + stockCode
  print(message)
}
```

함수 자체를 if 평가문에 사용하여 unwrapping 할 수도 있습니다.

### Function
```swift
func buildGreeting(name: String = "World") -> String {
  return "Hello " + name
}
let greeting = buildGreeting()
```

Swift에서는 func 키워드를 사용하여 함수를 정의합니다.
함수의 파라미터에 디폴트 값을 지정할 수 있습니다.
buildGreeting()과 같이 인자없이 호출할 경우 name 파라미터에 "World" 문자열이 할당되어 사용됩니다.

### Tuples
```swift
(379, 3.99, 4.19) // (Double, Double, Double)
(404, "Not found")  // (Int, String)
(2, "banana", 0.72)   // (Int, String, Double)
```

튜플 타입을 지원합니다. 튜플은 쉽게 말하면 값의 묶음이라 할 수 있습니다.
튜플은 선언과 동시에 상수가 되며, 값을 변경하려고 할 경우 컴파일 에러가 발생합니다.
튜플을 사용하면 한 번에 여러 값을 전달하고, 반환할 수 있어서 편리합니다.

### Decomposing a Tuple
```swift
func refreshWebPage() -> (Int, String){
  return (200, "Success")
}
let (statusCode, message) = refreshWebPage()
print("Received \(statusCode): \(message)")
```

반환된 튜플을 어떻게 사용해야 할까요? 튜플 변수에 값을 할당하여 사용할 수 있습니다.
