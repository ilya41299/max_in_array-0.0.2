#include <iostream>
#include <sstream>
using namespace std;
int main()
{
	string stroka1, stroka2;
	getline(cin, stroka1);
	getline(cin, stroka2);
	int x[10], y[10];
	istringstream stream1(stroka1);
	istringstream stream2(stroka2);
	bool failure1 = false, failure2 = false;
	for (int i = 0; i < 10; ++i) {
		if (!(stream1 >> x[i])) {
			failure1 = true;
			break;
		}
	}
	for (int j = 0; j < 10; ++j) {
		if (!(stream2 >> y[j])) {
			failure2 = true;
			break;
		}
	}
	if (!(failure1) && !(failure2)) {
		int max1 = x[0];
		int max2 = y[0];
		for (int i = 1; i<10; ++i) {
			if (x[i]>max1) {
				max1 = x[i];
			}
		}
		for (int j = 1; j<10; ++j) {
			if (y[j]>max2) {
				max2 = y[j];
			}
		}
		cout << max1 + max2 << endl; return 0;
	}
	else {
		cout << "An error has occurred while reading numbers" << endl;
	}
	return -1;
}
