**오늘은 좀처럼 오지 않는 한가한 날이어서 그동안 하지 못했던 파이썬 공부를 다시 할 수 있었습니다!**

기존에 하고 있던 파일을 가져와서 클래스를 이용한 게임 코딩을 하는 중에 다중 상속에서 헷갈려서 동영상을 시청하였습니다.

[파이썬 코딩 도장: 36.5 다중 상속 사용하기](https://dojang.io/mod/page/view.php?id=2388)

**오늘은 좀처럼 오지 않는 한가한 날이어서 그동안 하지 못했던 파이썬 공부를 다시 할 수 있었습니다!**

기존에 하고 있던 파일을 가져와서 클래스를 이용한 게임 코딩을 하는 중에 다중 상속에서 헷갈려서 동영상을 시청하였습니다.

[파이썬 코딩 도장: 36.5 다중 상속 사용하기](https://dojang.io/mod/page/view.php?id=2388)

from random import*

class Unit:

```
def __init__(self,name,hp,speed):

    self.name=name

    self.hp=hp

    self.speed=speed

    print("{0} 유닛이 생성되었습니다.".format(name))

def move(self, location):

    print("{0} : {1} 방향으로 이동합니다.[속도{2}]".format(self.name, location,self.speed))

def damaged(self,damage):

    print("{0} : {1} 데미지를 입었습니다.".format(self.name,damage))

    self.hp-=damage

    print("{0} : 현재 체력은 {1} 입니다.".format(self.name,self.hp))

    if self.hp<=0:

        print("{0} : 파괴 되었습니다.".format(self.name))

```

class AttackUnit(Unit):              #상속

```
def __init__(self,name,hp,speed,damage):

    Unit.__init__(self,name,hp,speed)

    self.damage=damage

def attack(self,location):

    print("{0} : {1} 방향으로 적군을 공격합니다. [공격력{2}]".format(self.name,location,self.damage))

```
