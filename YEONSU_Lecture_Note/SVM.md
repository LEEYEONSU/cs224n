## Support Vector Machine 

이 글은 ratsgo's blog를 참고하여 정리했음을 밝힙니다.

> **margin**

￼￼￼<img src="/Users/yeonsulee/Library/Application Support/typora-user-images/image-20191001191445542.png" alt="image-20191001191445542" style="zoom:50%;" />

두 범주를 나누는 classification 문제라고 할때 $b_{12}$ 와 $b_{11}$ 사이의 margin을 크게 만들어 주어야 한다.

SVM(Support Vector Machine)은 이 margin을 최대화하는 경계면을 찾는 기법이다. 

<img src="/Users/yeonsulee/Library/Application Support/typora-user-images/image-20191001192053091.png" alt="image-20191001192053091" style="zoom: 33%;" />

 위의 그림에서 분류 경계면을 $w^Tx + b$ 라고 했을 때, 벡터 $w$느ㄴ 이 경계면과 수직인 법선벡터가 된다. 

$x^+ = x^- + \lambda w$ 라고 했을 때, $\lambda$를 유도 해볼 수 있다.

<img src="/Users/yeonsulee/Library/Application Support/typora-user-images/image-20191001192906606.png" alt="image-20191001192906606" style="zoom:50%;" />

>  **margin의 거리 구하기** 

​											<img src="/Users/yeonsulee/Library/Application Support/typora-user-images/image-20191001193403160.png" alt="image-20191001193403160" style="zoom: 33%;" />

> **라그랑지안 문제로 변환**

- 라그랑지안 승수법(Langrange multiplier method) 제약식에 형식적인 라그랑지안 승수를 곱한 항을 최적화하려는 목적식에 더하여, 제약된 문제를 제약이 없는 문제로 바꾸는 기법이다. 
- 이 방법은 어떠한 문제의 최적점을 찾는 것이 아니라, 최적점이 되기 위한 조건을 찾는 방법이다. 
  - 최적해의 필요조건을 찾는 방법이다.

< 증명하는 부분 업데이트해야함>













> **support vectors를 찾기 위해서 두가지 조건 중 하나가 만족하면 된다.**

 	$(1) \alpha_i = 0$

​	 $	(2)y_i(w^Tx_i + b)-1 = 0$



<img src="/Users/yeonsulee/Library/Application Support/typora-user-images/image-20191001204819102.png" alt="image-20191001204819102" style="zoom: 50%;" />