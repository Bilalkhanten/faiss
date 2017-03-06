/* THIS SOFTWARE IS A DATABASE PROJECT WITH ALL THE BASIC CAPABILITIES A
   ////////////////////////////////////////////////////////////////////////
   DATABASE SHOULD HAVE. THIS APPLICATION SOFTWARE IS ABOUT LIBRARY MANAGEMENT
   ///////////////////////////////////////////////////////////////////////////
   SYSTEM AND IT RECORDS AND MAINTAINS RECORDS ABOUT THE BOOKS AND THE STUDENTS.
   ///////////////////////////////////////////////////////////////////////////
   RECORDS FOR BOOKS AND STUDENTS ARE SAVED IN SEPERATE FILES AND CAN
   ////////////////////////////////////////////////////////////////////////
   BE USED TO DELETE, TO SEARCH & TO MODIFY RECORDS IN THEM ..............*/
   
#include<iostream>
#include<cstdlib>
#include<cstring>
#include<iomanip>
#include <conio.h>
#include<ctime>
#include<windows.h>
#include<fstream>
#include<climits>
using namespace std;
bool s_flag=false;
bool b_flag=false;
bool login_flag=false;
bool run1=false;
bool run2=false;
using namespace std;
static int size=0;
////////////////////////////////STUDENT SECTION/////////////////////////////////
class book;
class student
{
	private:
		int id;
		string stud;
		int libnum;
		
	public:
		void set1(int id,int libnum,string stud)
		{
			this->id=id;
			this->libnum=libnum;
			this->stud=stud;
			return ;
		}	
		int getid()
		{
			return id;
		}
		int getlibnum()
		{
			return libnum;
		}
		string getstud()
		{
			return stud;
		}
		static int rang();
		void add(student s[]);
		void view(student s[]);
		void edit(student s[]);
		void delet(student s[]);
		void search(student s[]);
		friend void issue(student st[],book bk[]);
};

int student::rang()
{
	cout<<"Enter the Range: "<<endl;
	while (!(cin >> size))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter Range ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
}
//**********************************************************
// THIS FUNCTION INSERT THE LIST OF STUDENTS.
//**********************************************************

void student::add(student s[])
{
	rang();
	s_flag=true;
	run1=true;
	for(int i=0;i<size;i++)
	{
		int l,m;string n;
		cout<<"Enter ID of Student: "<<i+1<<endl;
		while (!(cin >> l))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter ID ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
	    cout<<"Enter Library No# of Student: "<<i+1<<endl;
		while (!(cin >> m))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter Library Number ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
		cout<<"Enter Name of Student: "<<i+1<<endl;
		cin.ignore();
		getline(cin,n);
		s[i].set1(l,m,n);
	}
	ofstream file("Student_add.txt",ios::binary|ios::app);
	file.write((char*)s,sizeof(s));
	file.close();
/*	ifstream file2("Book_add.txt",ios::binary|ios::in);
	file2.read((char*)a,sizeof(a));
	for(int i=0;i<size;i++)
	{
		cout<<"__________________________________"<<endl;
		cout<<"Code of Book "<<i+1<<" : "<<a[i].getcode()<<endl;
		cout<<"Stock of Book "<<i+1<<" : "<<a[i].getstock()<<endl;
		cout<<"Name of Book: "<<i+1<<" : "<<a[i].getname()<<endl;
		cout<<"__________________________________"<<endl;
	}	
	file2.close();			*/
	cout<<"___________________________________"<<endl;
	cout<<"|*** Records have been Inserted ***|"<<endl;
	cout<<"___________________________________"<<endl;
}

//**********************************************************
// THIS FUNCTION DISPLAY THE LIST OF STUDENTS.
//**********************************************************

void student::view(student s[])
{
	if(s_flag!=false)
	{
		ifstream file2("Student_add.txt",ios::binary|ios::in);
		cout<<"\t\t______________________________"<<endl;
		cout<<"\t\t|*** STUDENTS INFORMATION ***|"<<endl;
		cout<<"\t\t______________________________"<<endl;
		cout<<endl;
		for(int i=0;i<size;i++)
		{
			file2.read((char*)s,sizeof(s));
			cout<<"____________________________________"<<endl;
			cout<<"ID of Student "<<i+1<<" : "<<s[i].getid()<<endl;
			cout<<"Library No# of Student "<<i+1<<" : "<<s[i].getlibnum()<<endl;
			cout<<"Name of Student: "<<i+1<<" : "<<s[i].getstud()<<endl;
			cout<<"____________________________________"<<endl;
		}	
		file2.close();
	}
	if(s_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}
}

