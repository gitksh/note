---
title: '[C] 프로그래밍 기초 중간시험 M02'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M02'
thumbnail: './image/programmingBasics.png'
---
옛날 한국에서 사용하던 무게의 단위는 돈(don), 냥(nyang), 근(geun), 관(gwan) 이었다. 1냥은 10돈이고, 1근은 16냥, 1관은 100냥이다. 1근은 600g이다.

돈(don) 단위의 무게를 하나의 정수로 입력받아서, 이것을 냥, 근, 관, Kg로 환산하여 출력하는 프로그램을 작성하라.

## 입력
입력 데이터는 표준입력을 사용한다. 돈(don) 단위의 부피를 나타내는 x가 하나의 정수로 주어진다.

단, 0 ≤ x ≤ 100,000 이다.

## 출력
출력은 표준출력을 사용한다. 

첫째 줄에 입력된 돈(don)값에 해당하는 냥(nyang), 근(geun), 관(gwan), 킬로그램(Kg) 값들을 출력한다. 

출력 방식은 아래의 출력 예제와 똑같이 하며, 돈(don)은 정수로 출력하고, 냥(nyang), 근(geun), 관(gwan), 킬로그램(Kg)은 소수점 이하는 4번째 자리까지 출력한다. 

단, 소수점 이하 셋째 자리까지 맞는 경우 정답으로 인정한다.


## 입출력의 예

|입력|출력|
|---|---|
|2|2 dons are equivalent to each of the following:<br>0.2000 nyang<br>0.0125 geun<br>0.0020 gwan<br>0.0075 Kg|
|1000|1000 dons are equivalent to each of the following:<br>100.0000 nyang<br>6.2500 geun<br>1.0000 gwan<br>3.7500 Kg|

## 소스
```c
#include <stdio.h>

int main()
{
	
	int dons;
	double nyang, geun, gwan, kg;
	
	scanf("%d", &dons);
	
	nyang = dons / 10.0;
	geun = nyang / 16.0;
	gwan = nyang / 100.0;
	kg = geun * 0.6;
	
	printf("%d dons are equivalent to each of the following:\n", dons);
	printf("%.4lf nyang\n", nyang);
	printf("%.4lf geun\n", geun);
	printf("%.4lf gwan\n", gwan);
	printf("%.4lf Kg", kg);
	
	return 0;
}
```