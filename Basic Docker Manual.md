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
>> 위와 같은 에러는 'docker run --name webserver -d -p 80:80 nginx'를 치게되면 마주할 것이다. 
```
~~(아니면 좋고...)~~

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

<hr>

# _🪄 Execute & Create Container_

![Image](https://github.com/user-attachments/assets/a1652f31-2a65-4b89-bc32-ec869df4863b)

```txt
>> 'nginx'라는 Image를 생성하여 Container를 만들고 실행해보자!
```

![Image](https://github.com/user-attachments/assets/509d3a81-1554-4978-b691-4ad37101a127)

```txt
>> 위에서 보았듯이 Container의 PortID, 생성된 Image 이름, 생성된 날짜 및 상태 등을 확인할 수 있다.
```

![Image](https://github.com/user-attachments/assets/ec4c3310-2f13-4934-bec9-6c03e118e913)

```txt
>> ContainerID의 앞자리 3개만 쳐도 Container를 실행시킬 수 있다.
```

![Image](https://github.com/user-attachments/assets/b3cc43af-1964-4466-afb4-41240a5694b7)

```txt
>> 그리고, 상태도 업데이트 된다.
```

<hr>

# _🔥 Applying Container_

```txt
What is Foreground? ✏️
>> 내가 실행시킨 프로그램의 내용이 화면에서 실행되고, 출력되는 형태. 즉, 무언가를 설치하거나 실행하였을 때
   즉각적으로 내가 보이고, 확인할 수 있는 상태를 Foreground라고 부른다.
>> 이 Foreground 상태에서는 즉각적으로 상태 메세지를 보내야하다 보니, 내가 조작할 수 있는 것이 없다.
```

```txt
What is Background? ✏️
>> 내가 실행시킨 프로그램이 컴퓨터 내부적으로 실행되는 상태. Foreground와 반대로, 현재 프로그램이 실행되거나
   설치되고 있는 Log를 확인할 수 없다. 즉, 내부적으로 알아서 돌아가는 형태라고 보면 된다.
>> Background 상태에서는 기다림없이 추가적으로 명령을 내릴 수 있다.
```

![Image](https://github.com/user-attachments/assets/5ca17fca-802c-48e9-8de4-c8736f7365c5)

```txt
>> 'nginx'라는 Image를 생성하여 실행한다. 하지만, 설치가 되었다는 말만 나오고, 명령창으로 돌아가지지
   않는다. 이때, ctrl + c를 누르면 나가질 것이다. 그리고, 이것을 'Foreground' 상태라고 부른다.
```

![Image](https://github.com/user-attachments/assets/1f178ca9-cfd2-4f90-89b4-939d97acb3e6)

```txt
>> 이제 우리가 이전(GoormIDE x BootStrap편 참고)에 띄어보았던 Nginx를 이용해서 웹 사이트를 띄워보겠다.
```

![Image](https://github.com/user-attachments/assets/5d3959e2-be53-4de9-951c-d0d44fa64fdc)

```txt
>> 우선, 그동안 쌓아놓았던 Container와 Image를 정리하자. 단, 현재 돌아가고 있는 Container 및 Image는
   서비스를 중단한 후, 제거해야 한다. 그렇지 않으면 오류가 발생할 것이다.
```

![Image](https://github.com/user-attachments/assets/074d99b9-2184-40ba-a735-d3363f0f5523)

```txt
>> rm 명령어를 추가하여 넣을 때, 위처럼 Container의 ID를 한꺼번에 입력해서 제거할 수도 있다.
```

![Image](https://github.com/user-attachments/assets/ea30ea81-60f8-4796-806c-b4839e5d0490)

```txt
>> Container를 제거하였다면, Image도 빠르게 제거해준다.
```

![Image](https://github.com/user-attachments/assets/a3e5ccc1-963f-452e-ba99-f3a32205dcd4)
![Image](https://github.com/user-attachments/assets/0c1a7cc8-1adc-4504-8200-e3660bf13c09)

```txt
>> 위와 같이 아무것도 뜨지 않는다면 성공.
```

![Image](https://github.com/user-attachments/assets/636450c2-0df0-4b28-8e6b-074657bf5114)

```txt
>> 'nginx'라는 Image 안에 'my-web-server'라는 이름을 붙여서 하나의 Container를 생성하고 실행해보자.
   이렇게 이름으로 구분되어 있으면, Container를 찾기 더 수월해질 것이다.