//**********************************************************
// THIS FUNCTION MODIFY THE LIST OF STUDENTS.
//**********************************************************

void student::edit(student s[])
{
	int rec,ind,q,w;
	string e;
	if(s_flag!=false)
	{
		cout<<"Enter the ID to Edit Record: "<<endl;
		cin>>rec;
		for(int i=0;i<size;i++)
		{
			if(s[i].id==rec)
			{
				ind=i;
				cout<<"Enter ID of Student: "<<i+1<<endl;
				while (!(cin >> q))
			    {
			        cout << "|*** That's Not a Number Please Re-Enter ID ***| ";
			        cin.clear();
			        cin.ignore();
			        cout<<endl;
			    }
			    cout<<"Enter Library No# of Student: "<<i+1<<endl;
				while (!(cin >> w))
			    {
			        cout << "|*** That's Not a Number Please Re-Enter library No# ***| ";
			        cin.clear();
			        cin.ignore();
			        cout<<endl;
			    }
				cin.ignore();
				cout<<"Enter Name of Student: "<<endl;
				getline(cin,e);
				s[ind].set1(q,w,e);
				ofstream file("Student_edit.txt",ios::binary|ios::app);
				file.write((char*)s,sizeof(s));
				file.close();
				cout<<"__________________________________"<<endl;
				cout<<"|*** Record has been Modified ***|"<<endl;
				cout<<"__________________________________"<<endl;
			}
		}
	}
	if(s_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}
}

//**********************************************************
// THIS FUNCTION SEARCH THE LIST OF STUDENTS.
//**********************************************************

void student::search(student s[])
{
	int rec,ind;
	if(s_flag!=false)
	{
		cout<<"Enter the ID to Search Record: "<<endl;
		cin>>rec;
		for(int i=0;i<size;i++)
		{
			if(s[i].id==rec)
			{
				ind=i;
				cout<<"__________________________________"<<endl;
				cout<<"ID of Student: "<<s[ind].getid()<<endl;
				cout<<"Library No# of Student: "<<s[ind].getlibnum()<<endl;
				cout<<"Name of Student: "<<s[ind].getstud()<<endl;
				cout<<"__________________________________"<<endl;
			}
		}
		ofstream file("Student_search.txt",ios::binary|ios::app);
		file.write((char*)s,sizeof(s));
		file.close();
	}
	if(s_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}
	
}
//**********************************************************
// THIS FUNCTION DELETE THE LIST OF STUDENTS.
//**********************************************************

void student::delet(student s[])
{
	int rec,ind;
	if(s_flag!=false)
	{
		cout<<"Enter the ID to Delete Records: "<<endl;
		cin>>rec;
		for(int i=0;i<size;i++)
		{
			if(s[i].id==rec)
			{
				ind=i;
				s[ind].id=s[ind+1].id;
				s[ind].libnum=s[ind+1].libnum;
				s[ind].stud=s[ind+1].stud;
				size--;
				cout<<"__________________________________"<<endl;
				cout<<"|*** Record have been Deleted ***|"<<endl;
				cout<<"__________________________________"<<endl;
			}
		}
		ofstream file("Student_Delete.txt",ios::binary|ios::app);
		file.write((char*)s,sizeof(s));
		file.close();
	}
	
	if(s_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}		
}

//**********************************************************
// THIS FUNCTION PERFORM VARIOUS OPERATIONS ON STUDENTS.
//**********************************************************

