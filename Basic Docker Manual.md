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
>> What is nginx? ✏️
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
>> What is image? ✏️
우리들 추억속에 깃들어있는 '닌텐도'를 생각해보자. 닌텐도는 칩이라는 것을 꽂아야 게임이 돌아갈 수 있다.
이때, '칩'의 역할을 해주는 것이 Docker에서 Image라는 것이다. 즉, 프로그램을 실행시키는 데 있어서
필요한 모든 것들을 포함하고 있다.
```

```txt
>> What is container? ✏️
다른 분야에서도 마찬가지이지만, 'Container'라는 개념도 자주 쓰이니 알아두는 것이 좋다.
하나의 컴퓨터 환경에서 프로그램을 별도로 설치할 수 있게 만든 것이 Container라고 부르는데,
'Docker'에서는 이를 'Container'라고 부른다.
```

![Image](https://github.com/user-attachments/assets/3b6f9d5d-40aa-479d-b0c0-5c01348681ca)

| Image Name | Image Tag Name | Image ID Name | Image Created Date | Image Size |
|---|---|---|---|---|
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; nginx | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; latest | &nbsp; 9bea9f2796e2 | &nbsp;&nbsp;&nbsp;&nbsp; 2 months ago | &nbsp;&nbsp; 192MB |

<hr>

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

<hr>

# _💾 Install Nginx Image_

![Image](https://github.com/user-attachments/assets/962f09a3-e8c3-4172-931f-5f2d470962c5)

```txt
>> 본 과정은 Docker를 Pull하는 작업과 똑같다. 에러가 발생하였다면, 똑같이 대처하여 Nginx를 Pull 해준다.
```

![Image](https://github.com/user-attachments/assets/bd5f4b0c-59fb-4329-a602-2aea3df4e038)

```txt
>> 위의 과정을 마쳤다면, 'Docker Hub'를 검색하여 들어간다. 돋보기 란에는 'nginx'라고 입력해보자.
```

![Image](https://github.com/user-attachments/assets/4649f711-e4c8-45ee-885c-1a0a0847aa6e)

```txt
>> nginx와 같은 공식 'image'들은 DockerHub에서 많이 다운로드 받기 때문에, 우리는 여기서 Image를 Pull 할 것이다.
```

![Image](https://github.com/user-attachments/assets/d9bbc438-852a-4434-aff0-142a0177588e)

```txt
>> DockerHub에서 위와 같은 명령어로 Image를 다운로드 받을 수 있다.
```

![Image](https://github.com/user-attachments/assets/873e9102-56a9-42e1-885e-e358939bc9cf)

```txt
>> Nginx Image를 다운받았다면, 'Tag'에 들어가서 'latest'라는 이름으로 검색해보자.
```

![Image](https://github.com/user-attachments/assets/11d40d9a-3f75-4970-91df-82f36ce442ce)

```txt
>> 'latest'라는 Tag명을 가진 Image도 다운로드 받을 수 있다.
```

![Image](https://github.com/user-attachments/assets/16710998-469f-4cb2-bf82-257afead269d)

```txt
>> 방금 다운로드 받은 'latest'와 앞에서 다운로드 받았던 'stable-perl'의 Tag명을 가진 Image 2개가 설치된 것을 확인할 수 있다.
```

<hr>

# _✖️ Delete Nginx Image_

![Image](https://github.com/user-attachments/assets/848e3c96-7d7c-4807-a3e2-0ddece82002c)

```txt
>> Image 파일들을 많이 설치하고, 그 양이 너무 많아서 삭제하고 싶을 때가 있다. 간단하게 위의 명령어를 실행해서 삭제가 가능하다.
```

![Image](https://github.com/user-attachments/assets/26ebce37-e76b-41ca-8315-2c20b74a099e)

```txt
>> 위의 명령어를 쓸 때 Container ID의 몇 자만 쓰더라도, 해당하는 파일들은 모두 삭제된다. 삭제된 것을 확인했다면, 나머지도 지워보자.
```

![Image](https://github.com/user-attachments/assets/362f4ea3-f15a-4e0c-83a4-a75e15cd24fb)

```txt
>> 하지만, 나머지 Image를 삭제하고 싶어도, 삭제가 진행되지 않는다. 그 이유를 살펴보니 Image가 사용되고 있어서 삭제를 진행할 수 없다고
   말하고 있다. 이전에 우리는 Container를 중단시킨 바가 있다. 하지만, 이 중단시킨 Container에서 위의 Image를 쓰고 있어서, 삭제를
   못한다는 의미이다. 즉, rm이라는 명령어는 사용하지 않는 Image에 대해서만 삭제할 수 있는 명령어이다. 이럴 경우에는 어떻게 처리할까? 
```

![Image](https://github.com/user-attachments/assets/88208ce7-385e-4dee-8b8b-923513375ffe)

```txt
>> 우리가 자주 사용했던 '-f'를 이용하여 강제적으로 제거할 수 있다. 단, 실행중인 Container에 대해서는 제거를 해주지 못하니 명심하자.
```

![Image](https://github.com/user-attachments/assets/b5c2491b-8670-45a4-89b8-79bdda649e23)

```txt
>> Container에서 사용하고 있는 Image들을 모두 삭제해버리고 싶을 때는 위와 같은 명령어를 응용해서 쓸 수 있다. 쓸모없는 Image 파일들이
   많이 누적되어 있다면, 위의 명령어처럼 응용해서 사용할 수 있다는 것도 알아두자.
```


