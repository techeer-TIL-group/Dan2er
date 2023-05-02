# 메모리 동적할당

## 1. 실습문제 위주의 공부.

```c
#include<stdio.h>

int main(){

int N;
	scanf("%d", &N);
	int *x = NULL;
	x = (int *)malloc(sizeof(int) * N); 
	int sum = 0;
	for (int i = 0; i < N; i++) {
		scanf("%d", &x[i]);
		sum = sum + x[i];
	}
	printf("%d", sum);

	return 0;
}

//2
#include<stdio.h>

int main(){

	int N;
	scanf("%d", &N);
	float *x = NULL;
	x = (float *)malloc(sizeof(float) * N); 
	scanf("%f", &x[0]);
	float max = x[0];
	if (N != 1) {
		for (int i = 1; i < N; i++) {
			scanf("%f", &x[i]);
			if (x[i] > max) {
				max = x[i];
			}
		}
	}
	if (N == 1) {
		max = x[0];
	}
	printf("%.2f", max);

	return 0;
}

//3
#include<stdio.h>

int main(){

int N;
	scanf("%d", &N); 
	getchar();
	char *x = NULL;
	x = (char *)malloc(sizeof(char) * (N+1)); 
	for (int i = 0; i < N; i++) {
		scanf("%c", &x[i]);
	}
	getchar();
	char a, b;
	int cnt1 = 0;
	int cnt = 0;
	scanf("%c %c", &a, &b);
	for (int i = 0; i < N; i++) {
		if (x[i] == a) {
			cnt++;
		}
		if (x[i] == b) {
			cnt1++;
		}
	}
	printf("%d %d", cnt, cnt1);

	return 0;
}
```

주로 구조체와 이차원 배열을 이용한 실습 문제 들이다. 

## 2. 이해를 돕기 위한 동영상 강의 시청

[C언어 기초 프로그래밍 강좌 19강 - 동적 메모리 (C Programming Tutorial For Beginners 2017 #19)](https://www.youtube.com/watch?v=bEkAckPDHkM)

[[C언어] 동적할당 정리2 (malloc, free 예제)](https://blockdmask.tistory.com/290)
