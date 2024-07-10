- #include<iostream>
#include<windows.h>
using namespace std;

void printtask(string task[], int taskno)
{
  cout<<"<--------------------------------->"<<endl;
  for(int i = 0; i<taskno; i++)
  {
    cout<<"task"<<i<< " : "<<task[i]<<endl;
  }
  cout<<"<---------------------------------->"<<endl;
}

int main()
{
    string task[10] = {""};
    int taskno = 0;

    int option = -1;
    while(option!=0)
    {
        cout<<"<<<<< TO DO LIST >>>>>"<<endl;
        cout<<"1 --> Add Task"<<endl;
        cout<<"2 --> View Task"<<endl;
        cout<<"3 --> Remove Task"<<endl;
        cout<<"4 --> for terminate the program"<<endl;

        cin>>option;
        switch(option)
        {
            case 1:
            {
                 if(taskno > 9)
                 {
                    cout<<" <--- list is full --->"<<endl;
                 }
                else{
                    cout<<" enter a task "<<endl;
                    cin.ignore();
                    getline(cin, task[taskno]);
                    taskno++;
                }
                break; 
            }
            case 2:
            {
                system("cls");
                printtask(task, taskno); 
                break;
            }
            case 3:
            {
                system("cls");
                 printtask(task, taskno); 
                int deltask = 0;
                cout<<"enter a task to delete: ";
                cin>>deltask;

                if(deltask<0 || deltask>9)
                {
                    cout<<"you entered a invalid task"<<endl;
                    break;
                }
                for(int i = deltask; i<taskno; i++)
                {
                    task[i] = task[i+1];
                }
                taskno--;
            }
            case 4:

                cout<<"<-------terminating the program------->"<<endl;
                break;

            default :
            cout<<"you entered a invalid task"<<endl; 
        }
    }
     return 0;
}

