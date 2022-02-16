---
title: '[C] 프로그래밍 기초 중간시험 M10'
date: '2020-10-21'
category: 'Exam'
summary: '프로그래밍 기초 중간시험 M10'
thumbnail: './image/programmingBasics.png'
---
인터넷 쇼핑몰 총각네 야채가게에서는 아티초크(artichokes)를 100g당 3,500원에, 비트(beets)는 100g당 1,250원에, 당근(carrots)은 100g당 1,150원에, 더덕(deodeok)은 100g당 2,700원에, 가지(eggplant)는 100g당 990원에 판매한다.

배송비는 600g미만인 경우는 3,500원이고, 600g이상 2Kg미만인 경우는 기본 3,500원에 100g당 550원, 2Kg이상인 경우는 기본 15,000원에 100g당 700원이다.

예를 들어, 무게가 400g이면 배송비는 3,500원이고, 무게가 1.2Kg인 경우에는 배송비가 3500+12\*550원=10,100원이며, 무게가 2.2Kg인 경우에는 배송비가 15000+22\*700=30,400원이다.

배송비 포함하여 총 금액이 25,000원 이상 35,000원미만 이면 총 금액에서 5%할인을 해주고, 총 금액이 35,000원 이상이면 총 금액에서 10%를 할인해준다.

구매자로부터 물건을 주문받아 총 구매금액, 배송비, 할인금액, 그리고 청구금액을 구하는 프로그램을 작성하라.

예를 들어, 한 구매자가 더덕만 1.2Kg을 주문하였다면, 총 구매금액은 32,400원이고, 배송비는 10,100원이다. 

배송비 포함 금액이 42,500원이므로 10% 할인금액은 4,250원이고, 실제 청구금액은 38,250원이된다.

## 입력
입력 데이터는 표준입력을 사용한다.

입력의 첫 줄에 구매하는 물품의 수를 나타내는 하나의 정수 n이 주어진다.

n은 1 이상 20 이하의 정수이다. 둘째 줄부터 n개의 줄에는 한 줄에 하나씩 구매 내용이 주어진다.

구매 내용을 나타내는 하나의 줄에는 구입하려고 하는 물품의 종류를 나타내는 하나의 문자와 구입 양(100g 단위)을 나타내는 무게가 정수로 주어진다.

물품의 종류에서 문자 a는 아티초크, 문자 b는 비트, 문자 c는 당근, 문자 d는 더덕, 문자 e는 가지를 나타낸다.

## 출력
출력은 표준출력을 사용한다. 출력의 첫째 줄에 총 구매금액, 배송비, 할인금액, 그리고 청구금액을 정수로 출력한다.


## 입출력의 예

|입력|출력|
|---|---|
|1<br>d 12|32400 10100 4250 38250|
|5<br>a 1<br>b 1<br>c 1<br>d 1<br>e 1|9590 3500 0 13090|
|10<br>d 1<br>c 2<br>b 1<br>c 2<br>e 2<br>b 1<br>d 2<br>d 1<br>d 2<br>a 1|28780 11750 4053 36477|

## 소스
```c
#include <stdio.h>

int main(void) {
    int times;
    char vegetable[2];
    long long count, weight, price, delivery, discount, result;
    long long a = 0, b = 0, c = 0, d = 0, e = 0;

    scanf("%d", &times);

    for(int i=0; i<times; i++)
    {
        scanf("%s %lld", vegetable, &count);
    
        switch (vegetable[0]) {
            case 'a':
                a += count;
                break;

            case 'b':
                b += count;
                break;

            case 'c':
                c += count;
                break;

			case 'd':
                d += count;
                break;

			case 'e':
                e += count;
                break;
        }
    }

    price = a * 3500 + b * 1250 + c * 1150 + d * 2700 + e * 990;
    weight = a + b + c + d + e;

    if (weight < 6) delivery = 3500;
    else if (weight < 20) delivery = 3500 + weight * 550;
    else delivery = 15000 + weight * 700;

	result = price + delivery;
	
	if (result < 25000) discount = 0;
	else if (result < 35000) discount = result / 20;
	else discount = result / 10;

	result -= discount;

    printf("%lld %lld %lld %lld", price, delivery, discount, result);

    return 0;
}
```