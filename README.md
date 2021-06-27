#include<iostream>

using namespace std;
int r=0, p=0, k=20;
float allsell = 0;
class bus{
	char arrival[9], depart[10], from[10], to[10], pname[50];
	int busno, dpt, arv, totseat,s;
	public:
	      void install();
		  void show();
		  void book();
		  void exit(); 
}b[8];
void bus::install(void)
{
	cout<<"enter bus no:";
	cin>>busno;
	while(1){
		if(!(cin>>busno)){
			cin.clear();
            cin.ignore();
            cout<<"Invalid bus no.! enter again:";
		
		
			cin>>busno;
			}
		if(!cin.fail())
		break;
		}
		
	
	cout<<"\nFrom:";
	cin>>from;
	
	
	cout<<"\nTo:";
	cin>>to;
	
	
	cout<<"\nArrival:";
	cin>>arv;
	while(1){
		if(!(cin>>arv)){
			cin.clear();
            cin.ignore();
            cout<<"Invalid arrival time! enter again:";
		
		
			cin>>arv;
			}
		if(!cin.fail())
		break;
		}
	cout<<"\nDeparture:";
	cin>>dpt;
	while(1){
		if(!(cin>>dpt)){
			cin.clear();
            cin.ignore();
            cout<<"Invalid departure time! enter again:";
		
		
			cin>>dpt;
			}
		if(!cin.fail())
		break;
		}
	cout<<"\nTotal number of seats:";
	cin>>totseat;
	p++;
	cout<<"\n";
	cout<<"Success!!Information updated!!\n";
	system("PAUSE");
	system("CLS");
}
void bus::show(void)
{
	cout<<"Total number of buses available:"<<endl;
	for(int i=0; i<p; i++)
	         {
	         	cout<<"Bus No: ";
	         	cout<<b[i].busno<<endl;
	         	cout<<"From: ";
	         	cout<<b[i].from<<endl;
	         	cout<<"To: ";
	         	cout<<b[i].to<<endl;
	         	cout<<"Arrival: ";
	         	cout<<b[i].arv<<" hrs"<<endl;
	         	cout<<"Departure: ";
	         	cout<<b[i].dpt<<" hrs"<<endl;
	         	cout<<"Seats: ";
	         	cout<<b[i].totseat<<endl<<endl<<endl;
			 }
			 system("PAUSE");
			 system("CLS");
}
void bus::book(void)
{
int number;
float fair;
	cout<<"Enter Bus No: ";
	cin>>number;
	int n;
 for(n=0;n<p;n++)
 {
	 if(b[n].busno==number)
	 {
		if(b[n].totseat<=0)
		{
		cout<<"\tSORRY!"<<endl<<"\tNo  Seat Available\t";
		}
		else
		{
		 cout<<endl<<"Total seat available: "<<b[n].totseat;
		 cout<<endl<<"Enter Passenger's Name: ";
		 cin>>pname;
		 cout<<endl<<"Number of seats: ";
		 cin>>s;
		 while((b[n].totseat=b[n].totseat-s)<0)
			 {cout<<endl<<"Limit Exceed...Please re-enter ";
			 b[n].totseat=b[n].totseat+s;
				cin>>s;
		 }
cout<<endl<<"SUCCESS!!!Your booking is completed"<<endl;
cout<<"Bus No: ";
cout<<b[n].busno<<endl;
cout<<"From: ";
cout<<b[n].from<<" to "<<b[n].to<<endl;
cout<<"Arrival: ";
cout<<b[n].arv<<"hrs"<<endl;
cout<<"Departure: ";
cout<<b[n].dpt<<"hrs"<<endl;
cout<<"Total seat: ";
cout<<s<<endl;
cout<<"Thank You"<<endl<<endl;

		  }
	 }

 }
 if(b[n].busno!=number)
 {
 	cout<<"No such seat number is available.";
 }
system("PAUSE");
system("CLS");

}

int main()
 {
	int w,g=1;
 while(g){
 cout<<"\n\n\t\t\t\t==================================================="<<endl;
 cout<<"\t\t\t\t\t\tBus Ticketing System\n";
 cout<<"\t\t\t\t==================================================="<<endl;

 cout<<"\t\t\t\t\t 1 => Install\n\t\t\t\t\t 2 => List of Available Buses\n\t\t\t\t\t 3 => Book Tickets\n\t\t\t\t\t 4 => Exit";
 cout<<"\n\n\t\t\t\t\t Enter your choice: ";
 cin>>w;
 switch(w){
 case 1:
	b[p].install();
	break;
 case 2:
	 b[0].show();
     break;
 case 3:
	b[p].book();
    break;
 case 4:
	 {
g=0;

cout<<endl<<"********Thank You********"<<endl;
break;
	 }
 }
}
return 0;
}	