void st_operations(student obj[])
{
	int choice,ch;
	cout<<"________________________________________________________________"<<endl;
	cout<<"|**********************| STUDENT SECTION |*********************|"<<endl;
	cout<<"________________________________________________________________"<<endl;
	do
	{
		cout<<endl;
		cout<<"|****************************|"<<endl;
		cout<<"Press 1. to Add Data."<<endl;
		cout<<"Press 2. to Edit Data."<<endl;
		cout<<"Press 3. to Delete Data."<<endl;
		cout<<"Press 4. to Search Data."<<endl;
		cout<<"Press 5. to View Data."<<endl;
		cout<<"Press 0. to Exit."<<endl<<endl;
		cout<<"|****************************|"<<endl<<endl;
		while (!(cin >> choice))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
	    if(choice==1)
	    {
	    	obj[0].add(obj);
		}
		if(choice==2)
	    {
	    	obj[0].edit(obj);
		}
		if(choice==3)
	    {
	    	obj[0].delet(obj);
		}
		if(choice==4)
	    {
	    	obj[0].search(obj);
		}
		if(choice==5)
	    {
	    	obj[0].view(obj);
		}
		if(choice==0)
		{
			cout<<"_____________________________________________"<<endl;
			cout<<"|*** Thank You For Performing Operations ***|"<<endl;
			cout<<"_____________________________________________"<<endl;
			cout<<endl;
		}
		if(choice>5)
		{
			cout<<"\a";
			cout<<"|*** Please Press Between (0-5) ***|"<<endl;
			cout<<endl;
		}
	}
	while (choice!=0);
	return ;	
}

/////////////////////////////BOOK SECTION/////////////////////////////

class book
{
	private:
		int code;
		string name;
		int stock;
	public:
		void set(int code,int stock,string name)
		{
			this->code=code;
			this->stock=stock;
			this->name=name;
			return ;
		}	
		int getcode()
		{
			return code;
		}
		int getstock()
		{
			return stock;
		}
		string getname()
		{
			return name;
		}
		static int range();
		void add(book a[]);
		void view(book a[]);
		void edit(book a[]);
		void delet(book a[]);
		void search(book a[]);
		friend void issue(student st[],book bk[]);
};
int book::range()
{
	cout<<"Enter the Range: "<<endl;
	while (!(cin >> size))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter Range ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
}
//**********************************************************
// THIS FUNCTION INSERT THE LIST OF BOOKS.
//**********************************************************

void book::add(book a[])
{
	range();
	b_flag=true;
	run2=true;
	for(int i=0;i<size;i++)
	{
		int l,m;string n;
		cout<<"Enter Code of Book: "<<i+1<<endl;
		while (!(cin >> l))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter Code ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
	    cout<<"Enter Stock of Book: "<<i+1<<endl;
		while (!(cin >> m))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter Stock ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
		cout<<"Enter Name of Book: "<<i+1<<endl;
		cin.ignore();
		getline(cin,n);
		a[i].set(l,m,n);
	}
	ofstream file("Book_add.txt",ios::binary|ios::out|ios::app);
	file.write((char*)a,sizeof(a));
	file.close();
/*	ifstream file2("Book_add.txt",ios::binary|ios::in);
	file2.read((char*)a,sizeof(a));
	for(int i=0;i<size;i++)
	{
		cout<<"__________________________________"<<endl;
		cout<<"Code of Book "<<i+1<<" : "<<a[i].getcode()<<endl;
		cout<<"Stock of Book "<<i+1<<" : "<<a[i].getstock()<<endl;
		cout<<"Name of Book: "<<i+1<<" : "<<a[i].getname()<<endl;
		cout<<"__________________________________"<<endl;
	}	
	file2.close();			*/
	cout<<"____________________________________"<<endl;
	cout<<"|*** Records have been Inserted ***|"<<endl;
	cout<<"____________________________________"<<endl;
}
//**********************************************************
// THIS FUNCTION DISPLAYS THE LIST OF BOOKS.
//**********************************************************

