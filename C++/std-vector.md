# vector 시작 부분에 요소 삽입 방법
## 1. std::vector::insert 기능


```c++
std::vector<int> v={...};
v.insert(v.begin(), target);
```
<br/>
- 매개변수
vector 첫번째 요소를 가리키는 반복자(v.begin())와 처음에 삽입하고자 하는 요소(target)를 작성한다.