>> 다시 Container와 Image를 제거하고, 다음 과정을 따른다. 
```

![Image](https://github.com/user-attachments/assets/6b01399c-8456-4bea-8c98-970ea10579ae)

```txt
>> docker image와 함께 쓸 수 있는 명령어들을 조회할 수 있다. 
```

![Image](https://github.com/user-attachments/assets/96605cbe-973b-4daa-bd84-acb1dc8be67a)

```txt
>> docker run 명령어를 조금더 응용해보았다. 위 명령어의 의미는Docker를 실행하는 Host의
   '4000'번 Port를 Container의 '80'번 Port로 연결하겠다는 뜻이다.
```

![Image](https://github.com/user-attachments/assets/87209194-6298-4b0b-8285-a3e1118d8937)

```txt
>> 'Ports'에서 '4000'번 Port를 '80'번 Port로 연결시킨 것을 확인할 수 있다. 이제 Chrome을 켜고 실행해보자.
```

![Image](https://github.com/user-attachments/assets/8a00dc40-4129-48b9-b009-18a56e536edb)

```txt
>> 다음과 같이 창이 나온다면 성공이다.
```

<hr>

# _❌ Delete Option Applying_

![Image](https://github.com/user-attachments/assets/05be5e3c-a835-4edb-bff5-2369131b7089)

```txt
>> 위와 같이 'nginx' Image 안에 3개의 Container를 생성해보자.  
```

![Image](https://github.com/user-attachments/assets/f12267e3-6629-4c26-91c0-8e89734824b9)

```txt
>> 위에서 배웠던 것처럼, Container 서비스를 멈추고 제거를 해야한다. 하지만, 이번에는 조금 더 응용해서 제거하는
   명령어를 내려보자.
```

![Image](https://github.com/user-attachments/assets/1ea050c7-1fcd-4ced-9023-afce3348acf2)
![Image](https://github.com/user-attachments/assets/7c85a190-0a61-48b5-84a0-21a92ef557df)

```txt
>> 'ps -a'와 'ps'의 차이점은 전체 Container를 조회할 것인지, Local Container만 조회할 것인지의 차이로 나뉜다.
   즉, 단순히 'ps'만 치게 된다면 Local 상에 있는 Container만 보이기 때문에 Container를 중지시키고
   제거 후 조회하면 아무것도 보이지 않을 것이다. 하지만, 전체 조회인 'ps -a' 명령어를 치게 되면
   Stop한 Container를 포함해서 모든 Container의 목록들을 조회할 수 있다.
```

![Image](https://github.com/user-attachments/assets/e70dc372-e0e7-4a20-b072-8125f717aa5a)

```txt
>> 우리의 목적인 'rm'을 응용해서 위와 같은 명령어를 내려보았다. 단순히 'rm' 명령어를 쳐서 Container를
   일일이 지우기는 번거로울 것이다. 그래서 응용한 것이 바로 위의 명령어이다. 이 명령어를 내리게되면,
   멈춰있는 모든 Container를 한번에 제거할 수 있다.
>> 'kill' 명령어를 내려, 시스템을 차단하는 방법도 있지만, 최후의 수단으로 쓰길 바란다. 이 명령어를 실행하면
   파일들이 모두 손상되기 때문에, 컴퓨터가 작동 불가 상태나 급한 상황인 경우가 아닌 이상 사용하면
   위험할 수 있으니 신중하게 사용하자.
>> 가장 안전하게 제거하는 것은 'stop' 이후 'remove'하는 것이다.
```

![Image](https://github.com/user-attachments/assets/d7feb260-3cde-4467-b79d-248477dc4633)

```txt
>> 위에서 언급하였듯이 Stop을 한 후, 제거하는 것이 가장 안전한 방법이다. 하지만, 우리가 중요한 작업을 하고
   있는 중이 아니라면, 강제적으로 ShutDown 시키는 법을 알아보겠다. 위의 방법으로 '-f'를 붙이면 강제적으로
   Stop을 하지 않아도 Container를 강제적으로 삭제시킬 수 있다.
