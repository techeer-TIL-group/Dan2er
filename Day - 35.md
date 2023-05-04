# 실습문제 와의 사투..

## 그래도 이제는 속도가 좀 난다…

```
#include<stdio.h>

int main(){

 char input[101];
    char shortest[101] = { 0 };
    int N, L;
    
    char** st = NULL;
    scanf("%d", &N);
    getchar();
    int id = 0;
    st =(char **)malloc(N * sizeof(char *));
    if (st == NULL) {
        return -1;
    }
    
    for (int i = 0; i < N; i++) {
        
        gets(input);
        L = strlen(input);
        st[i] = (char*)malloc(L + 1);
        if (st[i] == NULL) {
            return -1;
        }
        strcpy(st[i], input);
    }
    
    int shortstrlen = strlen(st[0]);

    for (int i = 1; i < N; i++) {

        
        if (shortstrlen > strlen(st[i])) {
            id = i;
            shortstrlen = strlen(st[i]);
        }

    }
    
    printf("%s", st[id]);
    for (int i = 0; i < N; i++) {
        free(st[i]);
    }
    free(st);
	

	return 0;
}

//9
#include<stdio.h>

int main(){

char input[101];
	char shortest[101] = { 0 };
	int N, L;

	char** st = NULL;
	scanf("%d", &N);
	getchar();
	int id = 0;
	st = (char **)malloc(N * sizeof(char *));
	if (st == NULL) {
		return -1;
	}

	for (int i = 0; i < N; i++) {

		gets(input);
		L = strlen(input);
		st[i] = (char*)malloc(L + 1);
		if (st[i] == NULL) {
			return -1;
		}
		strcpy(st[i], input);
	} 

	int shortstrlen = strlen(st[0]);
	char *temp;
	for (int i = 0; i < N; i++) {
		for (int j = 0; j < i; j++) {
			if (strlen(st[i]) > strlen(st[j])) {
				temp = st[i];
				st[i] = st[j];
				st[j] = temp;

			}

		}
	}
		

	

	
	for (int i = 0; i < N; i++) {
		printf("%s\n", st[i]);
	}
	free(st);
	for (int i = 0; i < N; i++) {
		free(st[i]);
	}

	return 0;
}

//10
#include<stdio.h>

int main(){

int N;
    scanf("%d", &N);
    int* x = NULL;
    int* y = NULL;
    x = (int*)malloc(sizeof(int) * N);
    y = (int*)malloc(sizeof(int) * (N - 1));
    for (int i = 0; i < N; i++) {
        *(x+i) = i;
    }
    for (int i = 0; i < N-1; i++) {
        if (i < (N - 1) / 2) {
            *(y + i) = *(x + i);
        }
        else  if (i >= (N - 1) / 2) {
            *(y+i) = *(x+i) + 1;
        }
    }
    for (int i = 0; i < N-1 ; i++) {
        printf(" %d", *(y + i));
    }

	return 0;
}

//11

#include<stdio.h>

int main(){

int* x = NULL;
	int a = 5;
	int* y = NULL;
	x = (int*)malloc(sizeof(int) * 100);
	y = (int*)malloc(sizeof(int) * 5);
	for (int i = 0; ; i++) {

		scanf("%d", &x[i]);
		y[i] = x[i];
		if (x[i] == -1) {
			for (int j = 0; j <= i; j++) {
				printf(" %d", x[j]);
			}
			break;
		}

		a = a + 3;
		y = (int*)malloc(sizeof(int) * a);
	}

	return 0;
}
```

오늘의 영상자료는 효율적인 코딩에 관한 유튜브 영상이다.(니콜라스 좌)

[깨끗한 코드를 위한 5가지 팁](https://www.youtube.com/watch?v=Jz8Sx1XYb04)
