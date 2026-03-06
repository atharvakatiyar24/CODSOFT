[Task=1.cpp](https://github.com/user-attachments/files/25801181/Task.1.cpp)
#include<iostream>
using namespace std;

int main()

{
	int random_no= rand()%100+1;// used rand() function for random number and modulo by 100+1 for range b/w(1-100).
	
	int guess=0;
	cout<<"---:NUMBER GUESSING GAME:---"<<endl;
	while(guess!=random_no)
	{
		cout<<"Enter the number(1-100) for guess:"; // user input for guess.
		cin>>guess;
	    

		if(guess>random_no)
		{
			cout<<"Too High Number! please try again..."<<endl<<"The Number was:"<<random_no<<endl;
		    random_no=rand()%100; //again refreshing the random number.
		}
		else if(guess<random_no)
		{
			cout<<"Too Low Number! please try again..."<<endl<<"The Number was:"<<random_no<<endl;
		    random_no=rand()%100;// again refreshing the random number.
		}
		else
		{
			cout<<"Congratulations!! , You Won..."<<endl;
		}
	}
	
	return(0);
	
}