>> Container나 Image 삭제는 자주쓰게 될 것이니 유의사항과 명령어를 잘 숙지하기를 바란다.
```

<hr>

# _🪪 Docker Log(History)_

![Image](https://github.com/user-attachments/assets/52f93b74-c50e-47e9-81ca-bebc2b699891)

```txt
>> Container 하나를 실행해보자.
```

![Image](https://github.com/user-attachments/assets/2a56afbf-ccd0-410c-aa68-e949f0f7cef3)

```txt
>> 해당 Container의 ID를 위와 같이 치게되면, 정보들이 나열된다. 하지만, 이 많은 Log들을 보기에는
   정리도 되어있지않고, 난잡해보인다. 내가 보고싶은 Log만 보는 방법을 아래와 같이 소개한다.
```

![Image](https://github.com/user-attachments/assets/d9748108-6353-48b2-8ae2-ceed6f17759a)

```txt
>> 위의 Log들 중에서 [notice]라고 써있는 Log들만 모아서 보고싶어서 마지막 8줄만 보여달라고
   위와 같이 명령을 내렸다. 이렇게 해당되는 정보만 골라서 조회할 수 있다는 점도 숙지하길 바란다.
```

![Image](https://github.com/user-attachments/assets/46495eb9-4d51-4342-b050-3b1ad5ddbe57)
![Image](https://github.com/user-attachments/assets/3f95e9ac-6ccc-473c-8d76-007895228226)

```txt
>> 이제 Nginx 웹 사이트를 띄워서 해당 페이지의 Log를 출력해보자. Port는 에러가 날 경우, 위와 같이
   '80:80' Port가 아닌, 다른 Port 번호를 입력해서 명령을 내리길 바란다. (위의 자료 참고)
```

![Image](https://github.com/user-attachments/assets/f2d149c4-fc9a-41b9-a5d9-157dbf721852)

```txt
>> 새로고침 버튼을 누르면, 위의 사진처럼 Log가 전달되는 것을 볼 수 있다. 하지만, 웹 페이지의
   Log들만 보고싶고 쓸데없이 많은 양의 Log들을 모두 보고싶지 않다. 이때는 아래와 같이 실행한다.
```

![Image](https://github.com/user-attachments/assets/3b3bc7de-56ec-4d3d-916c-7bebc22b6585)

```txt
>> 위와 같이 명령어를 치게 될 경우, 웹 페이지에서 새로고침 한 Log들만 모아서 출력되는 것을 확인할 수
   있다. (Foreground 상태에서 나가는 단축키는 Ctrl + c이다. 기억해두자.)
```

<hr>

# _🔌 Connect to Container_

![Image](https://github.com/user-attachments/assets/7bc04b0d-2d7d-44ac-86f2-be4516d421a8)

```txt
>> 다시 Container를 밀어버리고, 새 Container를 실행시키자.
```

![Image](https://github.com/user-attachments/assets/75a48148-db6e-4a6d-ace0-cd45ca004479)

```txt
>> 위의 명령어를 실행시키면, 명령어를 사용하는 사용자가 바뀌게 된다. 즉, Container 내부에 접속된 것이다.
```

![Image](https://github.com/user-attachments/assets/de145b60-a19e-456a-8ab6-5e2c048dcc83)

```txt
>> Container 내부의 파일 List들을 출력한다. 그 중 nginx에 관한 파일을 살펴보자.
```

![Image](https://github.com/user-attachments/assets/ae5c073a-01b5-461b-b38d-7ba990a422aa)

```txt
>> 'cd /etc/nginx'로 Directory를 이동하고, List를 살펴보자. 가장 눈에 띄는 것은 'nginx.conf' 파일이다.
```

![Image](https://github.com/user-attachments/assets/6c426e15-e685-4651-91ef-fff8ee57d327)

```txt
>> 위의 명령어를 실행하면, 파일 내부를 확인할 수 있다. 이 파일은 Container 내부에서 디버깅을 할 때,
   엔진 세팅을 어떻게 할 것인지 수정할 수 있는 파일이다. 이렇게 Container 내부와 Localhost 사용자를
   번갈아가면서 파일을 수정하거나 볼 수 있다. 이제 Container에서 나가서 되돌아가보자.
