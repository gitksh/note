---
title: '[C] 프로그래밍 기초 중간시험 M01'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M01'
thumbnail: './image/programmingBasics.png'
---
네 개의 실수 a, b, c, d를 입력으로 받아서, 다음의 수식을 계산하는 프로그램을 작성하라.

$$
\frac{a \times b - c \times d}{a - b \times c - d}
$$

## 입력
입력 데이터는 표준입력을 사용한다. 입력의 첫 줄에는 네 개의 실수 a, b, c, d가 주어진다.

단 1.0 ≤ a, b, c, d ≤ 1000.0이다.

## 출력
출력은 표준출력을 사용한다. 계산 결과를 하나의 줄에 소수점 이하 두 자리까지 출력한다.


## 입출력의 예

|입력|출력|
|---|---|
|1.0 2.0 3.0 4.0|1.11|
|4.0 20.3 15.0 2.11|-0.16|

## 소스
```c
#include <stdio.h>

int main()
{
	double a, b, c, d, result;
	
	scanf("%lf %lf %lf %lf", &a, &b, &c, &d);
	
	result = ((a * b) - (c * d))/((a - (b * c) - d));
	
	printf("%.2lf", result);
	
	return 0;
}
```