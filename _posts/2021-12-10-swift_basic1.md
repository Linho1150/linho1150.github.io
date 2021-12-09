---
title: "Swift, Basic swift (If, For, Optional Type)"
date: 2021-12-08
author: LeeJaeJun
categories: [Programming,Swift]
tags: [Programming,Swift,SwiftUI]
math: true
mermaid: true
---

## Swift 기본
## if 문 & for 문

```swift
let individualScores:Array = [42,52,23,56,75] //값이 변하지 않아서 let선언
var teamScore:Int=0 //값이 변해서 var 선언
for score in individualScores{
    if score > 50{
        teamScore+=10
    }
    else{
        teamScore-=10
    }
}
print(teamScore) //10
```

나는 변수를 선언하는데 최대한 타입을 적기로 하였다. Javascript를 하면서 느낀점이 Type이 지정되어있지 않으면 코딩을 하는 과정에서 많은 문제점이 발생하더라 ..

IF문은 조금 난해했다. Array를 선언하는 과정은 파이썬과 비슷했는데 if문은 파이썬과 C언어 자바와 같이 보편적인 언어를 짬뽕시켜놓은 기분이다. . . For문 또한 비슷하다 ( For - in 구문은 파이썬인데 브라켓 { } 은 C언어 같기도 하면서 .. )

결과적으로 선언하는 방법은 다음과 같다.

### if문

```swift
if 조건1 {
    //조건1 = true
}
else if 조건2 {
    //조건2 = true
}
else{
    //조건1 & 조건2 = false
}
```

### for문

```swift
for 변수1 in 변수2 {
    //실행코드
}
```

변수2에는 Array 와 Dictionary 같은 변수가 변수 1에는 변수2에 있는 값을 순차적으로 출력한다. 따라서 For문과 If 문을 함께 사용하면 첫번째 샘플과 같은 코드를 완성 시킬 수 있다.

## Optional Type에 대한 고찰

### Optional Type은?

이해를 위해 간략하게 설명하자면 nil을 쓸 수 있는가 없는가?에서 비롯되는데 이전에 swift의 특성에 대해서 알고 있으면 보다 도움이 된다. Swift는 "안정성"을 중요시 하는 언어이다. 그에 걸맞게 Variable을 Define하는데 있어서 정확한 Type을 지정해야한다. 여러가지 예시를 갖고 실행되는 코드와 안되는 코드를 비교해보기로 하였다.

### 메인코드

```swift
var OptionalType:String?
if OptionalType==nil{
    OptionalType="aaa"
    print("맞음 \(OptionalType!)")
}
else{
    OptionalType="bbb"
    print("틀림 \(OptionalType!)")
}
```

여기서 중요한건 ?와 ! 이다. Optional Type만 사용할 수 있는 연산자이다. ?를 사용하고 값을 아무것도 지정하지 않았을 경우 ?를 마지막에 입력하면 nil로 값을 담고 있게 된다. (단, ?를 넣지 않으면 안정성 이유로 오류가 난다)

!는 Optional Type으로 선언했을 경우 변수명 뒤에 !를 붙여줘야한다 예를들어 OptionalType!과 같이 말이다. !를 적는 이유는 이 변수를 사용하기 이전에 Optional Type인 변수에 값을 넣었다는 말이다. 위 코드로 예를들자면 OptionalType 변수를 출력하기 이전에 "aaa" 값을 지정하였고 이후 print() 내부에 OptionalType!과 같이 적어야 값이 넣어졌다고 확인되는 것이다.

### 실험 샘플 1

```swift
var OptionalType1:String
OptionalType1="Hello"
print(OptionalType1) //Hello
```

위 코드는 실행가능한 코드이다. 변수를 선언하고 Print 하기 이전에 OptionalType1에 대한 값을 정확하게 입력하였음으로 실행하는데 있어서 문제가 없다.

### 실험 샘플 2

```swift
//1번 코드
var OptionalType1:String
print(OptionalType1)
//error: Swift_basic.playground:80:7: error: variable 'OptionalType1' used before being initialized

//2번 코드
var OptionalType1:String=""
print(OptionalType1)
//print Blank
```

위 1번 코드는 실행 불가능한 코드이다. 에러코드를 살펴보면 초기화 하기 이전에 OptionalType1을 실행할 수 없다는 내용이다.

위 2번 코드는 실행가능하다. 값을 공백으로 지정해줬기 떄문이다.

### 실험 샘플3

```swift
var OptionalType1:String=nil
print(OptionalType1)

/* error: Swift_basic.playground:79:26: error: 'nil' cannot initialize specified type 'String'
var OptionalType1:String=nil
                         ^
Swift_basic.playground:79:19: note: add '?' to form the optional type 'String?'
var OptionalType1:String=nil */
```

nil을 값으로 지정 할 수 있는건 Optional Type 밖에 없다고 나와있다.

base on : Apple BookStore - The Swift Programming Language(Swift 5.5) part [ Control Flow ]