void book::view(book a[])
{
	if(b_flag!=false)
	{
		ifstream file3("Book_add.txt",ios::binary|ios::in);
		cout<<"\t\t___________________________"<<endl;
		cout<<"\t\t|*** BOOKS INFORMATION ***|"<<endl;
		cout<<"\t\t___________________________"<<endl;
		cout<<endl;
		for(int i=0;i<size;i++)
		{
			file3.read((char*)a,sizeof(a));
			cout<<"____________________________________"<<endl;
			cout<<"Code of Book "<<i+1<<" : "<<a[i].getcode()<<endl;
			cout<<"Stock of Book "<<i+1<<" : "<<a[i].getstock()<<endl;
			cout<<"Name of Book: "<<i+1<<" : "<<a[i].getname()<<endl;
			cout<<"____________________________________"<<endl;
		}	
		file3.close();
	}
	if(b_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}
}
//**********************************************************
// THIS FUNCTION MODIFY THE LIST OF BOOKS.
//**********************************************************

void book::edit(book a[])
{
	int rec,ind,q,w;
	string e;
	if(b_flag!=false)
	{
		cout<<"Enter the Code to Edit Record: "<<endl;
		cin>>rec;
		for(int i=0;i<size;i++)
		{
			if(a[i].code==rec)
			{
				ind=i;
				cout<<"Enter Code of Book: "<<i+1<<endl;
				while (!(cin >> q))
			    {
			        cout << "|*** That's Not a Number Please Re-Enter Code ***| ";
			        cin.clear();
			        cin.ignore();
			        cout<<endl;
			    }
			    cout<<"Enter Stock of Book: "<<i+1<<endl;
				while (!(cin >> w))
			    {
			        cout << "|*** That's Not a Number Please Re-Enter Stock ***| ";
			        cin.clear();
			        cin.ignore();
			        cout<<endl;
			    }
				cin.ignore();
				cout<<"Enter Name of Book: "<<endl;
				getline(cin,e);
				a[ind].set(q,w,e);
				ofstream file("Book_edit.txt",ios::binary|ios::out|ios::app);
				file.write((char*)a,sizeof(a));
				file.close();
				cout<<"__________________________________"<<endl;
				cout<<"|*** Record has been Modified ***|"<<endl;
				cout<<"__________________________________"<<endl;
			}
		}
	}
	if(b_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}
}
//**********************************************************
// THIS FUNCTION SEACRHES THE LIST OF BOOKS.
//**********************************************************

void book::search(book a[])
{
	int rec,ind;
	if(b_flag!=false)
	{
		cout<<"Enter the Code to Search Record: "<<endl;
		cin>>rec;
		for(int i=0;i<size;i++)
		{
			if(a[i].code==rec)
			{
				ind=i;
				cout<<"__________________________________"<<endl;
				cout<<"Code of Book: "<<a[ind].getcode()<<endl;
				cout<<"Stock of Book: "<<a[ind].getstock()<<endl;
				cout<<"Name of Book: "<<a[ind].getname()<<endl;
				cout<<"__________________________________"<<endl;
			}
		}
		ofstream file("Book_serach.txt",ios::binary|ios::out|ios::app);
		file.write((char*)a,sizeof(a));
		file.close();
	}
	if(b_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}
	
}
//**********************************************************
// THIS FUNCTION REMOVES THE LIST OF BOOKS.
//**********************************************************

void book::delet(book a[])
{
	int rec,ind;
	if(b_flag!=false)
	{
		cout<<"Enter the Code to Delete Records: "<<endl;
		cin>>rec;
		for(int i=0;i<size;i++)
		{
			if(a[i].code==rec)
			{
				ind=i;
				a[ind].code=a[ind+1].code;
				a[ind].stock=a[ind+1].stock;
				a[ind].name=a[ind+1].name;
				size--;
				cout<<"__________________________________"<<endl;
				cout<<"|*** Record have been Deleted ***|"<<endl;
				cout<<"__________________________________"<<endl;
			}
		}
		ofstream file("Book_delete.txt",ios::binary|ios::out|ios::app);
		file.write((char*)a,sizeof(a));
		file.close();
	}
	
	if(b_flag==false)
	{
		cout<<"____________________________________"<<endl;
		cout<<"|*** You Have to Add Data first ***|"<<endl;
		cout<<"____________________________________"<<endl;
	}		
}
//**********************************************************
// THIS FUNCTION DISPLAYS THE CURRENT TIME
//**********************************************************

