# Python.starcraft
# 마린 : 공격 유닛, 군인. 총을 쏠 수 있음.

name = '마린'

hp = 40

damage = 5

​

print("{} 유닛이 생성되었습니다.".format(name))

print("체력 {0}, 공격력{1}\n".format(hp, damage))

​

# 탱크 : 공격 유닛, 탱크. 포를 쏠 수 있는데, 일반 모드 / 시즈 모드.

tank_name = '탱크'

tank_hp = 150

tank_damage = 35

​

print("{} 유닛이 생성되었습니다.".format(tank_name))

print("체력 {0}, 공격력{1}\n".format(tank_hp, tank_damage))

​

tank2_name = '탱크'

tank2_hp = 150

tank2_damage = 35

​

print("{} 유닛이 생성되었습니다.".format(tank2_name))

print("체력 {0}, 공격력{1}\n".format(tank2_hp, tank2_damage))

​

def attack(name, location, damage):

    print("{0} : {1} 방향으로 적군을 공격 합니다. [공격력 {2}]".format(name,location,damage))

​

attack(name, "1시", damage)

attack(tank_name, "1시", tank_damage)

attack(tank2_name, "1시", tank2_damage)

​

class

class Unit:

    def __init__(self, name, hp, damage):

        self.name = name

        self.hp = hp

        self.damage = damage

        print("{0} 유닛이 생성 되었습니다.".format(self.name))

        print(" 체력 {0}, 공격력 {1}".format(self.hp, self.damage))

​

marine1 = Unit("마린",40,5)

marine2 = Unit("마린",40,5)

tank = Unit("탱크", 150, 35)

출력결과 :

마린 유닛이 생성 되었습니다.

 체력 40, 공격력 5

마린 유닛이 생성 되었습니다.

 체력 40, 공격력 5

탱크 유닛이 생성 되었습니다.

 체력 150, 공격력 35

​

class Unit:

    def __init__(self, name, hp, damage):

        self.name = name

        self.hp = hp

        self.damage = damage

        print("{0} 유닛이 생성 되었습니다.".format(self.name))

        print(" 체력 {0}, 공격력 {1}".format(self.hp, self.damage))

​

# 공격 유닛

class AttackUnit:

    def __init__(self, name, hp, damage):

        self.name = name

        self.hp = hp

        self.damage = damage

​

    def attack(self, location):

        print("{0} : {1}방향으로 적군을 공격합니다. [공격력 {2}]"

        .format(self.name, location, self.damage))

​

    def damaged(self, damage):

        print("{0} : {1} 데미지를 입었습니다.".format(self.name,damage))

        self.hp -= damage

        print("{0} : 현재 체력은 {1} 입니다.".format(self.name,self.hp))

        if self.hp <= 0:

            print("{0} : 파괴되었습니다.".format(self.name))

​

# 파이어뱃 : 공격 유닛, 화염방사기.

firebat1 = AttackUnit("파이어뱃", 50, 16)

firebat1.attack("5시")

​

# 공격 2번 받는다고 가정

firebat1.damaged(25)

firebat1.damaged(25)

출력결과 :

파이어뱃 : 5시방향으로 적군을 공격합니다. [공격력 16]   

파이어뱃 : 25 데미지를 입었습니다.

파이어뱃 : 현재 체력은 25 입니다.

파이어뱃 : 25 데미지를 입었습니다.

파이어뱃 : 현재 체력은 0 입니다.

파이어뱃 : 파괴되었습니다.

​

상속

 일반 유닛과 공격 유닛의 self.name, self.hp가 겹치기 때문에 공격유닛은 일반유닛의 변수를 상속받을수 있음.

==> class AttackUnit(Unit):

def __init__(self,name,hp,damage)

       Unit.__init__(self,name,hp)

       self.damage = damage

​

# 일반 유닛

class Unit:

    def __init__(self, name, hp):

        self.name = name

        self.hp = hp

​

# 공격 유닛

class AttackUnit(Unit):  # 공격유닛은 일반유닛을 상속 받아 만들어진 것

    def __init__(self, name, hp, damage):

        Unit.__init__(self, name, hp)

        self.damage = damage
