# 거듭해서 곱하고 제곱근으로 만드는 방법
## 1. 거듭제곱 구하기

- pow 이용
pow(base,n)
:base를 n제곱하는 결과를 리턴한다.
<br>
*for-loop를 이용해서 푸는 것이 좋은데, 이유는 double 범위 넘어갈 경우 pow함수 결과값과 for문으로 직접 구해준 결과값이 달라지기 때문.
=>따라서 왠만하면 for-loop구문 이용
<br>

## 2. 제곱근 구하기

- sqrt 이용
sqrt(target)
:target에 대해 제곱근을 구해주는 함수