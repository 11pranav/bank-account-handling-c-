#include <iostream>
#include <string>

using namespace std;
class Account
{
 private:
 int account_no;
 string name,gender;
 double amount;
 static int account_generator;
 public:
 	static int generate_account_no()
 	{
 		return(++account_generator);
	 }
 void create_account(string name,string gender,double amount)	
 {
 	this->name=name;
 	this->gender=gender;
 	this->amount=amount;
 	this->account_no=generate_account_no();
 	cout<<"\nhi "<<name<<" Congrats! Account generated and number is "<<account_no;
 }
 void check_balance()
 {
 	cout<<endl<<"Account number:"<<account_no<<"\tName:"<<name<<"\tGender:"<<gender<<"\tBalance:"<<amount;
 }
 int get_account_no()
 {
 	return account_no;
 }
 
 //accept amount from the user if (amount - the withdraw amount) is not in negative, 
 //will allow the transaction, update account balance, 
 //and update the user about a successful transaction.
 void withdraw(double amount)
 {
 	if((this->amount-amount)>=0)
 	{
 		this->amount-=amount;//x=x-1-->x-=1
 		cout<<"\nSelection successful, new balance is:"<<this->amount;
	 }
	 else
	 	cout<<"\nTransaction failed due to insufficient balance";
  } 
  void deposit(double amount)
 {
 	if(amount>0)
 	{
	 this->amount+=amount;//x=x-1-->x-=1
 	 cout<<"\nSelection successful, new balance is:"<<this->amount;
	 }
	 else
	 	cout<<"\nAmount cannot be negative.";
  } 
};
int Account::account_generator=2500;

int main() 
{
	Account account[100];
	int i,ch,account_no,current_accounts=0,flag;
	string name,gender;
	double amount;
	//Create a menu and a switch case to call 1.Create account 2.deposit 3.withdraw 4.balance check 
	do
	{
		cout << "\n==== Banking System Menu ====\n";
        cout << "1. Create Account\n";
        cout << "2. Deposit Money\n";
        cout << "3. Withdraw Money\n";
        cout << "4. Check Balance\n";
        cout << "0. Exit\n";
        cout << "Enter your choice: ";
        cin >> ch;
        switch(ch)
        {
        	case 1:
        		cout<<"Enter Name:";
        		cin.ignore();
        		getline(cin,name);
        		cout<<"Enter Gender:";
        		cin>>gender;
        		//min balance 5000 else will not open account
        		while(true)
        		{
        			cout<<"\nEnter amount for opening account, minimum amount allowed ?5000.\n"	;
        			cin>>amount;
        			if (amount>=5000)
        				break;
        			else
        				cout<<"\nWrong amount entered."	;
				}
				account[current_accounts++].create_account(name,gender,amount);
        		break;
        		
        	case 2:
        			{cout<<"\nEnter account number:"; //Accept the account number
        			cin>>account_no;
        			int flag=0;//means not found 
        			for(int i=0;i<current_accounts;i++)
        				{
        					if(account_no==account[i].get_account_no())
        					{
        						cout<<"\nEnter amount:";
        						cin>>amount;
        						account[i].deposit(amount);
        						flag=1;//found bit set to 1
        						break;
							}
						}
					if(flag==0)
						cout<<account_no<<" not found.";
					break;
				}

			case 3:
				{
				
				
        			cout<<"\nEnter account number:"; //Accept the account number
        			cin>>account_no;
        			flag=0;//means not found 
        			for(int i=0;i<current_accounts;i++)
        				{
        					if(account_no==account[i].get_account_no())
        					{
        						cout<<"\nEnter amount:";
        						cin>>amount;
        						account[i].withdraw(amount);
        						flag=1;//found bit set to 1
        						break;
							}
						}
					if(flag==0)
						cout<<account_no<<" not found.";
					break;
				}	
				case 4:
					{
					
        			cout<<"\nEnter account number:"; //Accept the account number
        			cin>>account_no;
        			flag=0;//means not found 
        			for(int i=0;i<current_accounts;i++)
        				{
        					if(account_no==account[i].get_account_no())
        					{
        						account[i].check_balance();
        						flag=1;//found bit set to 1
        						break;
							}
						}
					if(flag==0)
						cout<<account_no<<" not found.";
					break;
				}
					case 0:
						cout<<"\nThanks for using Lena Banks.";
						break;
					default:
						cout<<"\nInvalid option selected ";
						break;
		}

	}while(ch!=0);
	    
}
