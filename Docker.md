# _📖 Why Docker?_

```txt
>> 하나의 예시를 들어보자. 친구는 컴퓨터에 'MySQL'을 에러없이 설치하였다. 하지만, 내 컴퓨터에 MySQL을
   설치하려고 하였으나, 에러가 발생하였다. 설치한 방식 그대로 지우고 깔고 다시 시도해보았지만, 똑같은
   에러가 반복하여 발생하였다. 이때, 생각할 수 있는 에러 원인은 다양할 것이다. 다른 버전을 착각하여
   설치하였든, 운영체제가 다르든, 내 컴퓨터에 설치되어있는 다른 프로그램과 충돌이 발생했든 다양하다.
   또한 설치 과정까지 말썽이라면, 새 컴퓨터를 구매한 후, MySQL을 설치할 때마다 번거롭게 귀찮게 될 것이다. 
```

```txt
>> 이 문제를 깔끔하게 해결하기 위해 등장한 것이 바로 'Docekr'라는 것이다. Docker는 명령어 몇 줄로 어떤
   컴퓨터에서든지 에러없이 소프트웨어를 잘 설치하고, 실행할 수 있게끔 도와준다.
```

```txt
>> Docker는 매번 귀찮은 설치 과정을 거치지 않아도 되고, 항상 일관된 프로그램을 설치할 수 있다.
   또한, 각 프로그램이 독립적인 환경에서 실행되기 때문에, 프로그램 간에 서로 충돌이 일어나는 것을 방지한다.
```

<hr>

_[출처(Reference)](https://www.youtube.com/watch?v=OPmSQCfzl1Q&list=PLtUgHNmvcs6rS5aNCRIZtVcyk3gRX2iOd)_<br>

# _🔧 Setting Docker_

```txt
>> What is nginx?
Nginx란 여러 기능을 가진 Server 중 하나를 의미한다.
대표적으로, 웹 서버(HTML, 웹 페이지를 렌더링 시키는 역할 등)가 있다.
```

![Image](https://github.com/user-attachments/assets/470d2d0c-beec-4af5-8b46-1099f7f64342)

```txt
>> 위와 같은 명령어로 Docker를 Install 한다.
```

![Image](https://github.com/user-attachments/assets/cb53d899-8fa9-4afb-af1d-ba54d091a9a7)

```txt
>> 명령어에서 오류를 발견할 경우, 위와 같이 대처한다면 해결될 것이다.
```

```txt
>> What is image?
우리들 추억속에 깃들어있는 '닌텐도'를 생각해보자. 닌텐도는 칩이라는 것을 꽂아야 게임이 돌아갈 수 있다.
이때, '칩'의 역할을 해주는 것이 Docker에서 Image라는 것이다. 즉, 프로그램을 실행시키는 데 있어서
필요한 모든 것들을 포함하고 있다.
```

```txt
>> What is container?
다른 분야에서도 마찬가지이지만, 'Container'라는 개념도 자주 쓰이니 알아두는 것이 좋다.
하나의 컴퓨터 환경에서 프로그램을 별도로 설치할 수 있게 만든 것이 Container라고 부르는데,
'Docker'에서는 이를 'Container'라고 부른다.
```

![Image](https://github.com/user-attachments/assets/3b6f9d5d-40aa-479d-b0c0-5c01348681ca)

| Image Name | Image Tag Name | Image ID Name | Image Created Date | Image Size |
|---|---|---|---|---|
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; nginx | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; latest | &nbsp; 9bea9f2796e2 | &nbsp;&nbsp;&nbsp;&nbsp; 2 months ago | &nbsp;&nbsp; 192MB |

# _🖨️ Print Nginx Website_

![Image](https://github.com/user-attachments/assets/0044c927-44a6-44d9-b2b1-d6c7acb22883)
![Image](https://github.com/user-attachments/assets/7d09548c-db8c-4e5f-9c7e-f91256b97227)

```txt
>> 위와 같은 에러를 안만나는 것이 좋긴하지만, 위와 같은 충돌이 발생하였다면 아래를 참고하여 해결하길 바란다.
   참고로, 글쓴이는 이와 같은 에러를 만나 고생하였다...
>> 위와 같은 에러는 'docker run --name webserver -d -p 80:80 nginx'를 치게되면 마주할 것이다. (아니면 좋고...)
```

![Image](https://github.com/user-attachments/assets/49fdd621-9e92-477f-8bd4-cb241ee47c4e)

```txt
>> ps -a: 현재 실행 및 생성된 Container에 대한 정보를 출력한다. 위와 같은 에러를 만났다면 이 Container들은 모두 삭제해야한다.
>> stop: 현재 구동중인 Container 서비스를 멈춰야한다.
>> rm: 서비스를 멈췄다면, 해당 Container들을 모두 삭제시킨다.
>> ps -a or ls -a: 둘 다 같은 내용을 출력하므로, 둘 중 하나만 명령어를 쳐도 상관없다. 아무 Container도 출력되지 않는다면 해결된다.
```

![Image](https://github.com/user-attachments/assets/72a1cf68-80bd-4569-9614-e55f4caf7d7f)

```txt
>> 본래 Port 번호를 80:80으로 하는 것이 이상적이나, 홈페이지가 출력이 되지 않을 수 있다.
   따라서, 위와 같은 Port 번호를 생성하고, 아래와 같이 Url을 쳐서 하는 방법이 가장 쉬울 수 있다.
```

![Image](https://github.com/user-attachments/assets/e4b59a76-1218-4eac-a7f6-1e385b4ae682)