char date_time()
{
    char x=' ';
    time_t depart;
    time(&depart);
    cout<<ctime(&depart);
    
    return x;
}
//**********************************************************
// THIS FUNCTION CHECKS THE AUTHENTICATION OF USER.
//**********************************************************
void login()
{
    //Username and Password to validate credentials
    const string USERNAME = "user";
    const string PASSWORD = "1234";
    string username, password;
	
    cout << "Enter Username : ";
    cin >> username;
    cout<<endl;
    if(username.length() < 4)
    {
        cout << "Username length must be atleast 4 characters long."<<endl;
    }
    else   //if username length is greater than 3
    {
        cout << "Enter Password : ";
        cin >> password;
        cout<<endl;
        if(password.length() < 4)
        {
            cout << "Password length must be atleast 4 characters long."<<endl;
            exit(1);
        }
        else 
        { 
            if(username == USERNAME && password == PASSWORD)
            {
                cout << "\t\t  |*** USER CREDENTIALS ARE CORRECT ***|" << endl;
                cout<<"|______________________________________________________________________|"<<endl;
                cout<<"LOGIN TIME:"<<endl;
                cout<<date_time()<<endl;
                login_flag=1;
            }
            else
            {
                login_flag=0;
            }
        }
        //closing the else Block.
    }
    return ;
}
//**********************************************************
// THIS FUNCTION PERFORM VARIOUS OPERATIONS ON BOOKS.
//**********************************************************
void bk_operations(book obj[])
{
	int choice,ch;
	cout<<"_____________________________________________________________"<<endl;
	cout<<"|**********************| BOOK SECTION |*********************|"<<endl;
	cout<<"_____________________________________________________________"<<endl;
	do
	{
		cout<<endl;
		cout<<"|****************************|"<<endl;
		cout<<"Press 1. to Add Data."<<endl;
		cout<<"Press 2. to Edit Data."<<endl;
		cout<<"Press 3. to Delete Data."<<endl;
		cout<<"Press 4. to Search Data."<<endl;
		cout<<"Press 5. to View Data."<<endl;
		cout<<"Press 0. to Exit."<<endl<<endl;
		cout<<"|****************************|"<<endl<<endl;
		while (!(cin >> choice))
	    {
	        cout << "|*** That's Not a Number Please Re-Enter ***| ";
	        cin.clear();
	        cin.ignore();
	        cout<<endl;
	    }
	    if(choice==1)
	    {
	    	obj[0].add(obj);
		}
		if(choice==2)
	    {
	    	obj[0].edit(obj);
		}
		if(choice==3)
	    {
	    	obj[0].delet(obj);
		}
		if(choice==4)
	    {
	    	obj[0].search(obj);
		}
		if(choice==5)
	    {
	    	obj[0].view(obj);
		}
		if(choice==0)
		{
			cout<<"_____________________________________________"<<endl;
			cout<<"|*** Thank You For Performing Operations ***|"<<endl;
			cout<<"_____________________________________________"<<endl;
			cout<<endl;
		}
		if(choice>5)
		{
			cout<<"\a";
			cout<<"|*** Please Press Between (0-5) ***|"<<endl;
			cout<<endl;
		}
	}
	while (choice!=0);
	return ;	
}

//**********************************************************
// THIS FUNCTION DEPOSITS A BOOK TO STUDENT.
//**********************************************************
void deposit(student a1[],book a2[],int cap,int d,int am)
{
	cout<<"___________________________________________________________________"<<endl;
	cout<<am<<" Book '"<<a2[cap].getname()<<"' Has Been Issued to Mr. '"<<a1[cap].getstud()<<"' for only '"<<d<<"' Days."<<endl;
	cout<<"___________________________________________________________________"<<endl;
	cout<<endl;
	cout<<"|*** RS. 50 Will be Coined Per-day (only-if Returned Late) ***|"<<endl;
	cout<<endl;
	return ;
}

