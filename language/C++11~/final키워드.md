final 키워드로 클래스 상속을 막을 수 있다.
```cpp
class Animal final{

};

class Dog :public Animal {}// 에러
```
