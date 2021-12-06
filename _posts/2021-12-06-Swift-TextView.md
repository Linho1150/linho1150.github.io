---
title: "Swift, SwiftUI - What is Text()?"
date: 2021-12-06
author: LeeJaeJun
categories: [Programming,Swift]
tags: [Programming,Swift,SwiftUI]
math: true
mermaid: true
---


## SwiftUI - What is Text()?

- SwiftUI에 관하여
swift는 StoryBoard를 사용하여 UI를 제작해왔지만 최근 "SwiftUI"를 발표하면서 기존 스토리 보드형식이 갖고 있던 협업의 문제점과 갈수록 커져가는 규모로 인해 새로운 인터페이스인 SwiftUI를 도입했다고 한다.
- ContentView.swift

```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            Text("Welcome to my first Project")
                .font(.headline) //글자 크기 (자동)
                .fontWeight(.semibold) //글자 굵기
                .foregroundColor(Color.green) //글자색
                .italic() //기울이게
                .underline(true, color: Color.red) //밑줄
                .strikethrough() //취소선
                .padding()
            Button(action: /*@START_MENU_TOKEN@*/{}/*@END_MENU_TOKEN@*/) {
                /*@START_MENU_TOKEN@*/Text("Hit me!")/*@END_MENU_TOKEN@*/
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

- 위 코드 세부 사항
    - . 뒤에 오는 내용을 "modifier"라고 지칭한다. ( 폰트 세부 속성을 이용할 수 있음. )
    - .underline()의 경우 Argument 없이 전달해도 무방하나 그럴경우 color를 지정할 수 없음. 색상을 지정하고 싶으면 첫번째 argument 로는 true를 두번째는 원하는 색상으로 전달해주면 활용가능하다.
    - .font(.system(size:24, weight:.semibold,design:.serif)와 같이 작성하면 사용자가 커스텀할 수 있다. 단 size를 24로 고정해놓으면 아이폰 화면 크기와 관계없이 24 사이즈를 유지하기 때문에 작은 화면에는 글씨가 커보일 수 있다. 기본적으로 제공하는 .font()의 속성을 활용하면 자동으로 화면크기에 맞게 글씨 크기를 맞춤 제공한다. (예: .headline )
    - .multilineTextAlignment(.leading)를 활용하면 Text의 길이가 길어졌을때 원하는 정렬을 사용할 수 있다. ( .leading : 왼쪽 정렬, .trailing : 오른쪽 정렬, center : 가운데 정렬 )
    - .baselineOffset(10.0) 글씨 간격
    중요. 가끔 순서가 바뀌면 작동하지 않는 modifier가 있다. 예를들어 .baselineOffset()은 .multilineTextAllignment() 뒤에 올 경우 작동하지 않는다. ( 코드 입력시 Hint가 나오지 않음 )
    - .kerning() 글자 간의 간격을 의미한다. ( 자간이랑 다른 의미라고함)
    - .frame(width: 200, height: 100, alignment: .center) 로 프레임의 크기를 지정할 수 있다. 프레임 밖을 벗어나면 " ... " 으로 요약표시가 된다.
    .minimumScaleFactor(1.0) 를 사용하면 frame에 비례하여 글씨의 크기를 조절할 수 있다.
    - 오른쪽 상단 '+' 버튼을 클릭하면 새로운 컴포넌트를 생성할 수 있음
    ( Button을 해당 방법으로 생성한 상태 )
    - 팁! 주석처리할 글자를 드레그 한 후 command + / 를 활용하면 일괄 주석처리 할 수 있다. (기본 주석처리는 "//")
    
    ```swift
    Text("code".uppercased())
    Text("code".lowercased())
    Text("code".capitalized)
    ```
    
- 위 코드 세부사항
    - .uppercased() : 전체 대문자
    - .lowercased() : 전체 소문자
    - .capitalized() : 도시명, 이름 등 특정 알파벳만 대문자

base on : https://youtu.be/RKfkG01x79w