```

![Image](https://github.com/user-attachments/assets/2474f35e-e966-4f16-abd6-3d591553f602)
![Image](https://github.com/user-attachments/assets/beef5664-bc9d-4bbc-996f-a67ab7b91e41)

```txt
>> 위와 같이 exit 명령어 하나만으로 빠져나올 수 있다. ls 명령어로 다시 확인하였더니 Local 환경으로
   변한 것을 볼 수 있다.
```

<hr>

# _💽 Install Redis_

```txt
What is Redis?
>> Redis란 Remote Dictionary Server의 약자로, 메모리 내에서 데이터가 저장되어, 이를 통한 서비스를
   제공해주는 형태로 이루어지는 Open Source System이다. 메모리를 기반한 DB로서 키값(Key-Value) 구조의
   데이터 저장이 가능하며 빠른 조회 및 쓰기를 지원해준다.
```

![Image](https://github.com/user-attachments/assets/94d3b83e-30dd-4e81-a2b5-4a98f73e3de5)

```txt
>> 우선 Redis를 가져오기 위해서, DockerHub에 접속해서 Image를 가져오자.
```

![Image](https://github.com/user-attachments/assets/7a374dfe-70ae-438a-934c-cd653a94ec10)
![Image](https://github.com/user-attachments/assets/7ca0fbe0-8a4a-47fc-9e67-0606749d4609)

```txt
>> 검색 창에 Redis를 치고, 오른쪽에 있는 명령어를 확인한다.
```

![Image](https://github.com/user-attachments/assets/89255d21-00e6-461c-8c86-47a558fa1359)

```txt
>> Image를 다운로드 받은 후 위와 같이 실행한다. 하지만, 우리는 옵션에 대해 명확히 할 필요가 있다.
>> '-d' 옵션은 Background 상태에서 실행한다는 뜻이다.
>> '-p' 옵션은 Port Mapping을 실행할 것이라는 의미이다.
>> 우리가 Nginx 엔진을 실행하였을 때, 기본으로 하는 Port 번호는 80:80이었다. 하지만, Redis에서는
   6379:6379이다. 이렇게 Port를 Mapping하면 그 뒤로는 앞에서 배운 명령어 및 과정은 비슷하다.
```

![Image](https://github.com/user-attachments/assets/7347ba4a-c615-400b-85d2-83a02301f32d)

```txt
>> 우리가 다운받고자 하는 Image는 Redis이므로, 제대로 다운받아졌는지 확인하기 위해, 위와 같은 명령어를
   실행한다. 
```

![Image](https://github.com/user-attachments/assets/2bc45c64-8c3c-4b7f-895e-3a1cf953ff7d)

```txt
>> 또한, ProcesS가 잘 진행되고 있는지, Container가 잘 실행되고 있는지 위와 같이 확인해준다. Port Mapping도
   6379번으로 잘 되어있는 것을 확인할 수 있다.
```

![Image](https://github.com/user-attachments/assets/a4ae7ed6-0a9d-415d-8f0b-c0b2b3334a21)

```txt
>> 해당 ContainerID의 Log들을 조회할 수도 있다. 아래에 보면, Server Initialized가 되어있는 것을 볼 수 있는데,
   서버도 잘 실행되었음을 알 수 있는 문구이다.
```

![Image](https://github.com/user-attachments/assets/940a8bb7-2800-45a4-a295-e0181a4449cb)

```txt
>> 우리가 지난 시간에 배운 Container에 접속하는 법을 사용해보자. 
```

![Image](https://github.com/user-attachments/assets/4e075afa-7dd3-44a3-99e8-bc7ce5171e6e)

```txt
>> 하지만, 그냥 접속한 상태에서 ls를 치게되면, 파일들이 아무것도 없다. 따라서 다른 Directory에 들어가서
   List들을 찾아보자.
