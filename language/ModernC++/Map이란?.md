key값으로 찾는거 매핑

- 키와 값의 쌍들을 저장
- 키는 중복될 수 없음
- c++ 맵은 자동 정렬되는 컨테이너 키기준
- 이진 탐색트리 기반
	- 오름차순
##### std::pair<key,value>
- 두 데이터를 한 단위로 저장하는 구조

##### insert()
```cpp
simpleScoreMap.insert(std::pair<std::string, int>("Mocha", 100));
```
- **새요소**를 map에 삽입한다
- 반복자와 bool값을 한쌍으로 반환
	-  반복자는 요소를 가리키고
	-  bool 값은 삽입 결과를 알려줌
- 키를 중복으로 삽입할 수 없음

##### operator[]
mapped_type& operator[] (const Key& key)
- key에 대응하는 값을 참조로 반환한다.
- map에 키가 없으면 새요소를 삽입
- map에 키가 있으면 그 값을 덮어씀

##### find()
iterator find(const key& key);
- map에서 key를 찾으면 그에 대응하는 값을 가리키는 반복자를 반환
- 못 찾으면 end()를 반환

##### swap(), clear()
void swap(map& other);
- 두 map의 키와 값을 서로 맞바꾼다.
void clear();
- map을 비운다.

##### erase()
한개의 key값의 값을 삭제

![[Pasted image 20250519123319.png]]
![[Pasted image 20250519123440.png]]
남이만든 구조체를 활용하는 방법