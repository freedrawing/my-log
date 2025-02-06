# Git commit message template

✨ :sparkles: 새로운 기능 추가, 구현 | ✨feat : Introduce new features
🐛 :bug: 버그 수정 | 🐛 fix : Fix a bug
🚑 :ambulance: 긴급 수정 | 🚑 fix : Critical hotfix
🔒 :lock: 보안 이슈 수정 | 🔒 fix : Fix security issues
🔥 :fire: 삭제(파일, 코드) | 🔥 remove : Remove code or files
🚛 :truck: 파일, 경로, route를 옮기거나 이름 변경 | 🚛 update : Move or rename resources
📝 :memo: 문서 파일 추가/수정 | 📝 update : Add or update documentation
💡 :bulb: 주석 추가/수정 | 💡 update : Add or update comments in source code
🧹 :broom: 단순오타 수정, 잡동사니 처리 | 🧹 chore : Modify typo
⚡ :zap: 성능 개선 | ⚡ perf : Improve performance
🎨 :art: 코드 구조/형태 개선 | 🎨 perf : Improve structure / format of the code
♻️ :recycle: 코드 리팩토링 | ♻️ refactor : Refactor code
👽 :alien: 외부 API 변화로 인한 수정 | 👽 update : Update code due to external API changes
🗃️ :card_file_box: 데이터베이스 관련 수정 | 🗃️ update : Perform database related changes
🙈 :see-no-evil: gitignore 추가/수정 | 🙈 update : Add or update a .gitignore file

---

# 질문

---

# 해야 할 것

* github action으로 test할 때, 어떤 테스트 메서드가 실행되었는지, 그리고 해당 테스트가 성공했는지 실패했는지 로그로 알 수 없을까.
* API가 만들어져 있지 않은 URL로 호출시 기본적으로 토큰 검사를 한다. 이런 경우, 잘못된 요청이라는 예외가 더 적절할 것 같다.
* 엘라스틱 서치도 적용할 수 있을까? 그전에 엘라스틱 서치란 무엇인가?
* B+tree와 B-tree의 차이점은 뭘까?
	* B+tree에서 'Like%'는 인덱스 사용이 가능하지만, '%Like'는 사용이 불가하다는 건 과연 무슨 의미?
* CDN 해보기.
* README
	* 아키텍쳐 구조 명시
	* Trouble Shooting
	* Ngrinder 
		* 성능 개선이 드라마틱하지 않아도 된다.
	* 테스트 코드나 이런 거 시각적인 자료
* v2 API like 성능 향상을 해보자.
* RediSearch
	* HashOpertations<K, HK, HV> <- 왜 반드시 String으로 Serialize해야만 데이터가 들어갈까. 이상하네... Config에서 Jackson으로 설정해줘서 괜찮을 줄 알았는데....
* 로컬 캐시는 어떻게 확인하지? 캐시 메트릭?
* @Cacheable top=100 넘기는 로직 마음에 안 듦.
* @Cacheable viewCount 해결해야 함
* @Transactional(readOnly = true) -> @Transactional(propagation = Propagation.REQUIRES_NEW) 갈 수 있는 방법은 없나...
* 랭킹 시스템 동시성 이슈에 대해 생각해보자. -> 캐시 메모리에서는 동시성 발생 이슈가 없을까?
* Message-Queue 방식으로 생각
* 

---
# Keyword
spring cloud vault
하쉬코프(HashiCorp) - vault
스프링-stop

아파치 - 제이미터 -> 동시성 제어 툴
NGrinder 

동시성
* 하나의 데이터를 가지고 여러 스레드에서 동시다발적으로 접근했을 때, 최신 데이터와 현재 데이터의 싱크가 맞지 않아서 발생하는 문제.
	* 낙관적 락
	* 비관적 락
	* 분산 락
* 동시성 제어는 만능이 아니다.
* 동시성이 종종 발생했을 때와 매일 발생했을 때 걸어야 하는 락이 다르다.
* 함수형 분산락 공부

인덱스
* 인덱스를 걸려면 어디에 걸어야 하는가.
* 인덱스는 만능인가? 인덱스에 단점이 있으면 어떤 상황에서만 인덱스를 사용해야 하는가
* 복합 인덱스는 한 개 이상의 컬럼을 엮어서 인덱스를 거는 건데, 복합 인덱스를 걸 때, 순서에 따라서는 어떻게 동작을 하는가
* 시간 차이 검증
* 복합 인덱스는 무조건 타는가?
* 인덱스 자료구조도 알아야 한다.
* 인덱스 분포도 <- 검색

쿼리 튜닝
* 스트레이트 조인
* 조인을 5개 한다고 하면, 조인 순서에 따라 성능이 달라진다.

캐싱
* 캐싱 전략
* Spring Cache
* Redis Cache
* 스프링 캐시가 더 빠를까?
* 레디스 캐시도 쥬디스와 레튜스가 있는데 레튜스만 캐시 매니저가 있음.
	* CrudRepository는 잘 사용하지 않음.
	* RedisTemplate이 권장됨.
	* RediSearch
	* CacheManager -> @Cacheable
	* RedisTemplate을 사용했을 때와 @Cacheable을 사용했을 때의 차이
* 로컬 캐시를 사용했을 때 문제
* 'RediSearch'보다는 ElasticSearch 사용할 것
* 레디스에 데이터를 Write할 때도 Transaction 처리를 해야 할까?
* Scan 명령어로는 필터링이 안 되는가? Scan 명령어를 조금 더 자세히 알아보자.

배포
* 롤링, 까나리, 블루그린


---
일반 리스트로 인기 쇼핑몰을 처리하니 `@Cacheable` 을 사용할 수 있으나 리스트 단위로 처리를 하다보니까, `@CachePut`이나 `@CacheEvict`은 사용하기가 쉽지 않다. 또한, 순위 변동이 있을 때도 업데이트를 하려면 리스트 타입이라 엘리먼트 하나하나를 옮겨야 하기에 불편함이 있다. 그렇기에 엘리먼트를 전부 옮기려면 `O(N)`만큼 시간이 걸린다.

이 문제를 @SortedSet으로 해결해보자.














































































































