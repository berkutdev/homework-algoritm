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
