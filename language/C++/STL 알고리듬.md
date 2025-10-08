- 요소 범위에서 쓸 수 있는 함수들
	- 처음, 마지막
- 배열 또는 몇몇 STL 컨테이너에 쓸 수 있음
- 반복자를 통해 컨테이너에 접근 
- 컨테이너의 크기를 변경하지 않음 (따라서 추가 메모리 할당도 없음)

##### STL 알고리듬 유형

algorithm
- 변경 불가 순차(sequence)연산
		find ,foreach
- 변경 가능 순차 연산
	copy(),swap
- 정렬 관련 연산
	sort(),merge()
	
numeric
- 범용 수치 연산
		accumulate() 

#### sort 알고리즘 
 - 비교 함수 형태: bool compare()
 - 반환 값의 의미 차
