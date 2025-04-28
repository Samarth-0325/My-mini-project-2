# My-mini-project-2

#include <iostream>
#include <string>
#include <map>

using namespace std;

char calculateGrade(int marks)
{

    if (marks >= 60)
        return 'A';

    else if (marks >= 50)
        return 'B';

         else if (marks >= 40)
          return 'C';
         

    else if (marks >= 30)
        return 'D';

    else if (marks >= 23)
        return 'E';

    else
        return 'F';
}

void studentgradesystem() {
    string studentName;
    cout << "Enter Student Name :";
    getline(cin,studentName);

    int totalnumberofSub = 5;

    map<string, float > studentmarks;
    string subname;
    float submarks;
    float totalmarks = 0;

    for(int x = 0; x < totalnumberofSub; x++) {
        cout << endl;
        cout << "Enter Subject name :";
        cin>>subname;
        cout << "Enter Subject marks :";
        cin>>submarks;
        studentmarks[subname] = submarks;
        totalmarks += submarks;
    }

    cout <<"/n----------------------------" << endl;
    cout << "student Result :- " << endl;
    for(auto sub : studentmarks){
        cout << sub.first << " : " << sub.second << " --->" << calculateGrade (sub.second) << endl;
    }

    cout << "Total Marks : " << totalmarks << endl;
}

int main() {
    studentgradesystem();
    cout << endl;
    return 0;
}
