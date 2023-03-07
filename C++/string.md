# 문자열 자르는 방법
## 1. substr()로 문자열 자르기

- 인덱스, 길이 이용하는 방법
substring Syntax
```c++
string substr(size_t pos, size_t len) 
```
인자로 index와 길이를 받고 index부터 원하는 길이만큼 자른다음, 해당 string을 리턴한다.

<br/>

```c++
std::string str="hello world, c++";
std::string newstr1=str.substr(0,5);
std::string newstr2=str.substr(6,5);
std::string newstr3=str.substr(13,3);
```

<br/>
output:

> hello <br/>
> world<br/>
> c++ 

<br/>
- 매개변수
vector 첫번째 요소를 가리키는 반복자(v.begin())와 처음에 삽입하고자 하는 요소(target)를 작성한다.


<br></br>

- 인덱스만 사용하는 방법

```c++
std::string str="hello world, c++";
std::string newstr1=str.substr(6);
std::string newstr2=str.substr(13);
```

<br/>
output:

> world, c++ <br/>
> c++<br/>

- 각각 해당 인덱스부터 문자열 끝까지를 리턴한다.
