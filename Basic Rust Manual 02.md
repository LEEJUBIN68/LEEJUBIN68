# _👀 Data Type of Rust_

| Length | Signed | Unsigned |
| --- | --- | --- |
| 8 - bit | i8 | u8 |
| 16-bit | i16 | u16 |
| 32-bit | i32 | u32 |
| 64-bit | i64 | u64 |
| 128-bit | i128 | u128 |
| arch | isize | usize |

```txt
>> Rust의 Data Type은 위와 같다.
>> 보통 양수와 음수값을 모두 사용하고 싶으면 'signed'를,
   양수값만 사용하고 싶다면 'unsigned' 자료형을 쓰는 것이
   보통이다.
>>  i = integer, u = unsigned라고 보면 된다.
>> 실수일 경우, C언어나 다른 프로그래밍 언어를 접해본 사람들은 알고있겠지만,
   float의 'f'만 따서 32bit로 표현하고 싶다면 'f32' 이렇게 표현하기도 한다.
>> 더 빠른 이해를 위해서 실습으로 알아보자.
```

_[출처 1](https://www.youtube.com/watch?v=8AWU1WHqAfM&list=PLsGh7Wc318khzAJOJIJpkL0KHMr4iAk0z&index=3)_ <br>
_[출처 2](https://doc.rust-lang.org/book/ch03-02-data-types.html)_

<hr>

```c++
# 기존에는 우리가 명시적으로 Data Type을 주지 않았기 때문에, 변수 선언만 되었다.
# 이제는 Data Type을 지정해서 출력해보자.
# 'i32'는 32까지의 범위를 지정해주는 것이다.
# 출력값은 -123112, 음수의 값이므로, Data Type = i로 하였다.

fn main() {
   let x: i32 = -123112;
   println!("{}", x);
}
```

```c++
# 숫자를 더 많이 집어넣어보자. 
# 친절하게 오류가 나오는데, 범위를 초과하였다는 오류일 것이다.
# 또한, 음수를 출력하려고 할 때 'u32'를 Data Type으로 입력하여도 오류가 발생할 것이다.
# unsigned integer는 음수를 출력할 수 없기 때문이다.

fn main() {
   let x: i32 = 123112111111111111111111111111;
   println!("{}", x);
}
```

```c++
# 실수의 형식은 이렇게 쓰인다.

fn main() {
   let x = 2.0;
   println!("{}", x);
}
```

```c++
# Python을 접해본 사람들은 다음의 Source Code가 출력되는 값이 예상이 갈 것이다.
# Tuple을 이용해서 값을 출력하는 Code인데, 우리가 많이 쓰이는 Data Type이 한눈에 보인다.
# Tuple의 Index 순서는 1이 아닌, 0부터 시작한다.
# 현재 tup.0이므로, 0번째 순서에 있는 500이 출력될 것이다.
# 그렇다면 tup.2는? 당연히 Tuple의 2번째 Index 번호인 korea'를 출력할 것이다.

fn main() {
    let tup: (i32, bool, char) = (500, true, 'korea');
    println!("{}", tup.0);
}
```

```c++
# 이제 오류에 익숙해졌다면, 다음의 오류를 예측할 수 있을것이다.
# 바로 let이라는 문법으로, tup를 정의하였기 때문에, 중간에 그 변수를 바꿀 수 없다는 문구가 나온다.
# 따라서 이 문법에서 오류를 해결하기 위해서는 let 앞에 'mut'를 기입해야한다.
# 우리가 또한 이렇게 오류를 금방 알아볼 수 있는 것도, 오류를 정확하게 잡아내주는 Rust의 힘이라는 것 잊지말자.

fn main() {
    let tup: (i32, bool, char) = (500, true, 'korea');
    tup.2 = 'Seoul';

    println!("{}", tup.2);
}
```















