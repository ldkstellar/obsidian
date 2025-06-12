final 키워드로 클래스 상속을 막을 수 있다.
```cpp
class Animal final{

};

class Dog :public Animal {}// 에러
```

물론 메소드도 가능하다.
##### 결론
- 클래스나 가상함수를 파생클래스에서 오버라이딩 못 하도록 하려면 final keyword를 사용한다.
- 컴파일 도중에 확인한다. 
- 당연히 가상 함수가 아니면 쓸 수 없다.(부모클래스에서 사용하기 때문) 