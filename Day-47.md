현재 파이썬과 자바 강의를 하루에 한개씩 듣고 복습중이다.

```python
from random import*

class Unit:

def __init__(self,name,hp,speed):            #__init__ 에서 self 를 제외한 값의 개수를 맞춰줘야 한다. 객체.

    self.name=name                  #멤버변수는 Unit 안에 있는 변수들

    self.hp=hp

    self.speed=speed

    print("{0} 유닛이 생성되었습니다.".format(name))

def move(self, location):

    print("{0} : {1} 방향으로 이동합니다.[속도 {2}]".format(self.name,location,self.speed))

def damaged(self,damage):

    print("{0}:{1} 데미지를 입었습니다.".format(self.name,damage))

    self.hp-=damage

    print("{0}: 현재 체력은{1} 입니다.".format(self.name, self.hp))

    if self.hp<=0:

        print("{0} : 파괴되었습니다.".format(self.name))

```

그것과 별개로 python queryset 에 대하여 공부하였다.

[[Django] QuerySet](https://velog.io/@inyong_pang/Django-QuerySet)
