---
title: DateFormatter를 이용하여 날짜 변경하기

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## 현재 시간을 특정 형태로 변형하기 

~~~  
func DateType2String() -> String{
    let current = Date()
    
    let formatter = DateFormatter()
    //한국 시간으로 표시
    formatter.locale = Locale(identifier: "ko_kr")
    formatter.timeZone = TimeZone(abbreviation: "KST")
    //형태 변환
    formatter.dateFormat = "yyyy-MM-dd HH:mm:ss"
    
    return formatter.string(from: current)
}
~~~  
결과
~~~
"2022-03-21 10:27:26"
~~~  

## String을 Date 타입으로 변경하는 방법

~~~
func String2DateType(string : String) -> Date?{
    let formatter = DateFormatter()
    
    formatter.dateFormat = "yyyy-MM-dd"
    
    return formatter.date(from: string)
}

String2DateType(string: "2020-01-02")
~~~
결과  
~~~
"Jan 2, 2020 at 12:00 AM"
~~~

## 시간을 추가하는 방법

~~~
func oneHourPlus() -> String{
    
    let now = Date()
    let oneHourLater = now.addingTimeInterval(+3600)
    //TimeInterval은 초를 의미한다.
    //60 - 1분
    //3600 - 1시간
    //86400 - 24시간 하루
    let formatter = DateFormatter()
    
    formatter.dateFormat = "yyyy-MM-dd HH:mm:ss"
    
    print("현재시간 : \(formatter.string(from: now))")
    
    return formatter.string(from: oneHourLater)
}

print(oneHourPlus())
~~~

결과 
~~~
현재시간 : 2022-03-21 22:29:26
2022-03-21 23:29:26
~~~

## DateFormatter에 오전 오후를 붙이는 방법

~~~
func makeAMPM() -> String{
    
    let now = Date()
    
    let formatter = DateFormatter()
    //한국 시간으로 표시
    formatter.locale = Locale(identifier: "ko_kr")
    formatter.timeZone = TimeZone(abbreviation: "KST")
    //형태 변환
    formatter.dateFormat = "a hh:mm:ss"
    formatter.amSymbol = "오전"
    formatter.pmSymbol = "오후"
    
    return formatter.string(from: now)
    
}
~~~
결과
~~~
"오후 10:29:26"
~~~
