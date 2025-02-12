# _🔍 Why Rust?_

```txt
>> 블록체인 기술을 접해본 사람이라면, Source Code를 한 번쯤 다운받아서 본 경험이 있을 것이다.
   이 블록체인 기술의 핵심은 네트워크 뿐만 아니라, 처리속도도 빨라야 하기 때문에, 2017년 경
   C++ 기반의 Boost Library를 사용하는 것들이 생겨나기 시작했다. 그 대체재인 Rust가 최근 블록체인
   Source Code에서 사용하는 부분들이 많아졌다.
>> 또한, Rust는 메모리 안정성과 그 성능 및 편의성으로 C++언어를 대체하는 프로그래밍 언어로 쓰이고 있다.
```

<hr>

_[출처 1](https://www.youtube.com/watch?v=aW7wK4-2Dwc&list=PLdvEO-IMMcPvfiBkVwgIwDf4AuTjI2aeG&index=1)_ <br>
_[출처 2](https://www.youtube.com/watch?v=EUc9zz3sMwE&list=PLsGh7Wc318khzAJOJIJpkL0KHMr4iAk0z)_

# _⚙️ Settings_

![Image](https://github.com/user-attachments/assets/50873995-dc06-42ac-90aa-4be980849b8d)

```txt
>> 위의 사이트에 접속해서 두 가지 방법 중 하나를 택하면 된다. Online에서 진행할 것인지 아니면,
   Download 받아서 진행할 것인지.
>> 단, Terminal이 나오는 파트도 등장하므로, 가급적이면 Download 받아서 진행할 것을 권장한다.
```
![Image](https://github.com/user-attachments/assets/ab2816b9-c21c-485a-9aaa-8c404d122d80)
![Image](https://github.com/user-attachments/assets/f0c0d56c-d30f-44b5-83f8-bc2e28a31085)

```txt
>> Installer Program을 다운로드하고 실행하면 위와 같은 화면이 나온다. 1번을 계속치고, 다음으로 넘어가자.
>> 만약 오류가 발생하였다면, Visual Studio Installer를 설치하고 다시 실행해보자. 'Build Tools for Visual Studio 2019'
   까지 모두 설치해야 오류가 발생하지 않는다.
```

![Image](https://github.com/user-attachments/assets/a6b46b5f-c28f-4185-8665-8587f099a4d2)
![Image](https://github.com/user-attachments/assets/d6d9cc59-4c02-4efb-94c3-0d9669368679)

```txt
>> 설치가 정상적으로 된 화면은 위와 같다.
```

![Image](https://github.com/user-attachments/assets/9e95938e-b342-4734-ac1e-906117f56267)
![Image](https://github.com/user-attachments/assets/45a39cc8-c7c0-4a42-8021-0f741bc04a0a)

```txt
>> VScode를 설치한 상태에서, 위와 같은 파일 하나를 생성한다. 단, 파일을 생성할 때 'Cargo.toml'파일이
   존재하는 곳에 생성해야한다. 글쓴이는 이 파일이 있는 곳을 택하여 'main.rs'라는 rust 파일을 하나
   생성하였다.
>> 이제 잘 작동되는지 시험해보기 위해, 아래의 Source Code를 복사해서 실행시켜보자.
```

![Image](https://github.com/user-attachments/assets/ee2b8aa7-40a1-4b12-b65f-6f1adc10b840)

```C++
fn main() {
   println!("Hello, World!\n");
}
```

_~~이렇게 잘만 실행되면 좋겠지만...~~_

![Image](https://github.com/user-attachments/assets/e4eb0d09-78c4-4bde-803c-78a4ed6b6f04)

```txt
>> 실행시키는 도중, 위와 같은 오류가 발생하였다면 다음을 따른다.
   CMD 창을 열고, 순서대로 명령을 내린다.
```

```txt
>> rustup toolchain install stable-x86_64-pc-windows-gnu
>> rustup default stable-x86_64-pc-windows-gnu
>> cargo build
```

```txt
>> 이제 VScode Terminal에서 명령어를 치게 되면, 오류없이 잘 실행될 것이다.
   단, 'cargo build' 명령어를 치는 위치는 우리가 생성했던 'main.rs' 파일이
   존재하는 곳으로 Directory를 이동한 후에 내리도록 한다. 
```

<hr>

_[출처 3](https://ng1004.tistory.com/127)_

# _🪄 Execute Cargo Project_

![Image](https://github.com/user-attachments/assets/c0d57ab4-1be1-4169-a736-a1d37ba2bddc)

```txt
>> 우리가 미리 봣었던 'cargo.toml' 파일에 들어가 위와 같이 수정해준다.
```

![Image](https://github.com/user-attachments/assets/e28cddde-5849-4aa9-8712-56549a21834c)

```txt
>> 새로운 Project Package도 하나 생성해주자.
```

```txt
>> cd hello_cargo
>> cargo build
```

```txt
>> 위와 같이 결과값을 출력할 수 있고, 다른 예시로 'main.rs'를 출력해보자.
```

![Image](https://github.com/user-attachments/assets/ac4b1317-9219-4d46-a4b7-a51b3214e3f6)

```txt
>> Package를 생성하였다면, 위와 같은 Directory가 생성되었을 것이다. 'cd' 명령어를 넣을 필요 없이,
   'hello_cargo.exe' 파일의 경로를 붙여넣기만 해도, 값이 출력된다.
```

![Image](https://github.com/user-attachments/assets/211b9260-e2f5-4cd5-b21f-0c5c5621cf00)

```txt
>> 위의 예제는 Build를 하는 과정에서 오류를 잡아주는 역할을 한다. 이제 Build를 하기 전에, 문법에
   어긋난 것이 있는지 확인하고 실행시킬 수 있다.
```

<hr>










