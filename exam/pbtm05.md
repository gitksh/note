---
title: '[C] 프로그래밍 기초 중간시험 M05'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M05'
thumbnail: './image/programmingBasics.png'
---
하나의 문자열(단어)를 입력으로 받아서 문자열 길이의 줄 수만큼, 첫번째 문자는 한번, 두번째 문자는 두 번, k번째 문자는 k번을 출력하는 프로그램을 작성하라.

## 입력
입력 데이터는 표준입력을 사용한다. 입력의 첫 줄에는 하나의 문자열이 주어진다. 

단, 입력되는 문자열의 길이는 1 이상 100 이하이다.

## 출력
출력은 표준출력을 사용한다. 입력으로 받은 문자열을 문자의 순서의 횟수만큼 출력한다.


## 입출력의 예

|입력|출력|
|---|---|
|Hello|H<br>ee<br>lll<br>llll<br>ooooo|
|ComPuteR|C<br>oo<br>mmm<br>PPPP<br>uuuuu<br>tttttt<br>eeeeeee<br>RRRRRRRR|

## 소스
```c
#include <stdio.h>
#include <string.h>

int main()
{
	char text[101];
	
	scanf("%s", text);
	
	for (int i = 0; i < strlen(text); i++)
	{
		for (int j = 0; j <= i; j++){
			printf("%c", text[i]);
		}
		printf("\n");
	}

	return 0;
}
```