//**********************************************************
// THIS FUNCTION WITHDRAW A BOOK FROM STUDENT.
//**********************************************************
void returned(student a1[],book a2[],int cap,int d,int am,float p)
{
	cout<<"___________________________________________________________________"<<endl;
	cout<<am<<" Book '"<<a2[cap].getname()<<"' Has Been Returned by Mr. '"<<a1[cap].getstud()<<"' after '"<<d<<"' Days."<<endl;
	cout<<"___________________________________________________________________"<<endl;
	cout<<endl;
	cout<<"|*** RS. '"<<p<<"' is Payable Because of Late Return ***|"<<endl;
	cout<<endl;
	return ;
}
//**********************************************************
// THIS FUNCTION ISSUES A BOOK TO STUDENT.
//**********************************************************
void issue(student st[],book bk[])
{
	int pub;
	bool depos=false;
	int cod,qua,sea;
	int ret;
	bool sad=false;
	bool bad=false;
	int days=15;
	
	int ind,price,total;
	if(run1!=false)
	{
		if(run2!=false)
		{
			cout<<"Enter Student ID: "<<endl;
			while (!(cin >> pub))
		    {
		        cout << "|*** That's Not a Number Please Re-Enter ***| ";
		        cin.clear();
		        cin.ignore();
		        cout<<endl;
		    }
			for(int i=0;i<size;i++)
			{
				if(pub==st[i].id)
				{	
					ind=i;
					sad=true;
					cout<<"______________________________"<<endl;
					cout<<"|*** Student Record Exist ***|"<<endl;
					cout<<"______________________________"<<endl;
					cout<<endl;
					
					cout<<"Enter the Book Code: "<<endl;
					while (!(cin >> cod))
				    {
				        cout << "|*** That's Not a Number Please Re-Enter ***| ";
				        cin.clear();
				        cin.ignore();
				        cout<<endl;
				    }
					if(cod==bk[i].code)
					{
						bad=true;
						if(bad==true)
						{
							cout<<"___________________________"<<endl;
							cout<<"|*** Book Record Exist ***|"<<endl;
							cout<<"___________________________"<<endl;
							cout<<endl;
							cout<<"Enter the Quantity: "<<endl;
							while (!(cin >> qua))
						    {
						        cout << "|*** That's Not a Number Please Re-Enter ***| ";
						        cin.clear();
						        cin.ignore();
						        cout<<endl;
						    }
						    bk[i].stock=bk[i].stock-qua;
						    do
						    {
						    	cout<<endl;
						    	cout<<"______________________________"<<endl;
								cout<<"|****************************|"<<endl;
								cout<<"Press 1. to Deposit Book."<<endl;
								cout<<"Press 2. to Return Book."<<endl;
								cout<<"Press 0. to Exit."<<endl<<endl;
								cout<<"|****************************|"<<endl;
								cout<<"______________________________"<<endl<<endl;
								
								while (!(cin >> sea))
							    {
							        cout << "|*** That's Not a Number Please Re-Enter ***| ";
							        cin.clear();
							        cin.ignore();
							        cout<<endl;
							    }
						    	if(sea==1)
							    {
							    	depos=true;
							    	cout<<"Enter Number of Days for Possesion: "<<endl;
							    	while (!(cin >> days))
								    {
								        cout << "|*** That's Not a Number Please Re-Enter ***| ";
								        cin.clear();
								        cin.ignore();
								        cout<<endl;
								    }
								    deposit(st,bk,ind,days,qua);
								}
								if(depos!=false)
								{
									if(sea==2)
									{
										cout<<endl;
										cout<<"Enter the Day of Return: "<<endl;
										while (!(cin >> ret))
									    {
									        cout << "|*** That's Not a Number Please Re-Enter ***| ";
									        cin.clear();
									        cin.ignore();
									        cout<<endl;
									    }
									    if(ret>days)
									    {
									    	total=ret-days;
									    	price=total*50;
									    	returned(st,bk,ind,total,qua,price);
										}
										if(ret<=days)
										{
											bk[i].stock=bk[i].stock+qua;
											cout<<"______________________________________________"<<endl;
											cout<<"|*** Thank You for Returning Book in Time ***|"<<endl;
											cout<<"______________________________________________"<<endl;
											cout<<endl;
										}
									}
								}
								else
								{
									cout<<"____________________________________"<<endl;
									cout<<"|*** No Book Has Been Depostied ***|"<<endl;
									cout<<"____________________________________"<<endl;
									cout<<endl;
								}
								
								if(sea==0)
								{
									cout<<"\t\t____________________"<<endl;
									cout<<"\t\t|*** THANK YOU  ***|"<<endl;
									cout<<"\t\t____________________"<<endl;
									cout<<endl;
									break;
								}
								if(sea>2)
								{
									cout<<"|*** You are required to Press Between (0-2) ***|"<<endl;
									cout<<endl;
								}
								
							}
							while(sea!=0);
						}
						
					}
				}
			}
			if(sad!=true)
			{
				cout<<"_______________________________"<<endl;
				cout<<"|*** Student Doesn't Exist ***|"<<endl;
				cout<<"_______________________________"<<endl;
				cout<<endl;
			}
			if(bad!=true)
			{
				cout<<"____________________________"<<endl;
				cout<<"|*** Book Doesn't Exist ***|"<<endl;
				cout<<"____________________________"<<endl;
				cout<<endl;
			}
			
		}
		else
		{
			cout<<"______________________________________________________"<<endl;
			cout<<"|*** Book Records are Needed to be Inserted First ***|"<<endl;
			cout<<"______________________________________________________"<<endl;
			cout<<endl;
		}
	}
	
	else
	{
		cout<<"_________________________________________________________"<<endl;
		cout<<"|*** Student Records are Needed to be Inserted First ***|"<<endl;
		cout<<"_________________________________________________________"<<endl;
		cout<<endl;
	}
	return ;
}

