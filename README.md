# OOP-ASSIGNMENT-2
SECOND SEMESTER:OBJECT ORIENTED PROFRAMMING
#include<iostream>
#include<string>
#include<fstream>
#include<sstream>
using namespace std;
int main()
{

	ifstream reading("ShoppingList.txt");
	if (!reading.is_open())
	{
		cout << " Error in opening file! " << endl;
		return 1;
	}
	string line;
	double total_price = 0.0;
	cout << " Product Details : " << endl;
	while (getline(reading, line))
	{
		stringstream ss(line);
		string product_name;
		double product_price;
		getline(ss, product_name,',');
		ss >> product_price;
		cout << " Product name: " << product_name << endl;
		cout << " Product price: " << product_price << endl;
		total_price = total_price + product_price;
	}
	cout << " Total price " << total_price << endl;
	reading.close();
	return 0;
}
