---
title: '[C] 프로그래밍 기초 중간시험 M04'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M04'
thumbnail: './image/programmingBasics.png'
---
하나의 정수를 입력으로 받아서 아래의 예제와 같이 출력하는 프로그램을 작성하라. (규칙을 찾고, 그 규칙대로 출력하도록 한다.)

예를 들어, 4를 입력으로 받았다면 아래와 같이 출력한다.

```
DCBA
CBA
BA
A
AB
ABC
ABCD
```

## 입력
입력 데이터는 표준입력을 사용한다. 입력의 첫 줄에는 출력될 줄의 수를 나타내는 하나의 정수가 주어진다. 

단, 정수는 1 이상 26 이하의 수이다.

## 출력
출력은 표준출력을 사용한다. 입력된 정수에 대해 위의 예와 같이 알파벳을 출력한다.


## 입출력의 예

|입력|출력|
|---|---|
|6|FEDCBA<br>EDCBA<br>DCBA<br>CBA<br>BA<br>A<br>AB<br>ABC<br>ABCD<br>ABCDE<br>ABCDEF|
|1|A|

## 소스
```c
#include <stdio.h>

int main()
{
	int input;

	scanf("%d", &input);

    for(int i = 1; i <= input ; i++)
    {
    	for (int j = input-i; j >= 0; j--)
    	{
    		printf("%c", 65+j);
		}

        printf("\n");
    }
	
	for(int i = 1; i < input; i++)
    {
        for (int j = 0; j <= i; j++)
        {
        	printf("%c", 65+j);
		}

        printf("\n");
    }

	return 0;
}
```