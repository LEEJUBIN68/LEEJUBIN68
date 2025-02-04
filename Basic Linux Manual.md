# _Linux Command_

```txt
Warning!
This manual begins with the assumption that you have already installed VMware from the Git manual.
If you had not installed VMware, please read the 'Git' manual and come back.
```

```txt
Warning!
This reference consists of Korean.
Please bring your own translation.
```

## _1. Print Words & Date + Clear Your Commands_

![Image](https://github.com/user-attachments/assets/05986a94-2e39-42dd-80d3-8cb894ce944c)

```txt
echo: 문자열, 숫자 등을 출력
timedatectl: 해당 시간에 대한 정보들을 출력.
timedatectl set-time "yy-mm-dd": 날짜와 시간 모두 설정.
timedatectl list-timezones | grep Asia: 원하는 시간대의 국가를 조회.
timedatectl set-timezone Asia/Seoul: 변경하고자 하는 시간대를 입력 및 변경.
date: 현재 위치해 있는 시간대를 출력.
clear: 명령어 Clear.
```

## _2. Print History_

![Image](https://github.com/user-attachments/assets/1daa9717-7c50-4877-ace6-1000e00f88b9) <br>
![Image](https://github.com/user-attachments/assets/b8717153-ff1f-4ff3-829e-e11efdfacb8f)

```txt
history: 지금까지 썼던 명령어들을 모두 출력.
```

## _3. Print Before Command_

![Image](https://github.com/user-attachments/assets/ddf38759-36f5-442b-892f-ed4a3849fe91)

```txt
!!: 이전에 썼던 명령어를 출력.
```

## _4. Print File Path_

![Image](https://github.com/user-attachments/assets/16e40c92-b6f2-409e-950d-0a656e2f56b9)
![Image](https://github.com/user-attachments/assets/ec31e639-cd07-42c9-8e0c-2e549e1ed27a)

```txt
echo $PATH: 환경변수들의 경로인 path를 출력하는 명령어.
which: 특정 명령어의 위치를 찾아줌.
which -a find: 검색 가능한 모든 경로에서, 해당 명령어를 찾아줌.
whereis: 실행 파일의 위치, 소스 위치, 'man' 페이지 파일의 위치까지 찾아줌.
locate *.bak: 현재 로컬에 존재하는 '*.bak'파일 찾기.
locate -n 10 *.conf: 특정 패턴에 해당하는 파일들 중에서 지정한 개수만큼 검색.
```

## _5. Install Calendar Packages_

![Image](https://github.com/user-attachments/assets/69c85722-b494-4800-9b46-ca26c2a8ad12)
![Image](https://github.com/user-attachments/assets/a7251dfa-e770-4628-8c51-2319a696e0b6)
![Image](https://github.com/user-attachments/assets/09db662f-bd6f-4974-ac22-93e45d1a8ff3)

```txt
sudo apt install: 다양한 Package를 다운받을 수 있음(본 과정은 Calendar를 출력하기 위한 패키지 설치 과정).
```

## _6. Print Calendar_

![Image](https://github.com/user-attachments/assets/0e55a2ab-57c7-4622-bdf3-1201bace597f)

## _7. Print Calendar(Year: 2022)_

![Image](https://github.com/user-attachments/assets/0b954236-5f82-4744-a239-d86ff6455ddf)

## _8. Print Calendar(Year + Month: 2022. 08.)_

![Image](https://github.com/user-attachments/assets/b5bb85ed-e836-4e62-a819-dd802710155d)

## _9. Print Calendar(Recent Year)_

![Image](https://github.com/user-attachments/assets/d3f0aea2-cabc-48f0-9034-f8c20c99f023)

## _10. Print Calendar(Previous month and next month: 2022. 08)_ 

![Image](https://github.com/user-attachments/assets/1cb07ad7-6191-4967-9397-6bd66de51a0b)
![Image](https://github.com/user-attachments/assets/38a8e25e-7a91-4e3c-8e28-6b1d0620e9dc)
![Image](https://github.com/user-attachments/assets/b31a4d3b-814b-4046-98c1-b85d7c3ec166)

## _11. Print Time(UTC & Your Location Time)_

```txt
What is the 'UTC'?:
>> Coordinated Universal Time is the time used as the standard for international standard time.
>> For example, UTC 02:00 is 11:00 am in Korean standard.
>> In other words, Korean clocks are nine hours ahead of Coordinated Universal Time.
```

![Image](https://github.com/user-attachments/assets/91bb3e78-38d0-4283-abea-010bed7f9478)

## _12. Print Your Memory Status_

![Image](https://github.com/user-attachments/assets/cf234331-4a29-447c-ba1e-6c8a3d4cb5f0)

## _13. Print Swap_

```txt
What is the 'SWAP'?:
>> An area that helps you continue working by utilizing some space on the HDD when system memory is insufficient
```

![Image](https://github.com/user-attachments/assets/6cc2da8e-e947-4912-9e19-a9b3ebe2ff0d)

```txt
swap -a: /etc/fstab 파일을 참고하여, Swap 영역 활성화.
swap -p: Swap 영역을 활성화 할 때, 우선순위 지정.
swap -s: 활성화된 Swap 영역의 정보를 출력.
swapon/swapoff: 스왑 영역 활성화 / 해제.
free: 전체 물리메모리의 사이즈 및 사용량, Swap 영역의 사용량 등을 출력.
free -h: 사용자가 읽기 쉽게, 단위로 출력.
```

## _14. ETC_

```txt
What is the 'GCC'?:
>> You can use C language through the editor.
```

![Image](https://github.com/user-attachments/assets/16a3ef2d-47ac-4cb5-8dac-77d26d4e7959)
![Image](https://github.com/user-attachments/assets/d2689fa3-4e84-45a0-b316-a397f7718c55)






