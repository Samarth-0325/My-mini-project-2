# My-mini-project-2

 #include <iostream>
#include <string>
#include <vector>
using namespace std; 

class subject {
    public:
    string subjectname;
    int credit;
    float gradepoint;

    //contructor
    subject(string name, int cr, int gp)
    {
        subjectname=name;
        credit = cr;
        gradepoint = gp;
    }

};

class student{
    public:
    string name;
    vector<subject>subjects;
    //constructor
 
    student(string studentname)
    {
        name=studentname;
    }
    void addSubject(string subjectName, int credit, float gradepoint)
    {
        subject newsubject(subjectName, credit, gradepoint);
        subjects.push_back(newsubject);
    }  float calculatecgpa()
    {
        int totalcredit=0;
        float weightgradepoint;

        for (const subject & subject : subjects)
        {
            totalcredit+=subject.credit;
            weightgradepoint+=subject.credit*subject.gradepoint;
        }
        return (totalcredit>0)?(weightgradepoint/totalcredit):0;
    }

    void displaycgpa()
    {
        cout << "student Name " << name << endl;
        float cgpa=calculatecgpa();
        cout << "CGPA c" << cgpa << endl;
    }
   // void addSubject(string subjectname, int credits, float gradepoint);
    
};


int main (){

    string studentname;
    int numsub;

    cout << "Enter the name of student ";
    getline (cin,studentname);

    cout << "Enter the number of subjects ";
    cin >> numsub;
    student student(studentname);

    for(int i = 0; i < numsub; i++)
{
    string subjectname;
    int credit;
    float gradepoint;

    cout << "Enter the subject name ";

    cin.ignore();

    getline(cin,subjectname);

    cout << "Enter the credit ";
    cin >> credit;

    cout << "Enter the Gradepoint ";
    cin >> gradepoint; 
    student.addSubject(subjectname, credit, gradepoint);

    
}
student . displaycgpa ();



    return 0;
}
