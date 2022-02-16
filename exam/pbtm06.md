---
title: '[C] 프로그래밍 기초 중간시험 M06'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M06'
thumbnail: './image/programmingBasics.png'
---
항의 수 n을 입력으로 받아서 다음의 무한 수열의 값을 구하는 프로그램을 작성하라.

$$
S = \frac{1^2}{2\cdot3} + \frac{3^2}{3\cdot4} + \frac{5^2}{4\cdot5} + \frac{7^2}{5\cdot6} + \cdot\cdot\cdot
$$

예를 들어, n=3인 경우 세번째까지 항의 합을 소수점 다섯째자리까지 구하면 다음과 같다.

$$
S = \frac{1^2}{2\cdot3} + \frac{3^2}{3\cdot4} + \frac{5^2}{4\cdot5} = \frac{1}{6} + \frac{9}{12} + \frac{25}{20} = 2.16667
$$

n의 값은 반복적으로 주어지며, 더 이상 입력이 없을 때까지 합을 계속적으로 구한다.

## 입력
입력 데이터는 표준입력을 사용한다. 입력의 각 줄에는 항의 수를 나타내는 하나의 정수 n 이 주어진다. 

단 1 ≤ n ≤ 1,000이다.

## 출력
출력은 표준출력을 사용한다. 

무한수열의 값을 소수점이하 5 자리까지 출력한다. (채점은 소수점 이하 3 자리까지 맞으면 정답으로 간주한다.)


## 입출력의 예

|입력|출력|
|---|---|
|1<br>3<br>10|0.16667<br>2.16667<br>18.09863|
|55|174.27789|
|5<br>123<br>11<br>7|5.72857<br>433.87561<br>20.92555<br>10.23651|

## 소스
```c
#include <stdio.h>
#include <math.h>

int main()
{
	int input, a;
	double result = 0;
	
	while(scanf("%d", &input) == 1)
	{
		a = 1;
		for(int i = 1; i<input+1; i++)
		{
			result += (double) (a*a)/((i+1)*(i+2));
			a += 2;
		}
		printf("%.5lf\n", result);
		result = 0;
	}

	return 0;
}
```