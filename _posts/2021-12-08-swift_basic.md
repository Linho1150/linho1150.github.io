---
title: "Swift, Basic swift (Print, Variable)"
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

## 간단한 변수 선언

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

### String 문자열 중간에 변수값 출력하기

```swift
let name:String = "Jaejun"
let number:Int = 3
let Welcome:String = "Welcome to \(name+String(number)) World"
print(Welcome)
```

\(변수)을 활용하면 String 사이에 변수 값을 출력할 수 있다.

base on : Apple BookStore - The Swift Programming Language(Swift 5.5) page4
