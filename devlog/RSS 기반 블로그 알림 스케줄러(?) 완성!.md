# RSS 기반 블로그 알림 스케줄러(?) 완성!

![](https://postfiles.pstatic.net/MjAyNTA3MjlfMjM1/MDAxNzUzNzY2NTgxNzM3.cNCnTXIGfMktaoY1hPnVEBx4oyh2qpz_qFYkBFtAlc8g.CnVebMiu_SdndvrPneRUTC7rVEFhCcUmW2AtAp4hLdEg.PNG/image.png?type=w773)

팔로잉하고 있는 블로거가 새 글을 올릴 때 알림을 받을 수 있는 워크플로우를 완성했다. n8n으로 만들었는데 코딩하는 것에 비해 시각적으로 플로우를 볼 수 있기에 편한 것은 사실이지만 알아야 할 노드가 생각보다 많아서 처음 사용해 보면 다루는 게 쉽지만은 않다. 그래도 많은 Redis, Postgresql 같은 개발할 때 많이 사용하는 툴들을 다양하게 지원하기에 만족스럽다. 원래는 SaaS 기반 클라우드로 사용하고 싶었으나 한 달에 24달러나 해서, 그냥 물리 서버 하나를 구매해서 구축했다. (만족쓰 ㅎㅎ)

​

RSS Trigger 노드로 해결할 수 있는 블로그들은 Trigger로 주기적으로 추적하면 되지만, Rss Trigger를 봇으로 인식하고 RSS 정보를 내어주지 않는 나쁜(?) 블로그들이 다수 있어서 이런 친구들 같은 경우 개별적으로 추적해 줘야 했다. 그래서 Rss Read 노드로 Rss 값을 읽고 최신 데이터를 Redis의 SortedSet으로 관리하고 주기적으로 SortedSet과 비교해서 SortedSet에 없는 게시글이면 텔레그램으로 알림을 보내주는 방식으로 처리했다.

![](https://postfiles.pstatic.net/MjAyNTA3MjlfMjQ3/MDAxNzUzNzY2NTk1MzM5.T3Jigc50VMW6yEppIqKs_sG-Kg0wP0QEEcOjXPNAh6Ag.7zgnVDZQi8gEng--G8i11iy6P9yApX8Jl-wcA2_6yD8g.PNG/image.png?type=w773)

​

![](https://postfiles.pstatic.net/MjAyNTA3MjlfMjUx/MDAxNzUzNzY2NzMxMDQw.-q9ZVEAiYC1WFvN24ZK9bTeo2HDcwsqc3I8MvrguVxMg.0nXkaKgVDTF4mvGCZo95V4L2BvKz_mi-SJ5_QAGOXosg.PNG/image.png?type=w773)

(예전만 해도 Redis에 저장된 데이터 보는 방법을 몰라서 고통받았는데 세상 참 좋아졌다. 역시 많이 알아야 한다)

