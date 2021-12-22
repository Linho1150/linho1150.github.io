---
title: "Swift, Basic swift (Simple Variable)"
date: 2021-12-08
author: LeeJaeJun
categories: [Programming,Swift]
tags: [Programming,Swift,SwiftUI]
math: true
mermaid: true
---

## Swift 기본
## 출력하기

```swift
print("Hello, World")
```

## 변수 선언

```swift
var myVariable = 42
myVariable=52
//변할 수 있는 값 선언 = var 타입

var myInteger:Int = 42
//변수명 뒤에 ":타입"을 적으면 타입을 지정할 수 있음

let myConstant = 42
myConstant = 52 //Error
//변하지 않는 값 선언 = let 타입
```

어디선가 만났던 var 과 let이 나오는데 javascript와 동일하다. var Type으로 선언한 변수 myvariable은 중간에 값을 52로 변경이 가능하다. 하지만 let은 C언어의 const와 동일하게 값 변경이 불가능하다. 이렇게 선언하는 이유는 포인터를 잃어버리거나 메모리 누수 방지를 위해 필요한 양 만큼만 선언하여 관리하는 이유이다.
(단, let을 객체로 선언하였을 경우, 예를들어 let myConstant=Person() 이면 myConstant=Person2()와 같이 변경은 불가능하지만 myConstant.키=180 과 같이 객체 내부의 값은 변경할 수 있다.)

### 궁금해! Int 형태로 선언하고 :Double을 적으면 어쩔까?

```swift
let myTall=180
let myWeight=70.0
let myInteger:Double = 70

print(myTall) //180
print(myWeight) //70.0
print(myInteger) //70.0
```

변수 myInteger를 보면 Integer 형태인 70을 선언했으나 출력 결과물을 보면 70.0으로 출력되는 것을 알 수 있다.

## 변수 합치기

```swift
let name:String = "Jaejun"
let number:Int = 3
let id:String=name+String(number) //원하는 타입(변수명)
print(id) //Jaejun3
```

변수는 기본적으로 같은 Type끼리 연산할 수 있다. 다른 변수 타입을 연산할때 Type(변수명)을 사용하면 타입을 변경할 수 있다. 

### 궁금해! 타입을 정의하고 문장을 합치면 어떻게 될까?

```swift
let name:String = "Jaejun"
let number:Int = 3
let id:String=name+number

print(id)
//error: Swift_basic.playground:5:20: error: cannot convert value of type 'Int' to expected argument type 'String'
```

최종적으로 String 형태가 나오길 바랬으나 연산을 먼저 하기에 결과값의 오류가 났다.

## String 문자열 중간에 변수값 출력하기

```swift
let name:String = "Jaejun"
let number:Int = 3
let Welcome:String = "Welcome to \(name+String(number)) World"
print(Welcome)
```

\(변수)을 활용하면 String 사이에 변수 값을 출력할 수 있다.

## Print multiple lines

```swift
let apple:String="Apple"
let banana:String="Banana"
let quotation:String = """
I said "I have\(apple)"
And then I said "I have \(apple+banana) pieces of fruit"
"""
```

""" 사이에 글을 쓰면 Multiple line 구현이 가능하다. 단, 첫줄에 """줄바꿈 그리고 마지막줄에 줄바꿈"""을 해줘야 중간에 multiple line이 가능하다. 예를들어, """Hello "I said""""와 같이 사용하는건 불가능하다.

## Define Array & Dictionary

```swift
//Array
var shoppingList:Array=["a","b","c"]
shoppingList[0]="z"
print(shoppingList)
//["z", "b", "c"]

//Dictionary
var playingList:Dictionary=[
    "soccer":"fun",
    "baseball":"nice",
    "coding":"hmmm,,,"
]
playingList["coding"]="very fun"
print(playingList)
//["baseball": "nice", "coding": "very fun", "soccer": "fun"]
```

Python과 비슷한 느낌으로 List 와 Dictionary 형태의 Variable을 선언할 수 있다. 둘다 브라켓( [] ) 기호를 통해 선언되며 Index 느낌으로 선언되면 Array 타입, Key 와 Value 를 섞어놓은 형식이면 Dictionary 타입으로 선언된다. 선언에 사용되는 기호가 다르다는 점만 고려하면 Python의 문법과 흡사하다.

### Array 항목 추가

```swift
var addList:Array=["안"]
addList.append("녕")
print(addList)//["안", "녕"]
```

Python의 리스트와 동일하게 append(새로운값)을 사용하면 새로운 항목을 가장 마지막에 추가할 수 있다.

## Array & Dictionary 초기화

```swift
var EmptyArray:[String] = []
var EmptyDictionary:[String:Int]=[:]
//비어있는 Array 와 dictionary 선언

var EmptyArrayNoType = ["Sample1","Sample2","Sampel3"]
var EmptyDictionaryNoType = [
    "Sample1":"me1",
    "Sample2":"me2"
]
EmptyArrayNoType = [] //Array 값 초기화
EmptyDictionaryNoType=[:] //Dictionary 값 초기화
print(EmptyArrayNoType) //[]
print(EmptyDictionaryNoType) //[:]
```

- :[타입]을 정하면 비어있는 Array 와 Dictionary를 선언할 수 있다.  Array와 Dictionary를 구분하는 차이점은 [ ] 기호 내부에 : 표시가 있는지 없는지 이다.
- [ ] 와 [ : ]를 사용하면 값을 초기화할 수 있다.

base on : Apple BookStore - The Swift Programming Language(Swift 5.5) part [ A Swift Tour - Simple Values ]
