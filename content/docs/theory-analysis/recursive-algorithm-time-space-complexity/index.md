---
title: 재귀 알고리즘 시간/공간 복잡도
---

재귀 알고리즘의 시간복잡도, 공간복잡도 계산법을 정리한다.

## 1. 재귀 알고리즘 시간 복잡도/공간 복잡도

### 1.1. Factorial

``` {caption="[Function 1] Factorial"}
f(0) = 1
f(n) = n * f(n - 1)
```

``` {caption="[Explanation 1] Factorial 시간 복잡도"}
T(n) = T(n - 1) + 1C
     = T(n - 2) + 2C
     = T(0) + nC
     = 1 + nC
     = O(n)
```

* 시간 복잡도
  * O(n)
  * 함수 호출이 n번 발생하고 함수 내부적으로는 곱셈 연산을 제외한 별도의 연산이 수행되지 않기 때문에, 대략적으로 O(n)의 시간 복잡도를 갖는다는 것을 추정할 수 있다.
* 공간 복잡도
  * O(n)
  * 함수 호출이 n번 발생하고 함수 내부적으로도 함수 호출을 위한 Memory 사용량 이외에 별도의 Memory를  이용하지 않기 때문에, 대략적으로 O(n)의 공간 복잡도를 갖는다는 것을 추정할 수 있다.

### 1.2. 피보나치 수열


``` {caption="[Function 2] 피보나치 수열"}
f(0) = 1
f(1) = 1
f(n) = f(n - 1) + f(n - 2)
```

## 2. 참조

* [https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=wns7756&logNo=221568348621](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=wns7756&logNo=221568348621)
* [https://justicehui.github.io/easy-algorithm/2018/03/11/TimeComplexity4/](https://justicehui.github.io/easy-algorithm/2018/03/11/TimeComplexity4/)