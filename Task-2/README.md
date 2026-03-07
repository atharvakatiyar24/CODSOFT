#include<iostream>
using namespace std;

int main()
{
	char operations;
	double x,y;
	cout<<"---:SIMPLE CALCULATOR:---";
	cout<<endl;
	
	cout<<"Enter Value:";  // input first value
	cin>>x;
	cout<<"Enter Operations(+,-,*,/):";  // input operations (+,-,*,/) for performing calculations
	cin>>operations;
	cout<<"Enter Value:";  // input second value
	cin>>y;
	
	switch(operations)  // used switch-case 
	{
		case '+':cout<<"Result:"<<x<<"+"<<y<<"="<<x+y;break;  
		case '-':cout<<"Result:"<<x<<"-"<<y<<"="<<x-y;break;
		case '*':cout<<"Result:"<<x<<"*"<<y<<"="<<x*y;break;
		case '/':cout<<"Result:"<<x<<"/"<<y<<"="<<x/y;break;
		
		default:cout<<"INVALID CREDENTIALS";
	}
	return(0);
	
}

