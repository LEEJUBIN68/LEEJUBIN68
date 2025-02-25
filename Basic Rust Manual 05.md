# _📚 Enums of Rust_

```txt
>> 이 Enums(열거형)는 하나의 Type이 가질 수 있는 값들을 열거함으로써,
   Type을 정의할 수 있도록 하는것을 의미한다.
```

<hr>

_[Reference 01](https://rinthel.github.io/rust-lang-book-ko/ch06-01-defining-an-enum.html)_ <br>
_[Reference 02](https://www.youtube.com/watch?v=GoNxOfiW1bs&list=PLsGh7Wc318khzAJOJIJpkL0KHMr4iAk0z&index=9)_

```c++
// 1. 다음의 예제는 우리가 실생활에서 사용하는 IP주소를 예시로 들었다.
      (IPv4, IPv6)
// 2. 열거형 함수 안에 v4 상태인지, v6 상태인지 정의할 수 있도록 하였다.
// 3. Main 함수에는 v4라는 Variants(아래 함수처럼 개념을 Code에 표현하는 것)를
      'four'라는 변수에 담아주었다.
// 4. If 조건문에서는 IpAddrKind가 four라는 변수와 일치한다면, "IPv4"라는 문자열을
      출력하도록 설계하였다.

enum IpAddrKind {
    V4,
    V6,
}

fn main() {
    let four = IpAddrKind::V4;
    
    if let IpAddrKind::V4 = four {
        println!("IPv4\n");
    }
}
```

```c++
// 1. If 조건문 대신, match를 사용해서 출력할 수도 있다.
// 2. 단, match를 사용할 때, 모든 Variants들을 정의하지 않으면,
      오류가 발생한다.

enum IpAddrKind {
    V4,
    V6,
}

fn main() {
    let four = IpAddrKind::V4;
    
    match IpAddrKind::V4 = four {
        IpAddrKind::V4 => println!("IPv4\n"),
        IpAddrKind::V6 => println!("IPv6\n"),
    }
}
```

```c++
// 1. 위처럼 모든 Variants가 한두개 정도일 경우, 정의하기는 쉽지만,
      일일이 다 작성하기에는 상당한 귀찮음이 따른다.
// 2. 그럴 경우, 특수한 조건만 제외하고, 외의 것들은 모두 다르게 출력하도록
      설정하게 한다. 아래처럼 '_'를 삽입하면 실행가능하다.

enum IpAddrKind {
    V4,
    V6,
}

fn main() {
    let four = IpAddrKind::V4;
    
    match four {
        IpAddrKind::V4 => println!("IPv4\n"),
        _ => println!("Etc..\n"),
    }
}
```

```c++
// 1. 이제 각 Variant들에게 Data Type을 지정해주자.
// 2. 먼저 열거형 IpAddrKind에 V4 Variant를 String Type으로
      지정하였다.
// 3. 그리고, "IPAddrV4"라는 문자열을 출력하기 위해,
      match 안에 String Data Type으로 모두 지정해주었다.

enum IpAddrKind {
    V4(String),
    V6,
}

fn main() {
    let four = IpAddrKind::V4(String::from("IpAddrV4"));
    
    match four {
        IpAddrKind::V4(String) => println!("{}\n", String),
        _ => println!("Etc..\n"),
    }
}
```

```c++
// 1. 다시 If 조건문으로 바꿔서 Coding을 해보자.
// 2. match와 다르게, If 조건문에서는 반드시 변수를 선언해야한다.
// 3. 우리는 enum 안에 여러 Variant를 선언하였고, 이 예제에서는
      Instance를 만들 때, V4 Variant안에 String Type과 값을
      넣어주었다.
// 4. If 조건문 아래 V4 Variant에서 값을 설정할 때 굳이 String으로
      작성하지 않아도 된다. 단, String이 아니라, Value라고 설정하였다면,
      print 구문에도 Value를 출력하겠다고 다시 선언해야한다.

enum IpAddrKind {
    V4(String),
    V6,
}

fn main() {
    let four = IpAddrKind::V4(String::from("IPAddrV4"));
    
    if let IpAddrKind::V4(String) = four {
        // IpAddrKind::V4(value)
        println!("{}\n", String);
        // println!("{}\n", value);
    }
}
```

```c++
// 1. 다시 돌아와서, Data Type을 더 추가해보자.
// 2. V4 Variant에 문자열 외 Unsigned 8bit INT도 추가가 가능하게끔
      선언하였다.
// 3. 이번에는 'IpAddrV4'외 다른 숫자를 삽입해서 출력해보고 싶다.
// 4. 그렇다면 ','를 찍고, 출력하고 싶은 숫자만 입력하면 끝!
// 5. 추가적으로, 0의 변수가 선언되어 있지 않으므로, num이라는 변수를
      써서 value와 함께 출력할 수 있도록 설계해보았다.
// 6. 이제 value에서 선언된 값과 num에서 선언된 값이 출력될 것이다.

enum IpAddrKind {
    V4(String, u8),
    V6,
}

fn main() {
    let four = IpAddrKind::V4(String::from("IpAddrV4"), 0);
    
    if let IpAddrKind::V4(value, num) = four {
        println!("{}, {}\n", value, num);
    }
}
```

```c++
// 1. 이번에는 IP 주소를 출력할 수 있도록 Coding 해보자.
// 2. IP 주소 부분에 127.0.0.0을 출력하도록 만들어보았다.
// 3. IP 주소는 숫자로만 이루어져 있으므로, String에 관한
      Instance들은 모두 지워주도록 하겠다.
// 4. IP 주소는 모두 4자리이므로, 총 4개의 변수를 선언해주었다. 

enum IpAddrKind {
    V4(u8, u8, u8, u8),
    V6,
}

fn main() {
    let four = IpAddrKind::V4(127, 0, 0, 1);
    
    if let IpAddrKind::V4(num1, num2, num3, num4) = four {
        println!("{}.{}.{}.{}\n", num1, num2, num3, num4);
    }
}
```

<hr>
