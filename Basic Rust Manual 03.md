# _👸 Ownership and Stack of Rust_

```c++
// 1. 이제 Stack에 대해 알아보자.
// 2. Stack이란 간단하게 LIFO(Last-In, First-Out)방식의 자료구조로,
      가장 최근에 들어온 Data가 가장 먼저 나간다는 뜻으로 이해하면
      쉬울 것이다.
// 3. 다음의 예제를 살펴보자.

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


```