//**********************************************************
// THIS FUNCTION MAKES DATABASE FOR LIBRARY SYSTEM.
//**********************************************************
void library(student s1[],book obj[])
{
	int dap;
	cout<<"________________________________________________________________________"<<endl;
	cout<<"|**********************| LIBRARY DATABASE SYSTEM |*********************|"<<endl;
	cout<<"________________________________________________________________________"<<endl;
	cout<<"\n\n";
	login();
	do
	{
		if(login_flag!=false)
		{
			system("COLOR F0");
			cout<<"______________________________________"<<endl;
			cout<<"|************************************|"<<endl;
			cout<<"Press 1. to Insert Student Records."<<endl;
			cout<<"Press 2. to Insert Book Records."<<endl;
			cout<<"Press 3. to Issue a Book to Student."<<endl;
			cout<<"Press 0. to Exit Library System."<<endl;
			cout<<"|************************************|"<<endl;
			cout<<"______________________________________"<<endl;
			while (!(cin >> dap))
		    {
		        cout << "|*** That's Not a Number Please Re-Enter ***| ";
		        cin.clear();
		        cin.ignore();
		        cout<<endl;
		    }
			if(dap==1)
			{
				st_operations(s1);
			}
			if(dap==2)
			{
				bk_operations(obj);	
			}
			if(dap==3)
			{
				issue(s1,obj);
			}
			if(dap==0)
			{
				system("CLS");
				
				cout<<endl;
				if(s_flag!=false)
				{
					s1[0].view(s1);
				}
				if(b_flag!=false)
				{
					obj[0].view(obj);
				}
				
				cout<<"\n\n\n";
				cout<<"\t\t\t**********"<<endl;
				cout<<"_______________________________________________________"<<endl;
				cout<<"|*** THANK YOU FOR USING LIBRARY MANAGEMENT SYSTEM ***|"<<endl;
				cout<<"_______________________________________________________"<<endl;
				cout<<"\t\t\t**********"<<endl;
				cout<<"\n\n\n";
				
				exit(1);
			}
			if(dap>3)
			{
				cout<<"\a";
				cout<<"|*** Please Press Between (0-3) ***|"<<endl;
				cout<<endl;
			}
		}
		else
		{
			system("COLOR 0C");
			Sleep(200);
			cout<<"\t\t\t\t*****************"<<endl;
			cout<<"\t\t\t\t| INVALID LOGIN |"<<endl;
			cout<<"\t\t\t\t*****************"<<endl;
			cout<<endl<<endl<<endl;
			Sleep(1000);
			exit(1);
		}
	}
	while(dap!=0);
}
//--------------------------------------------------------------------//
//////////////////////////////Main Section//////////////////////////////
//--------------------------------------------------------------------//
int main()
{
	const int lim=500;
	book obj[lim];
	student s1[lim];
	library(s1,obj);
	
	system("pause");
	return 0;
}
