# _♻️ BlockChain of Rust_

```txt
>> BitCoin을 한 번이라도 접해본 사람이라면, 이 BlockChain 기술에 대해서 알고있을 것이다.
   이 BlockChain 기술이라는 것은 Business Network에서도 정보를 투명하게 공유할 수 있도록
   하는 고급 DB Mechanism이라고 할 수 있겠다.
>> 특히, 이 BitCoin을 예시로, 온라인 지불, 계정 및 시장 거래를 관리하는 데 도움이 많이 된다.
```

<hr>

_[Reference 1](https://aws.amazon.com/ko/what-is/blockchain/?aws-products-all.sort-by=item.additionalFields.productNameLowercase&aws-products-all.sort-order=asc)_

# _🏢 Structure of Rust_

```c++
// 1. 이번 시간에는 Structure(구조체)에 대해 알아보자.
// 2. 이 구조체는 DB를 관리하고, 입력하는데 큰 도움이 될 것이다.
// 3. 'struct' Instance 안에 이름, 전자주소, 길이, 활성화 여부를 넣고,
      Main함수로 불러와 호출하는 식으로 Coding 되어있다.
// 4. 이미 문자열로 Email과 Username을 입력해놓았으므로, 이 문자열들이
      출력될 것이다.

struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}

fn main() {
    let user1 = User {
        email: String::from("someone@sample.com"),
        username: String::from("someoneName123"),
        active: true,
        sign_in_count: 1,
    };
    
    println!("Email: {}, UserName: {}\n", user1.email, user1.username);
}
```

```c++
// 1. 만약 중간에 DB값을 변경하고 싶다면, Mutable 선언과 Scope 밖에서 다른 값으로
      변경 후, 출력해주면 된다.

fn main() {
    let mut user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someuserName123"),
        active: true,
        sign_in_count: 1,
    };
    
    user1.username = String::from("anyusername");
    println!("Email: {}, Username: {}\n", user1.email, user1.username);
}
```

```c++
// 1. 이렇게 구조체를 세우는 방법은 정말 쉽다. 'struct'라는 Keyword로 안에
      Field들을 지정하고, Instance값을 지정할 때는 이 값이 구조체의 이름이다
      라고 지정만 해주면 끝이다.
// 2. 하지만, 구조체도 틀에 갇혀있는 것이 아니라, 계속해서 변경해야될 때가
      있는데, 이제부터 갱신하는 방법에 대해 알아보도록 하겠다.
// 3. 아래 예제의 경우, user1과 user2의 Instance를 나눠놓았다. 특히, user2에
      '..user1'이라고 적어놓음으로써 user1의 Instance를 그대로 빌려서 쓸 수 있다.
// 4. '.' 연산자를 이용하여 Email과 Username 정보를 출력하도록 지정해놓았고,
      최종적으로 보면, user2의 정보는 email 정보만 들어올 것이다.

struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}

fn main() {
    let mut user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someUsername123"),
        active: true,
        sign_in_count: 1,
    };
    
    let mut user2 = User {
        email: String::from("someone2@example.com"),
        ..user1
    };
    
    user1.username = String::from("anyUsername");
    println!("Email: {}, Username: {}\n", user2.email, user2.username);
}
```

```c++
// 1. 이번에는 user2 Instance의 값을 바꿔서 Coding 해보자.
// 2. 이 user2의 Field 명을 바꿔줄 때, 

struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}

fn main() {
    let mut user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someusername123"),
        active: true,
        sign_in_count: 1,
    };
    
    let mut user2 = User {
        email: String::from("someone2@example.com"),
        ..user1
    };
    
    user2.username = String::from("anyusername2");
    println!("Email: {}, Username: {}\n", user2.email, user2.username);
}
```

```c++
// 1. 이번에는 Tuple을 이용해서, 구조체를 만들어보자.
// 2. 'let black' Instance에서 구조체 이름인 'Color'에서
      검정색의 RGB값인 (0, 0, 0)을 넣었다.
// 3. Index값은 0번부터 시작하므로, 마지막에 출력되는 값에
      각각 번호를 주었다.
// 4. 모두 0이 출력되겠지만, RGB 위치에 따라서 값이 출력될 것이다.  

struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}

struct Color(i32, i32, i32);

fn main() {
    let mut user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someUsername123"),
        active: true,
        sign_in_count: 1,
    };
    
    let mut user2 = User {
        email: String::from("someone2@example.com"),
        ..user1
    };
    
    user2.username = String::from("anyusername2");
    println!("Email: {}, Username: {}\n", user2.email, user2.username);
    
    let black = Color(0, 0, 0);
    
    println!("R value of BlackColor: {}, Value G: {}, Value B: {}\n", black.0, black.1, black.2);
}
```

```c++
// 1. 특정 값을 다르게 출력하고 싶을 때는 아래와 같이, mut를 선언 후,
      해당 값의 Instance를 수정해주면 된다.
// 2. 우리가 수정한 부분은 RGB중에서 R이므로, 이 값은 100으로 출력될 것이다.

struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}

struct Color(i32, i32, i32);

fn main() {
    let mut user1 = User {
        email: String::from("someone2@example.com"),
        username: String::from("someUsername123"),
        active: true,
        sign_in_count: 1,
    };
    
    let mut user2 = User {
        email: String::from("someone2@example.com"),
        ..user1
    };
    
    user2.username = String::from("anyusername2");
    
    println!("Email: {}, Username: {}\n", user2.email, user2.username);
    
    let mut black = Color(0, 0, 0);
    
    black.0 = 100;
    
    println!("The value R of BlackColor: {}, Value of G: {}, Value of B: {}\n", black.0, black.1, black.2);
}
```

```c++
// 1. 아래의 예제는 사각형의 넓이를 구하는 공식을 쓴 것이다.
// 2. 넓이는 음수가 나오지 않을 것이므로, unsigned Integer Data Type을 기입하였고,
      'area'라는 함수에서 length 변수와 width 변수를 곱하게 만들어주었다.
// 3. main 함수에서 변수는 각각 50과 30이고, area 함수에 각 값을 대입시키도록 Coding 하였다.
// 4. 당연히 그 값은 1500이 나올것이다.

fn main() {
    let length1 = 50;
    let width1 = 30;
    
    println!("The Area of the Rectangle is {} Square PX\n", area(length1, width1));
}

fn area(length: u32, width: u32) -> u32 {
    length * width
}
```

```c++
// 1. 이번에는 위를 인용하여, Tuple로 값을 출력해보겠다.
// 2. 추가적으로, 구조체를 만들어 보기 쉽게 Coding 하였다.
// 3. 결과값은 동일하다.

struct Rectangle {
    length: u32,
    width: u32,
}

fn main() {
    let rect1 = Rectangle {length: 50, width: 30};
    
    println!("The Area of the Rectangle is {} Square PX\n", area(&rect1));
}

fn area(rectangle: &Rectangle) -> u32 {
    rectangle.length * rectangle.width
}
```

```c++
// 1. 이제 문자열의 길이를 출력해보자. 
// 2. 아래의 Source Code는 Rectangle이라는 구조체 아래,
      length, width 변수에 각각 Data Type을 u32로 지정해주었다.
// 3. impl을 선언함으로써, 그 안에 Method를 만들 수 있게 해주었다.
// 4. 함수 안에 길이를 출력하는 len() 함수를 기입하였고, 1번째 인자로
      Self 즉, 자기 자신을 받고 출력할 때 'length'는 struct에서 선언한
      Data Type이 그대로 적용된다. 또한, 이 length Field 부분을 찾아서
      출력할 것이다.
// 5. 최종적으로, Main 함수에서 rect1의 길이를 출력하는 함수를 받아서
      출력할 것이다. 

struct Rectangle {
    length: u32,
    width: u32,
}

impl Rectangle {
    fn len(&self) {
        println!("Len is {}\n", self.length);
    }
}

fn main() {
    let rect1 = Rectangle {length: 50, width: 30};
    
    println!("The Area of the Rectangle is {} Square Pixels\n", area(&rect1));
    
    rect1.len()
}

fn area(rectangle: &Rectangle) -> u32 {
    rectangle.length * rectangle.width
}
```

```c++
// 1. 이번에는 Parameter를 2개 붙이는 법에 대해 알아보겠다.
// 2. Parameter가 뜻하는 값은 can_hold 함수에 있는 인자들을 뜻한다.
// 3. 이 Parameter는 무조건 기본으로 오게되고(&self), other 인자에는
      Rectangle struct를 참조하겠다고 선언하였다.
// 4. 그리고 Bool Data Type을 입력함으로써, 서로 크기를 비교하여
      T or F의 값을 출력하도록 지정하였다. 

struct Rectangle {
    length: u32,
    width: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.length * self.width
    } 
    
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.length > other.length && self.width > other.width
    }
}

fn main() {
    let rect1 = Rectangle {length: 50, width: 30};
    let rect2 = Rectangle {length: 40, width: 10};
    let rect3 = Rectangle {length: 45, width: 60};
    
    println!("Can Rect1 Hold Rect2? {}\n", rect1.can_hold(&rect2));
    println!("Can Rect1 Hold Rect3? {}\n", rect2.can_hold(&rect3));
}
```

```c++
// 1. 마지막으로, 연관 함수에 대해 알아보자.
// 2. 이 함수는 '&self'를 사용하지 않는다. 그 이유는 구조체에서
      &변수를 사용할 필요가 없기 때문이다. 즉, 더 이상 번거롭게
      '&Self' 인자를 쓰지 않아도 된다는 의미이다.
      
struct Rectangle {
    length: u32,
    width: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.length * self.width
    }
    
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.length > other.length && self.width > other.width
    }
}

impl Rectangle {
    fn square(size: u32) -> Rectangle {
        Rectangle {length: size, width: size}
    }
}

fn main() {
    let rect1 = Rectangle {length: 50, width: 30};
    let rect2 = Rectangle {length: 40, width: 10};
    let rect3 = Rectangle {length: 45, width: 60};
    let sq = Rectangle::square(3);
    
    println!("Can Rect1 Hold Rect2? {}\n", rect1.can_hold(&rect2));
    println!("Can Rect2 Hold Rect3? {}\n", rect2.can_hold(&rect3));
    
}
```

```c++
// 1. 또한, 기존에 있었던 IMPLementation 함수를 그대로 가지고와서 사용해도
      무방하다.

struct Rectangle {
    length: u32,
    width: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.length * self.width
    }
    
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.length > other.length && self.width > other.width
    }
    
    fn square(size: u32) -> Rectangle {
        Rectangle {length: size, width: size}
    }
}

fn main() {
    let rect1 = Rectangle {length: 50, width: 30};
    let rect2 = Rectangle {length: 40, width: 10};
    let rect3 = Rectangle {length: 45, width: 60};
    let sq = Rectangle::square(3);
    
    println!("Can Rect1 Hold Rect2? {}\n", rect1.can_hold(&rect2));
    println!("Can Rect2 Hold Rect3? {}\n", rect2.can_hold(&rect3));

   println!("The Area of the Rectangle is {} Square Pixels.\n", rect1.area());
}
```

<hr>

_[Reference 2](https://www.youtube.com/watch?v=RyopIyMjtcE&list=PLsGh7Wc318khzAJOJIJpkL0KHMr4iAk0z&index=8)_ <br>
_[Reference 3](https://rinthel.github.io/rust-lang-book-ko/ch05-03-method-syntax.html)_
