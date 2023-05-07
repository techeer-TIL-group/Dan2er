히스토그램 코드 작성.

1. 함수작성(rand_rv)
2. for 중첩
3. 출력

```c
#include <stdio.h>
#include <stdlib.h>
#define MAX_NUM 10000
#define INTERVALS 11

double uniform_rv()
{
    int j=1+(int)(100000.0*rand()/(RAND_MAX+1.0));
    double value=(double)j/100000;
    return value;
}

int main(int argc, const char * argv[]) {
    int case_division[4] = {10, 100, 1000, 10000};
    int counts[INTERVALS] = {0};
    double rand_num;
    

    // for 문 중첩을 통해 10, 100, 1000, 10000 각각의 경우 실행.
    for(int j = 0; j < 4; j++) {
       
        for(int i = 0; i < case_division[j]; i++) {
            rand_num = 10.0 * uniform_rv(); // 10을 곱해주며 0과 10사이의 값 생성
            counts[(int)rand_num]++; // 값이 들어갈 interval의 count 증가(히스토그램 * 개수 출력에 필요)
        }

        // histogram 출력
        printf("%d", case_division[j]);
        for(int i = 0; i < INTERVALS - 1; i++) {    // 1차 중첩(step-size 표시)
            printf("%2d ~%2d: ", i, i + 1);
            for(int k = 0; k < counts[i]; k++) {    //2차 중첩(히스토그램 출력)
                printf("*");
            }
            printf("\n");
        }
        printf("\n");

        
        for(int i = 0; i < INTERVALS; i++) { // count 초기화
            counts[i] = 0;
        }
    }

    return 0;
}
```

참고 자료

[[C/C++ 해보기] 랜덤 값 히스토그램](https://moonachi.tistory.com/121)
