# 킹왕짱 n8n workflow 자동화하기
일상의 반복적인 일을 조금씩이라도 자동화하기 위해 서버 하나를 구입했다. 요즘은 클라우드 시대라 굳이 물리 서버를 구입할 필요는 없으나 클라우드는 저렴하지 않다. 더군다나 요즘은 중국제(?) 미니 PC는 15만 원 내외면 살 수 있기에 중국제인 게 불안하지만 가난한 취준생인 만큼 거금을 들여 서버를 구입했다. Windows가 기본으로 탑재되어 있지만 중국이라 불안하니 다 밀어버리고 우분투로 바꿔버렸다. 환경 구축이 제일 귀찮은 나였지만 이건 이것 나름대로 또 재미있다. OS를 설치하고, 네트워크 설정을 하기 위해 UTP선도 오랜만에 직접 만들어보고... 포트포워딩도 하고, Https도 입혀보고... 크고 작은 시행착오가 있었지만 네트워크 전반에 대해서 공부할 수 있어 좋았다.
​

![](https://postfiles.pstatic.net/MjAyNTA3MjlfNDYg/MDAxNzUzNzE3MzU4NzI4.Md1KgCaV-SYwZxKdSEYA0Y1du8b9v9Fs2peY-U4YWWQg.ShM_qfUgbwAEeRPN9Jf-xHIzQrJIFgJlU8mR1sqReL8g.JPEG/20250729_004101.jpg?type=w773)

(매우 조그만 귀염둥이 서버)


서버의 주된 목적은 일상의 자잘한 일을 자동화하는 것이다. 이를테면, 나는 다른 사람의 블로그에 들어가 그들이 쓴 글 읽는 걸 좋아하는데 매번 새로운 글이 발행됐는지 확인하는 건 여간 시간 낭비가 아닐 수 없다. 그렇기에 글이 발행됐을 때 이메일이나 텔레그램 등으로 알림을 보내줄 수 있는 시스템이 있으면 참 좋겠다는 생각을 오래전부터 했다. RSS를 활용한 Notifier가 있겠지만 커스터마이징이 중요하니 직접 만들어 보려고 한다. 특히나 요즘은 n8n 같은 워크플로우 자동화 도구 등이 매우 잘 되어 있어서 이 툴을 활용하면 코딩은 최소화하면서 빠른 시간 내에 완성할 수 있으리라 생각된다. 이 밖에도 환율 추적 시스템 등 여러 미니 서비스를 만들어 내 시간을 줄이려고 한다.
​

앞으로 천천히 자동화 과정을 올려보겠다 ㅋㅋㅋ

![](https://postfiles.pstatic.net/MjAyNTA3MjlfMTUz/MDAxNzUzNzE3NDQzNTEx.y9ZTnHfsTxPtJmJ8lbhGdvkTxM9Tp6S1TSPL-k3uS3wg.lwMHTng3dUmX8UT5UcmFK76cGXFvCp3JbYzxFsNIaHwg.PNG/image.png?type=w773)

(n8n으로 블로그 구독 알림 만들어 보고 있음. RSS Trigger로 가능한 블로그도 있지만 티스토리 같은 경우는 봇이 RSS에 접근하는 걸 허용하지 않아서 직접 워크플로우를 만들어서 관리해야 한다. 귀찮지만 나름 재미있다)