```

![Image](https://github.com/user-attachments/assets/5576ee6e-6051-4b34-97b0-79bff96fb53f)

```txt
>> 그중 pwd를 치게되면 경로가 나오게된다. 즉, Container 내부에서 여러 명령어를 치고 있음을 알 수 있다.
```

![Image](https://github.com/user-attachments/assets/f0204630-c9f7-4a1d-93e8-b0ecb321474b)

```txt
>> 그중 pwd를 치게되면 경로가 나오게된다. 즉, Container 내부에서 여러 명령어를 치고 있음을 알 수 있다. 최종적으로
   Redis에 접속하기 위해, 저런 생소한 명령어도 실행해본다. 
```

![Image](https://github.com/user-attachments/assets/4c290099-e4ef-42f2-bb64-00fabcd1c41a)

```txt
>> Redis에 접속하여, 여러 명령어를 치고 그 값을 확인해보자. 잘 작동되고 있음을 확인해볼 수 있을 것이다. 다시
   Local 환경으로 돌아가기 위해, Exit 명령어로 나간다.
```

![Image](https://github.com/user-attachments/assets/38283ec2-fe0d-4d6d-84f1-fbdf5c8657c2)
![Image](https://github.com/user-attachments/assets/a10adb81-2664-4b9f-a4b5-af1b7e81a266)
![Image](https://github.com/user-attachments/assets/0f580cb2-a9f8-4fb7-bd49-d75c363b8653)

```txt
>> Container에서 나왔다면, 우리가 수도없이 많이 했던 Container와 Image를 제거해보자. 그 과정과 명령어는 동일하다.
```

<hr>

# _🔊 Docker Volume_

```txt
What is Volume? ✏️
>> 우리는 지금까지 Docker를 활용하여 특정 프로그램을 Container 상에 띄울 수 있었다. 그저 Image를 생성하고,
   Container를 실행시키면 끝이다. 하지만, 우리가 Container와 Image를 지우면서 생각해보았는가? 새로운
   Container를 만들어서 통째로 갈아끼우는 방식으로 명령어를 써왔는데, 이것이 효율적이라 생각해왔다.
>> 이러한 특징으로 Container를 다루게 된다면, Container 내부에 있는 데이터도 같이 삭제된다. 이렇게
   Container가 가진 한계점을 보완해주는 것이 '볼륨(Volume)'이다. 
```

```txt
What is Docker Volume? ✏️
>> Docker에서의 Volume은 데이터를 영구적으로 저장하기 위한 방법이다. 이 볼륨(Volume)이라는 것은
   Container 자체에서 저장 공간을 사용하지 않고, Host 자체의 저장 공간을 공유해서 사용하는 형식이다.
```

# _🗄️ Docker MySQL_

![Image](https://github.com/user-attachments/assets/37d65eae-8b81-4d5a-9eec-121dc7611178)
![Image](https://github.com/user-attachments/assets/e3f38370-3b72-4072-b6c5-30a17de80723)

```txt
>> 위와 같이 MySQL을 설치하고 실행해보자. 만약 오류가 발생한다면, 아래 사항을 따르면 된다.
```

## _docker: Error response from daemon: Ports are not available_

```txt
>> 이러한 오류가 뜨는 경우는 MySQL이 설치된 이후, 실행되고 있기 떄문이다.
>> 이 오류를 해결하기 위해, 아래의 명령어를 차래대로 삽입한다.
```

### _3306번 Port에서 어떤 프로그램이 실행되고 있는지를 조회_

```txt
>> sudo lsof -i:3306
```

### _해당 프로그램을 ShutDown_

```txt
>> kill <PID>
```

### _권한이 없는 오류 발생시, 다음 명령어를 진행_

```txt
>> sudo kill <PID>
```

### _프로그램이 종료되었는지 마지막으로 확인_

```txt
>> sudo lsof -i:3306
```

### _MySQL 재실행_

```txt
>> docker run -p 3306:3306 -d mysql
>> docker ps -a
```

![Image](https://github.com/user-attachments/assets/6a5cde02-b943-4150-b4c1-fcba551f7f36)

```txt
>> 위와 같이 실행중인 Container의 Log를 살펴보자. 오류 하나를 발견할 것이다. 이 오류는 PassWord를
   정의하지 않아서 생기는 오류이다. 이 오류를 해결하기 위해 아래의 명령어도 실행해보자.
