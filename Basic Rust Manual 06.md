# _🔥 Practice of Rust_

```txt
>> 우리가 Coding을 하면서, Module화하는 것은 필수이다. 이 Rust에서도
   똑같이 등장하는데, 먼저 'Crate'라는 개념에 대해 알아보려고 한다.
>> 이 Crate라는 것은 흔히 술병을 담는 Tray나 애완동물을 옮길때 쓰는
   Cage같은 것을 뜻한다.
>> 우리는 이 Crate Library에 Project를 생성하여 볼 것이다.
```

<hr>

_[Reference 01](https://rinthel.github.io/rust-lang-book-ko/ch07-01-mod-and-the-filesystem.html)_ <br>
_[Reference 02](https://www.youtube.com/watch?v=-RYinP9sImI&list=PLsGh7Wc318khzAJOJIJpkL0KHMr4iAk0z&index=10)_

<br>

```txt
>> cargo new communicator --lib
>> cd communicator
```

```txt
>> 위와 같이 명령어를 내리게 되면, 기본 Source Code가 있는 Library가
   생성된다.
>> 우리가 직접 'lib.rs'라는 파일을 작명해서 생성할 수 있지만, 빈 Lib 파일만
   생성될 것이다. 앞으로 Project를 만들 때 이를 잘 사용해보도록 하자.
>> 명령어가 오류없이 잘 되었다면, lib.rs라는 파일이 생성되고, 기본 Source
   Code가 생성되어져 있을 것이다.
```

![Image](https://github.com/user-attachments/assets/46670a1f-47bb-42e4-ac69-2ea7b77c143d) 
![Image](https://github.com/user-attachments/assets/2ccf5efa-4b5e-4f44-9ede-a208fa263c00)

```c++
// 1. 아래의 예제처럼 우리의 목적은 Module화이다.
// 2. 이 Module은 하나만 생성하는 것이 아니라, 계층적으로 생성할 수 있다.
// 3. 여기서 Crate는 결국 하나의 절대경로로 이용되게 된다. 한 상자에 Module을
      담아서 출력하게끔 만드는 개념이라고 보면 된다.
// 4. 하지만, 이대로 Cargo Build를 실행하게되면, 오류가 발생할 것이다. 이 Module은
      Private Module이라서 접근이 안된다는 오류 메시지이다. 

mod 구매대행주문 {
    mod 웹호스팅 {
        fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

fn vip고객주문() {
    crate::구매대행주문::웹호스팅::견적문의접수();
}
```

```c++
// 1. 위와 같이, Private Module을 해제하기 위해, Public으로
      바꿔주면 오류가 해결될 것이다.
// 2. Warning은 많이 뜨겠지만, 무시해도 상관없다. (단지 예제일 뿐)

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

fn vip고객주문() {
    crate::구매대행주문::웹호스팅::견적문의접수();
}
```

```c++
// 1. 이번에는 super라는 KeyWord로 부모 Module 경로를
      가리켜보자.
// 2. 이 KeyWord를 사용하면, 경로가 길고 복잡할 때 간략하게
      작성하여 보기 쉽게 만들 수 있다.

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

fn vip고객주문() {
    crate::구매대행주문::웹호스팅::견적문의접수();
}

// super: 현재 Module의 부모 Module

mod 구매작업 {
    fn 고객만족작업() {
        기대수익();
        super::vip고객주문();
    }
    
    fn 기대수익() {}
}
```

```c++
// 1. 이제 본격적으로 Block Chain Tech의 Project 예시로
      연습을 해보자.
// 2. 아래 예제의 경우, enum Instance 부분에서 Private이
      기본 값으로 설정되어있기 때문에, 오류가 발생한다.

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

fn vip고객주문() {
    crate::구매대행주문::웹호스팅::견적문의접수();
}

// super - 현재 Module의 부모 Module

mod 구매작업 {
    enum 추가수입 {
        coupon,
        rebate,
    }
}

fn 기대수익() {
    let order1 = 구매작업::추가수입::coupon;
    let order2 = 구매작업::추가수입::rebate;
}
```

```c++
// 1. 아래처럼 Public으로 바꾸면, 정상적으로 실행될 것이다.

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

fn vip고객주문() {
    crate::구매대행주문::웹호스팅::견적문의접수();
}

// super - 현재 Module의 부모 Module

mod 구매작업 {
    pub enum 추가수입 {
        coupon,
        rebate,
    }
}

fn 기대수익() {
    let order1 = 구매작업::추가수입::coupon;
    let order2 = 구매작업::추가수입::rebate;
}
```

```c++
// 1. super 외에도 다양한 KeyWord가 있는데,
      우선 Use라는 KeyWord를 살펴보겠다.
// 2. vip고객주문이라는 함수에서 경로가 너무 길다.
// 3. 이를 Use를 사용하여 줄여보자.
// 4. 앞의 Crate를 떼어내고, Use KeyWord를 사용해서
      포괄하여 입력가능하다.

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

use crate::구매대행주문::웹호스팅;

fn vip고객주문() {
    웹호스팅::견적문의접수();
}

// super - 현재 Module의 부모 Module
// use - 긴 Module 경로를 줄임
// self - 현재 Module

mod 구매작업 {
    pub enum 추가수입 {
        coupon,
        rebate,
    }
}

fn 기대수익() {
    let order1 = 구매작업::추가수입::coupon;
    let order2 = 구매작업::추가수입::rebate;
}
```

```c++
// 1. 이번에는 Self라는 KeyWord를 사용해서 
      현재 Module을 출력해보도록 하자.
// 2. 결과값은 위와 동일하다.

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

use self crate::구매대행주문::웹호스팅;

fn vip고객주문() {
    웹호스팅::견적문의접수();
}

// super - 현재 Module의 부모 Module
// use - 긴 Module 경로를 줄임
// self - 현재 Module

mod 구매작업 {
    pub enum 추가수입 {
        coupon,
        rebate,
    }
}

fn 기대수익() {
    let order1 = 구매작업::추가수입::coupon;
    let order2 = 구매작업::추가수입::rebate;
}
```

```c++
// 1. 아래줄 경로도 너무 길다. 이 Instance 경로도 줄여보자.
// 2. Warning이 많다 할지라도, 정상적으로 Build되는 것을 확인할 수 있다.

mod 구매대행주문 {
    pub mod 웹호스팅 {
        pub fn 견적문의접수() {}
        fn 접수확인메일_발송() {}
    }
    
    mod 구매대행견적 {
        fn 견적메일발송() {}
        fn 결제받기() {}
        fn 구매대행주문() {}
    }
}

use self crate::구매대행주문::웹호스팅;

fn vip고객주문() {
    웹호스팅::견적문의접수();
}

// super - 현재 Module의 부모 Module
// use - 긴 Module 경로를 줄임
// self - 현재 Module

mod 구매작업 {
    pub enum 추가수입 {
        coupon,
        rebate,
    }
}

use crate::구매작업::추가수입;

fn 기대수익() {
    let order1 = 구매작업::추가수입::coupon;
    let order2 = 구매작업::추가수입::rebate;
}
```

```c++
// 1. 

```
