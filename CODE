#include <iostream>
#include <string>

using namespace std;

class Moveable {
public:
    int x_position;
    int y_position;
    int hp = 100;

public:
    Moveable(int titikX, int titikY) : x_position(titikX), y_position(titikY) {}

    int getXposition() const {
        return x_position;
    }

    int getYposition() const {
        return y_position;
    }

    int getHp() const {
        return hp;
    }

    void setHp(int newHP) {
        hp = newHP;
    }
};

class Attackable {
public:
    int attackPower = 10;

    int getAttackPower() const {
        return attackPower;
    }

    void setAttackPower(int attack) {
        attackPower = attack;
    }

    virtual void attack(Moveable &target) {
        cout << "Attacking with " << attackPower << " attack power" << endl;
        target.setHp(target.getHp() - attackPower);
    }
};

class Defendable {
public:
    int defensePower = 2;

    int getDefensePower() const {
        return defensePower;
    }

    void setDefensePower(int defense) {
        defensePower = defense;
    }

    void defend() {
        cout << "Yay! You have " << defensePower << " defense HP" << endl;
    }
};

class Warrior : public Moveable, public Attackable {
public:
    string name;

    Warrior(string name, int titikX, int titikY) : Moveable(titikX, titikY), name(name) {}
};

class Mage : public Moveable, public Attackable, public Defendable {
public:
    string name;

    Mage(string name, int titikX, int titikY) : Moveable(titikX, titikY), name(name) {}
};

class Healer : public Moveable, public Defendable {
public:
    string name;

    Healer(string name, int titikX, int titikY) : Moveable(titikX, titikY), name(name) {}

    void heal() {
        if (hp < 100) {
            hp += 8;
            if (hp > 100) {
                hp = 100;
            }
            cout << "Yay! You got 8 HP, your current HP is " << hp << endl;
        }
    }
};

int main() {
    Warrior YANTO("yanto", 0, 0);
    Mage eko("eko", 0, 0);
    Healer yuni("yuni", 0, 0);

    YANTO.attack(eko);
    eko.defend();
    eko.attack(YANTO);
    eko.attack(yuni);
    yuni.heal();
    yuni.heal();

    return 0;
}

