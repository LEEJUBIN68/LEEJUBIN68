# _👸 Ownership and Stack of Rust_

```txt
>> 이제 Stack과 OwnerShip에 대해 알아보자. Stack이란 간단하게 LIFO(Last-In, First-Out)방식의
   자료구조로, 가장 최근에 들어온 Data가 가장 먼저 나간다는 뜻으로 이해하면 쉬울 것이다.
>> OwnerShip은 Rust의 가장 Unique한 특성이며, Rust Garbage Collector없이, Memory 안정성을 보장해준다.
   그러므로, Rust 내에서 이 요소가 어떻게 동작하는지 알아둘 필요가 있다.
```

```c++
// 1. 다음의 예제를 살펴보자.

fn main() {
    let s = 2;
    let x = s;
}

fn Function() {
    let a = true;
    let b = false;
}
```

<hr>

_[Reference 1](https://www.youtube.com/watch?v=3hyoKRDRovg&list=PLsGh7Wc318khzAJOJIJpkL0KHMr4iAk0z&index=7)_ <br>
_[Reference 2](https://rinthel.github.io/rust-lang-book-ko/ch04-00-understanding-ownership.html)_

## _Stack Table_

| Address | Name | Value |
| -- | -- | -- |
| 0 | s | 2 |
| 1 | x | s |
| 2 | a | True |
| 3 | b | False | 

<hr>

```c++
// 1. Stack 방식은 최근에 들어온 Data가 나가는 방식이므로,
      위의 예제에서는 'b -> a -> x -> s'순으로 사라질 것이다.
// 2. 이제 우리는 메모리에 Stack 방식으로 Data Type을 편하게
      넣을수도 있다.
// 3. 아래의 예제는 사용자가 만든 함수에 합을 구할 수 있도록 하고.
      각 변수에 Data Type을 지정해주었다.

fn main() {
    let s = 2;
    let x = s;
    
    fn Function(s, x);
}

fn Function(s: i32, x: i32) {
    s + y
}
```

<hr>

## _Stack Table_

| Address | Name | Value |
| -- | -- | -- |
| 0 | s | 2 |
| 1 | x | 2 |
| 2 | s | 2 |
| 3 | x | 2 | 

<hr>

```c++
// 1. 위의 예제에서는 'Function'이라는 함수에
      s와 x에 Data Type을 지정해주고, 그 합까지
      구하게 만들었다.
// 2. 따라서 x = 2 -> s = 2 순서로 메모리에서 지워질
      것이다.
// 3. 이번에는 Str Type을 살펴보자. 

fn main() {
    let s = 2;
    let string = String::from("Hello!");
}
```

<hr>

## _Stack Table_

| Address | Name | Value |
| -- | -- | -- |
| 0 | s | 2 |
| 1 | string | "Hello!" |
| 2 |  |  |
| 3 |  |  | 

## _Heap Table_

| Address | Name | Value |
| -- | -- | -- |
| 5 | s | "Hello!" |
| 6 |  |  |
| 7 |  |  |
| 8 |  |  | 

<hr>

```c++
// 1. 위에서 살펴본 예제에서는 String Type의 변수를
      선언하였다.
// 2. '::'의 의미는 동적으로 Size를 변환하겠다는 의미이다.
// 3. 하지만, 이번에는 두 개의 Table을 보아야한다. 
// 4. 위에서 언급하였듯이 우리가 '::'를 선언함으로써, 메모리를
      동적으로 사용하겠다고 하였다. 따라서, Heap Memory라는
      공간에 Data가 저장되는데, 지정 가능한 Memory를 찾고,
      배치를 하게 된다.
// 5. 여기서 Pointer라는 개념이 나오는데, 이 Pointer가 "Hello!"
      라고 저장된 Heap Memory가 있는 위치를 가리키게 되는 것이다.
// 6. 다음 예제를 살펴보자.

fn main() {
    let x = 6;
    let y = x;
    let s1 = String::from("Hello!"); 
    let s2 = s1;
    
    println!("{}, World!\n", s1);
}
```

<hr>

```c++
// 1. 위의 예제의 경우, 오류가 발생할 것이다.
// 2. 현재 s1은 이동해버리고, s2만 가리키고 있는 상태이므로,
      오류가 발생할 것이다.
// 3. 즉, s1을 Print 하려고 하면, 출력에 오류가 생길 것이고,
      현재 가리키고 있는 것은 s2 뿐이므로, s2를 출력하면
      정상적으로 실행될 것이다.
// 4. 그렇다면, 저 상태에서 s1을 출력하고 싶을 때, 어떻게 해야할까?

fn main() {
    let x = 5;
    let y = x;
    let s1 = String::from("Hello");
    let s2 = s1.clone();
    
    println!("{}, World!\n", s1);
}
```

<hr>

```c++
// 1. 정답은 s1을 Move 시키지 않고, Clone하는 것이다.
// 2. 이제 위의 예제를 실행시키면, s1 값도 출력할 수 있다.
// 3. 이번에는 소유권과 함수에 대해 알아보자.
// 4. 함수 단위에서 OwnerShip이 동작하는 방식도 크게 다르지 않다.

fn main() {
    let s = String::from("Hello");
    // s가 Scope 안으로 들어왔습니다.
    
    takes_ownership(s);
    // s의 값이 함수 안으로 이동했습니다.
}

fn takes_ownership(some_string: String) {
    println!("{}", some_string);
}
```

<hr>

```c++
// 1. s라는 변수에 Str Type인 "Hello"를 선언하였고, 'takes_ownership'이라는
      함수에서는 이 문자열이 출력되도록 설계하였다. 다시 이 함수를 Main 함수로
      불러와서 출력되도록 'takes_ownership(s)'도 선언하였다.
// 2. 다만, 위의 예제에서 이제 s를 출력하지 못할 것이다.
// 3. 그 이유는 s변수 역시도, Move 되었기 때문이다.
// 4. 좀 더 복잡하지만, 다른 예시를 들어보자.

fn main() {
    let s = String::from("Hello"); // s가 Scope 안으로 들어왔습니다.
    
    takes_ownership(s);            // s의 값이 함수 안으로 이동했습니다.
    
    let x = 5;                     // x가 Scope 안으로 들어왔습니다.
    
    makes_copy(x);                 // x가 함수 안으로 이동했습니다.
                                   // 단, i32는 Copy되므로, x를 이후에 사용해도 됩니다. 
}

fn takes_ownership(some_string: String) {
    println!("{}", some_string);
}

fn makes_copy(some_integer: i32) {
    // some_integer가 Scope 안으로 들어왔습니다.
    println!("{}", some_integer);
}

// 여기서 some_integer가 Scope 밖으로 벗어났습니다.
// 별다른 일은 발생하지 않습니다.
```

<hr>

```c++
// 1. 위의 예제를 살펴보면, x = 5라고 선언하였고, makes_copy라는 함수에서
      x를 출력하도록 만들었다. 다만, Data Type 'i32'는 Copy가 가능하기
      때문에, 문자열과 다르게 'println!("{}", x)'로 출력을 하여도 상관없다.
// 2. 다음 OwnerShip 예제를 살펴보겠다.
// 3. 이 예제에서는 s1에게 'gives_ownership'이 Return 값을 이동시키고,
      some_string 변수에서 "Hello"를 반환하고, 'gives_ownership' 함수가
      끝나면, Main 함수로 이동하여 출력된다. 

fn main() {
    let s1 = gives_ownership();              // gives_ownership은 Return 값을 s1에게 이동시킵니다.
    
    println!("s1 = {}\n", s1);               // s1은 Scope 밖으로 벗어나서, Drop이 호출됩니다.
}                                            

fn gives_ownership() -> String {             // gives_ownership 함수가 Return 값을 호출한 쪽으로 이동시킵니다.
    let some_string = String::from("Hello"); // some_string이 Scope 안에 들어왔습니다.
    
    some_string                              // some_string이 반환되고, 호출한 쪽의 함수로 이동됩니다.
}
```

<hr>

```c++
// 1. 위의 예제를 응용해보자.

fn main() {
    let s1 = gives_ownership();                       // gives_ownership은 Return값을 s1에게 이동시킵니다.
    let s2 = String::from("World!\n");                // s2가 Scope 안에 들어왔습니다.
    let s3 = takes_and_gives_back(s2);                // s2는 takes_and_gives_back 안으로 이동되었고, 이 함수가
                                                      // Return값을 s3로도 이동시켰습니다.
    println!("s1 = {}, s3 = {}", s1, s3); 
}                                                     // s1은 Scope 밖으로 벗어나서, Drop이 호출됩니다.

fn gives_ownership() -> String {                      // gives_ownership 함수가 Return값을 호출한 쪽으로 이동시킵니다.
    let some_string = String::from("Hello");          // some_string이 Scope 안에 들어왔습니다.
    
    some_string                                       // some_string이 Return되고, 호출한 쪽의 함수로 이동합니다.
}

fn takes_and_gives_back(a_string: String) -> String { // a_string이 Scope 안으로 들어왔습니다.
    a_string                                          // a_string은 반환되고, 호출한 쪽의 함수로 이동됩니다.
}
```

<hr>

# _📖 References and Borrowing of Rust_

```txt
>> 의미는 별다른 뜻이 없다. 말 그대로, 참조자와 빌린다는 의미를 가진 단어들이다.
```

```c++
// 1. 아래의 예제는 오류 예제이다.
// 2. 그 이유는 OwnerShip이 변경이 되었기 때문인데, 이때 's1'을 참조만 하겠다고
      선언하면, 오류가 생기지 않을 것이다.

fn main() {
    let s1 = String::from("Hello!");
    let len = calculate_length(s1);
    
    println!("The Length of '{}' is {}\n", s1, len);
}

fn calculate_length(s: String) -> usize {
    s.len();
    // len() 함수는 문자열의 길이를 Return 합니다.
}
```

<hr>

```c++
// 1. 's1' 변수와 'len' 변수에 '&'을 붙여서, '참조'만 String으로 하겠다고 선언하였다.
// 2. 아래의 경우, Scope 's'가 밖으로 나와도, Drop 처리가 되지 않을 것이다.
// 3. OwnerShip 즉, 소유권이 바뀌지 않는다.
// 4. Pointer가 가리키고 있는 순서는 다음과 같다.
// 5. s -> s1 -> 'Hello!'
// 6. 이렇게 Reference 형식으로 만드는 것을 Borrow 즉, '빌려주었다'라고 부른다.

fn main() {
    let s1 = String::from("Hello!");
    let len = calculate_length(&s1);
    
    println!("The Length of '{}' is {}\n", s1, len);
}

fn calculate_length(s: &String) -> usize {
    s.len()
    // len() 함수는 문자열의 길이를 Return 합니다.
}
```

<hr>

```c++
// 1. 아래처럼, OwnerShip의 소유권 즉, 이것은 빌려준 형태이기 때문에,
      절대로 사용자가 임의로 바꿀 수 없다.

fn main() {
    let s1 = String::from("Hello!");
    let len = calculate_length(&s1);
    
    println!("The Value of {} is {}.\n", s1, len);
}

fn calculate_length(s: &String) -> usize {
    s.push_str("내 맘대로 쓸거야!\n");
    s.len()
    // len() 함수는 문자열의 길이를 Return 합니다.
}
```

<hr>














