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

<br>
<br>

## 2. find()와 substr()를 이용해 구분자로 문자열 자르기

- find() 정의
: string::find Syntax
```c++
size_t find(const string& str, size_t pos=0) const;
size_t find (const char* s, size_t pos = 0) const;
buffer (3)	
size_t find (const char* s, size_t pos, size_t n) const;
character (4)	
size_t find (char c, size_t pos = 0) const;

```
>첫번째 인자로 seperator를 받고, 검사를 시작할 위치를 두번째 인자로 받는다. 리턴값은 구분자 이전 위치를 리턴한다.

-substr() 정의
: 1번에서 다루었으므로 넘어간다.


<br/>

```c++
std::string str="hello world, c++";
std::string seperator=",";
int cur_position=0;
int position;
while((position=string.find(seperator,cur_position))!=string::npos){
    int len=position-cur_position;
    string result=string.substr(cur_position,len);
    std::cout<<result<<"\n";
    cur_position=position+1;
}
cout<<string.substr(cur_position);
```

<br/>
output:

> hello <br/>
> world<br/>
> c++ 

<br/>
- 현재위치에서 구분자를 찾으면 구분자 이전 위치 값을 리턴받도록 하고, npos를 만나면 종료되는 원리.


<br></br>