```

![Image](https://github.com/user-attachments/assets/6e60e94d-83fa-46eb-91d4-d942fe780d7a)

```txt
>> 위처럼 PassWord를 정의해주도록 한다. '=' 오른쪽에 자신이 원하는 비밀번호를 무작위로 치면 된다.
>> '-e' 옵션을 붙이는 이유는 환경 변수를 설정하기 위함이다.
```

![Image](https://github.com/user-attachments/assets/a4463ab6-29fa-4126-ab97-78c72b2943bb)
![Image](https://github.com/user-attachments/assets/15bc1cab-9b99-42f7-be4a-91ba3b34eda8)

```txt
>> MySQL Image가 정상적으로 작동되고 있는 것을 볼 수 있다. Log도 마찬가지로, 'process done.
   Ready for start up'이라는 문구를 보게 되면 잘 실행되고 있음을 알 수 있다.
```

![Image](https://github.com/user-attachments/assets/1deb75aa-18e9-47b0-b725-8731bd068f79)

```txt
>> Container 내부에 접근해서, 위에서 작성한 환경변수가 잘 수정되었는지 확인해보자. 
```

![Image](https://github.com/user-attachments/assets/0a7d3630-3baf-4b51-907b-c682c321d217)

```txt
>> MySQL Container의 리스트들은 다음과 같다. 우리는 파일로 접근하는 것이 아니라, 환경변수를
   확인하기 위해 접근하였으므로, 아래의 명령어로 PassWord를 출력해보자.
```

![Image](https://github.com/user-attachments/assets/94f00e01-0863-44c9-bb1c-74be886e1b95)

```txt
>> 우리가 설정했던 PassWord가 정상적으로 바뀌었음을 알 수 있다.
>> '$' 옵션은 해당 환경변수의 값이 잘 저장되었는지 확인할 때 많이 쓰인다. 자주 쓰이는 옵션이니
   '-d', '-p' 옵션처럼 잘 기억해두자.
```

![Image](https://github.com/user-attachments/assets/22673b93-325f-43c5-a865-ba76599ea2da)

```txt
>> 다시 Container에서 나가자. Ctrl + c를 칠 필요없이 exit 명령어 한 번만 치면 밖으로 나가질 것이다.
```

![Image](https://github.com/user-attachments/assets/5f5f7b78-b1f6-4c94-b5a3-54c410d688f2)

```txt
>> 환경변수도 잘 바뀌었고, MySQL Image도 정상적으로 설치되었으니 이제 MySQL을 실행해보자. 프로그램은
   다양하지만, 본 강의에서는 '데이터 그립(DataGrip)'을 다운받아서 실행하였다. 설치가 완료되면 자동으로
   실행될테니 기다려보자. 나오지 않는다면, 환경설정에 들어가서 실행한다.
```

![Image](https://github.com/user-attachments/assets/5182404a-3996-4474-bd6a-d31801790966)

```txt
>> 우리가 설정해놓은 PassWord를 입력하고, Test Connection을 해보자.
>> 'User' 이름은 Host가 아닌 root로 바꿔서 접속한다.
```

~~잘못찍혔다...~~

![Image](https://github.com/user-attachments/assets/9654174b-0aea-4619-9826-ff9e893b3cf8)

```txt
>> 접속에 성공하였다면, 다음과 같은 문구가 나올 것이다. 이번에는 다시 터미널로 돌아가서,
   Container들을 강제로 ShutDown 시키고, 제거까지 해보자.
```

![Image](https://github.com/user-attachments/assets/01a6d4eb-2dad-493c-a0e2-290bb263d106)

```txt
>> 한번에 강제 종료시키고, 제거를 하기 위해 '-f' 옵션을 추가해서 조회해보자.
```

![Image](https://github.com/user-attachments/assets/d5bf512b-2839-4823-a90d-b3dad96c7060)

```txt
>> 다시 접속이 불가하다는 문구가 등장한다. 이로써 우리는 3가지의 Image를 설치하고 구동시켜보았다.
   하지만, MySQL Image는 Container를 제거하여도 데이터를 따로 백업할 수 있다는 점에서 의의가 있다.
   이를 더 심화적으로 사용해보자. Container를 제거해도 문제없이 Docker를 사용할 수 있을 것이다.
```





















