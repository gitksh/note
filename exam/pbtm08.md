---
title: '[C] 프로그래밍 기초 중간시험 M08'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M08'
thumbnail: './image/programmingBasics.png'
---
입력 데이터중에서 #문자를 처음 만날 때까지, 연속된 문자열 "**cat**" 혹은 "**dog**" 이 나타난
횟수를 구하는 프로그램을 작성하라. 

**\#** 문자는 줄 가운데 있을 수도 있으며 **\#** 다음에도 다른 문자들이 있을 수도 있다. 

단, 대소문자를 구분하여 소문자로만된 문자열만 찾는다.

## 입력
입력 데이터는 표준입력을 사용한다.

문자열이 여러 줄에 걸쳐서 입력된다.

입력에서 처음 나오는 **\#** 까지만 읽는다.

## 출력
출력은 표준출력을 사용한다.

출력의 첫째 줄에 연속된 문자열 "**cat**" 혹은 "**dog**" 이 나타난 횟수의 합을 출력한다.


## 입출력의 예

|입력|출력|
|---|---|
|One man, though, knows what your pet is<br>thinking — or thinks he does. Etsy artist<br>Christopher Rozzi's paintings of cats and<br>dogs each come with a witty caption that<br>deciphers what may very well be going through<br>your pet's mind at any moment.#|2|
|Cat & Dog is the fourth track of the album<br>The Dream Chapter: STAR by South Korean boy<br>group TXT.<br>It was released on March 4, 2019.<br>!! # dog cat|0|
|Cat & Dog is the fourth track of the album<br>dododogog cacacatat The Dream Chapter: STAR<br>by South Korean boy group TXT.<br>It was released on March 4, 2019.<br>!! #|2|

## 소스
```c
#include <stdio.h>

int main()
{
    int count = 0, check1 = 0, check2 = 0;
	char input, prev = ' ';

    while((input = getchar()) != '#')
    {
        if (input == 'a' && prev == 'c'){
        	check1 = 1;
		} else if (input == 't' && prev == 'a' && check1 == 1){
			count++;
			check1 = 0;
		} else check1 = 0;
				
		if (input == 'o' && prev == 'd'){
        	check2 = 1;
		} else if (input == 'g' && prev == 'o' && check2 == 1){
			count++;
			check2 = 0;
		} else check2 = 0;
		
		prev = input;
    }

    printf("%d", count);
    
	return 0;
}
```