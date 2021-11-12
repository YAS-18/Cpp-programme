# Cpp-programme
C++ Program for students database system using the OOPs fundamentals like class ; static variables &amp; functions ; constructors , etc.

#include <iostream>
using namespace std;
class Class
{
	
	long int contact;
	string name;
  string addresse;
	string blood_grp;
public:
   int roll_no;
   static string class_teacher; 
   static char div; 
   static int n;
    Class(){
      name="xxxxxxxx";
      roll_no=00;
      blood_grp="X(+/-ve)";
      addresse="xxxxxxxxxxx";
      contact= 0000000000;
    }

   static void set()
   {
    cout<<endl<<"Enter the name of class teacher ::";
    cin>>class_teacher;
    cout<<"Enter the division ::";
    cin>>div;
   }

   void setDetails();
   void display();	
};

//initialization static variables
string Class:: class_teacher;
char Class:: div;
int Class::n;

//function to read the details
void Class::setDetails()
   {
    cout<<endl<<"Enter the name of student :-";
    cin>>name;
    cout<<"Enter the Roll no. :-";
    cin>>roll_no;
    cout<<"Enter the Blood group :-";
    cin>>blood_grp;
    cout<<"Enter the Addresse :-";
    cin>>addresse;
    cout<<"Enter the Contact no. :-";
    cin>>contact;
    cout<<"_______________________________________________"<<endl;
   }

//function to display the details1
void Class::display()
   {
    cout<<"Name of student :-"<<name<<endl;
    cout<<"Roll no. :-"<<roll_no<<endl;
    cout<<"Blood Group :-"<<blood_grp<<endl;
    cout<<"Addresse :-"<<addresse<<endl;
    cout<<"Contact no. :-"<<contact<<endl;
    cout<<"___________________________________"<<endl;
   } 

   
int main()
{
	int ch;
  int n;
  int reply;

    cout<<"\t \t \t PIMPRI CHINCHWAD EDUCATION TRUST`S"<<endl<< "\t \tPIMPRI CHINCHWAD COLLEGE OF ENGINEERING ,PUNE"<<endl;
    cout<<"_________________________________________________________"<<endl<<endl<<endl;
    cout<<"Enter the Number of Students in Class ::";
    cin>>Class::n;
    Class Student[Class::n];
       
   while(1)
   {
   cout<<"\t\t\t\tMENU"<<endl;
   cout<<"1.CLASS TEACHER AND DIVISION"<<endl;
   cout<<"2.SET STUDENT RECORD"<<endl;
   cout<<"3.DIAPLAY DETAILS"<<endl;
   cout<<"4.SEARCH STUDUENT"<<endl;
   cout<<"5.EXIT"<<endl;
   cout<<"Enter your choice (1/2/3/4/5)::";
   cin>>ch;
   cout<<"____________________________________________________________"<<endl;
   switch(ch)
   {
   case 1:
          cout<<"ENTER THE CLASS TEACHER NAME AND DIVISION "<<endl;
          Class::set();
          break;

   case 2:
          cout<<endl<<"ENTER THE STUDENTS DETAILS IN BELOW "<<endl;
          
          for(int i=0;i<Class::n;i++)
           {
            Student[i].setDetails();
           }
           break;

  case 3:
          cout<<"DISPLAYING THE CLASS STUDENTS DETAILS"<<endl<<endl;

          cout<<"Div :- "<<Class::div<<"\t\t\t\t\t\t\tCLASS TEACHER :- "<<Class::class_teacher<<endl<<endl;
          for(int i=0;i<Class::n;i++)
           {
            Student[i].display();
           } 
           n++;
          break;
          
  case 4:
          int rn,Return;
          cout<<endl<<"SEARCH THE STUDENT"<<endl;
          cout<<"Enter the roll number of the student ::";
          cin>>rn;
           for(int i=0;i<Class::n;i++)
             {
               if(Student[i].roll_no==rn)
               {
                 Student[i].display();
                 break;
               }
              }
              if(rn>Class::n){
                cout<<endl<<"Roll no. does not Exit........"<<endl;
              } 
          break;
  case 5: 
          return 0;
 
  default:
          cout<<"INVALID CHOICE.......";
   }
   } 
}    
