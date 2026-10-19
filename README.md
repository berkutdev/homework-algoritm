#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    
    setlocale(LC_ALL, "Ukrainian");

    const int ROWS = 10;
    const int SEATS = 20;
    int cinema[ROWS][SEATS];

    
    srand(time(0));

    
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < SEATS; j++) {
            cinema[i][j] = rand() % 2;
        }
    }

    
    cout << "zal:\n";
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < SEATS; j++) {
            cout << cinema[i][j] << " ";
        }
        cout << endl;
    }
    cout << endl;

    
    cout << "ryadi de miste prodano:\n";
    
    for (int i = 0; i < ROWS; i++) {
        int count = 0; 
        
        for (int j = 0; j < SEATS; j++) {
            if (cinema[i][j] == 1) {
                count++;
            }
        }

        
        if (count == 20) {
            cout << "ryad nomer " << i + 1 << endl;
        }
    }

    return 0;
}




2 home work !!!! /////
#include <iostream>
using namespace std;

class Pizza
{
private:
	string name;
	unsigned short price;
	unsigned short size;
public:
	Pizza() = default;
	Pizza(string name, unsigned short price, unsigned short size);
	string getName();
	unsigned short getPrice();
	unsigned short getSize();
	void setName(string name);
	void setPrice(unsigned short price);
	void setSize(unsigned short size);
};

Pizza::Pizza(string name, unsigned short price, unsigned short size)
{
	this->name = name;
	this->price = price;
	this->size = size;
}

string Pizza::getName()
{
	return this->name;
}

unsigned short Pizza::getPrice()
{
	return this->price;
}

unsigned short Pizza::getSize()
{
	return this->size;
}

void Pizza::setName(string name)
{
	this->name = name;
}

void Pizza::setPrice(unsigned short price)
{
	this->price = price;
}

void Pizza::setSize(unsigned short size)
{
	this->size = size;
}

Pizza* searchByPrice(Pizza* order, unsigned int size, unsigned int price)
{
    for (int i = 0; i < size; i++)
    {
        if (order[i].getPrice() == price)
        {
            return &order[i];
        }
    }
    return nullptr;
}


Pizza* searchByName(Pizza* order, unsigned int size, string name)
{
    for (int i = 0; i < size; i++)
    {
        if (order[i].getName() == name)
        {
            return &order[i];
        }
    }
    return nullptr;
}

int main()
{
    setlocale(LC_ALL, " ");
    cout << "========== Linear Search (Pizza Project)!==========\n";
    unsigned int const SIZE = 3;
    Pizza order[SIZE] = {
        {"cheese4", 200, 34},
        {"margarita", 190, 26},
        {"peperroni", 300, 40}
    };

    Pizza* pizza = searchByPrice(order, SIZE, 200);
    if (pizza != nullptr)
    {
        cout << pizza->getName() << endl;
    }

    
    Pizza* pizzaByName = searchByName(order, SIZE, "margarita");
    if (pizzaByName != nullptr)
    {
        cout << pizzaByName->getName() << endl;
    }
}
