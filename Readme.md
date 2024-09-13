** 나와 다른 사람이 작업 중 다른사람이 먼저 add commit하고 내가 늦게 add commit하게 되면 충돌 에러가 발생함! **
=> 충돌에러 발생한 사람은 git push add origin 명령어 실행하여 먼저 commit한 사람의 소스코드로 바꾸고 나서, 작업해야 됨
=> 같은 파일을 동시에 개발하면 계속 충돌 현상이 발생되므로, 각자 다른 파일 개발 담당 권장

https://github.com/silversmell/gittest1.git
① 폴더 생성 후 초기화
git init

② 사용자 등록
origin이란 이름으로 원격 저장소 https://github.com/tnwls0903/Note.git 를 등록

git config user.name "tnwls"
git config user.email "kim20267878@gmail.com"
git remote add origin https://github.com/tnwls0903/Note.git
cat .git/config

③ 소스 변경시 반복 실행 (3줄 세트)
git add .
git commit -m "김수진 수정함"
git push origin main


④ 최신 소스 로딩하기, push reject발생하면 실행
- origin이란 이름의 원격 저장소에 있는 main branch를 Local로 가져와 병합
git pull origin main -> STS(편집기)로 이동하여 편집 계속


- 저장소 삭제: git remote remove origin || STS에서 폴더 전체 삭제 -> clone 명령어 실행 -> import 폴더 -> 2번 사용자 등록
- clone: 
git clone https://github.com/daumnulunggi/test2.git test2-clone
git clone ttps://github.com/tnwls0903/Note.git Note



** 코틀린 **
(09.13) 노트
----------------------------------------
상수는 재대입 불가.

=> 숫자 - 정수형
1 bite = 8 bit 
1 short = 16 bit
1 int = 32 bit
1 long = 64 bit

=> 숫자 - 실수형
flot =  32 bit
double = 64 bit -> 실수형은 기본적으로 double형 씀

=> 정수형 리턴 종류
- 10 진수
- 16 진수
- 2 진수
! 8 진수는 취급 안함.

=> Boolean
파이썬에서는 True, False 대문자이지만, 코틀린에서는 true, false 소문자

** 코틀린은 기본형(int, long, float, double 등)이 아닌 참조형(Int, Long, Float, Double 등)만 사용함.

자료형 지정하지 않고 null 선언하면 ? 없어도 오료 안남.
자료형 선언한 변수 println 사용할 땐 앞에 $ 선언해야 함.

** 코틀린 암묵적 형변환 지원안함.

** 자료형이 정해지지 않은 Any형 변수(Int, String)인 경우, 할당 형변환 가능.

** 불변 변수 선언할 땐 val, 가변 변수 사용할 땐 var
----------------------------------------

(09.13) 코드
----------------------------------------
fun main() {
    // 잘못된 예
    // -----------------------------------
//     val username="Kildong"
//     username="Hello"
//     val init:Int = 1234
//     init=0
    
//     println(username)
//     println(init)
    // -----------------------------------
    
    
    // 올바른 예
    // -----------------------------------
//     var username="Kildong"
//     username="Hello"
//     var init:Int = 1234
//     init=0
    
//     println(username)
//     println(init)
    // -----------------------------------
    
    
    // -----------------------------------
//     var s:Int=1000 // s = string
//     println("s=:$s")
//     println("$s")
//     println(s)
//     println("hello, world!!")
    // -----------------------------------
    
    
    // -----------------------------------
//     var name="Hello"
//     println(name.toUpperCase())
//     println(name.toLowerCase())
//     println(name[1])
//     println("Hi my name is $name 입니다")
// //     println("Hi my name is $name입니다") // error, $ 변수 다음에 공백 필요
//     println("Hi my name is ${name}입니다") // $ 변수 붙여서 쓰고 싶을 때 {} 추가하면 됨
//     println("Hi my name is ${name + 543} 입니다")
//     println("Hi my name is " + name + "입니다")
    // -----------------------------------
    
    // -----------------------------------
//     var a:Int=null // error, 정수형은 null값 불가
//     var a:Int ?= null // ? 추가하면 null값 허용되는 정수형 가능
//     println(a)
    
// 	var a:Int=null
//     var a=null
//     println(a)
    // -----------------------------------
    
    
    // -----------------------------------
//     val ch='A'
//     val ch2:String="K"
    
//     val ch="A"
//     val ch2:String="K"
    
//     val ch='A'
//     val ch2:Char='K'
    
//     println("ch: $ch")
//     println("ch2: $ch2")
    // -----------------------------------
    
    // p37.
    // -----------------------------------
//     val name = "HonhKilDong"
//     var age = 20
//     var tel = "010-7890-4569"
    
//     println("이름 =: $name")
//     println("나이 =: $age")
//     println("전화번호 =: $tel")
    // -----------------------------------
    
    
    // p39.
    // -----------------------------------
//     val name = null
// //     var name02:String = null // error, 자료형 선언한 경우에는 null 값 반영하려면 ? 추가해야 함
// //     var name02:String = "null"
//     var name02:String ?= null

//     println(name)
//     println(name02)
    // -----------------------------------
    
    
    // p41.
    // -----------------------------------
//     var a=123 // 기본 정수형인 int형으로 자동 할당
//     var b=200L // long형
// //     b=a // error, 할당으로 형 변환 불가
//     b=a.toLong()
    
//     println(a)
//     println(b)
    // -----------------------------------
    
    // p42.
    // -----------------------------------
//     var a=123
//     var b=200L
//     var name=""
    
//     name=a.toString() 
    
//     println(name)
//     if(name is Int) {
//         print("True")
//     } else {
//         print("False")
//     }
//     // -> name이 String형으로 형변환되어 False 값 나옴
    
//     println()
    
//     if(name is String) {
//         print("True")
//     } else {
//         print("False")
//     }
    // -> name이 String형으로 형변환되어 True 값 나옴
    // -----------------------------------
    
    // p43. 참조 주소가 달라지는 경우의 예시 문제 삭제!
    // -----------------------------------
//     val a:Int=123 // 123
//     val b:Int=123 // 123
    
//     println(a==b) // true
//     println(a===b) // true
    // -----------------------------------
    
    // p48. Any형(Int, String) 변수 형변환
    // -----------------------------------
//  	var a:Any=1 // Any에서 1은 Int형으로 자동 할당됨
//     a=20L // Int -> Long
    
//     println("a: $a type: ${a.javaClass}") // a의 자바 기본형은 long
    
//     var b:Any=1 // Any에서 1은 Int형으로 자동 할당됨
//     b="1" // Int -> String
    
//     println("b: $b type: ${b.javaClass}") // a의 자바 기본형은 long
    // -----------------------------------
    
    
    // p50.
    // -----------------------------------
//     checkArg("Hello")
//     checkArg(5)
    // -----------------------------------
}

// fun checkArg(x: Any) {
//     if(x is String) {
//         println("x is String: $x") // Hello
//     }
    
//     if(x is Int) {
//         println("x is Int: $x") // 5
//     }
// }
----------------------------------------
