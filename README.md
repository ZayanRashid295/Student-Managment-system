\\ Student-Managment-system
\\The provided code is a C++ program that simulates a simple student management system. here is the provided code.
#include <iostream>
#include <string>
#include <iomanip>
#include<fstream>
#include<stdlib.h>

using namespace std;


class Data {
public:
    string name;
    string login_ID;
    string password;

    void main_data()
    {
        cout << "ENTER NAME : ";
        cin >> name;
        cout << "ENTER ID : ";
        cin >> login_ID;
        cout << "ALLOCATE PASSWORD : ";
        cin >> password;
    }
};


class course_enroll
{
public:
    char attendance;
    int credithours;
    string faculty_name;
    int semester_select;
    string slot;
    char quiz_grade;
    string subject_name;
    char assignment_grade;
   
    int code;
    void data_in()
    {
        cout << "NAME : ";
        cin >> subject_name;
        cout << "CREDIT HOURS : ";
        cin >> credithours;
        cout << "CODE : ";
        cin >> code;
        cout << "FACULTY MEMBER ASSIGNED : ";
        cin >> faculty_name;
    }
    void data_display()
    {
        cout << endl;
        cout << "\nNAME : ";
        cout << subject_name;
        cout << "\nCREDIT HOURS : ";
        cout << credithours;
        cout << "\nCODE : ";
        cout << code;
        cout << "\nFACULTY MEMBER : ";
        cout << faculty_name;
        cout << endl;
    }
};
class Admin : public Data, public course_enroll {
public:
    string sem;
    int semester_selection()
    {
        if (sem == "fall" || sem == "FALL")
        {
            cout << "Fall semesters have been selected" << endl;
            cout << "select semesters : \n1\n3\n5\n7" << endl;
            cout << "enter your selected semester : " << endl;
            cin >> semester_select;

        }
        if (sem == "spring" || sem == "SPRING")
        {
            cout << "spring semesters have been selected" << endl;
            cout << "select semesters : \n2\n4\n6\n8" << endl;
            cout << "enter your selected semester : " << endl;
            cin >> semester_select;

        }
        return semester_select;
    }
    void sem_offer()
    {
        if (sem == "fall" || sem == "FALL")

        {
            for (int x = 0; x < 20; x++)
            {
                cout << "-";
            }
            cout << "SEMESTERS OFFERED : \n1st\n3rd\n5th\n7th\n";
            for (int x = 0; x < 20; x++)
            {
                cout << "-";
            }

        }
        else if (sem == "spring" || sem == "SPRING")
        {
            for (int x = 0; x < 20; x++)
            {
                cout << "-";
            }
            cout << "SEMESTERS OFFERED : \n2nd\n4th\n6th\n8th\n";
            for (int x = 0; x < 20; x++)
            {
                cout << "-";
            }
        }
    }


};


class Student : public Data, public course_enroll {
public:
    int code_course_Selected;
    void enroll_in()
    {
        cout << endl;
        for (int x = 0; x < 20; x++)
        {
            cout << "-";
        }
        cout << endl;
        cout << "\nENTER CODE OF THE COURSE YOU WANT TO ENROLL IN : ";
        cin >> code_course_Selected;
        for (int x = 0; x < 20; x++)
        {
            cout << "-";
        }
    }
    void fee_challan() 
    {
        int tran_fee = 1500;
        int lib_fee = 300;
        int internet = 3000;
        int hos_charges = 29000;
        int ac_fee = 2500 * credithours;
        int t_fee = tran_fee + lib_fee + internet + hos_charges + ac_fee;
        cout << "\nFee Challan for " << name << ":" << endl;
        cout << " Transport Fee  : " << tran_fee << " " << endl;
        cout << " Library Fee  : " << lib_fee << " " << endl;
        cout << " IP Fee : " << internet << " " << endl;
        cout << " Hostel Charges : " << hos_charges << " " << endl;
        cout << " Academic Fee : " << ac_fee << " " << endl;
        cout << " Total Fee : " << t_fee << " " << endl;

    }

};
class Faculty : public Data,public course_enroll
{

};
int quiz = 0, assessment = 0;
int stud = 0, facul = 0;
int a = 0;
int main() {
    int  option, option1, option2, option3, option4, option5;
    Student student;
    course_enroll c1;
    Faculty f1;
    Admin admin;
    bool fac;
    string pass_admin;
    string pass_stud;
    string pass_fac;
    string admin_id;
    string stud_id;
    string faculty_id;
    fstream stud_data;
    fstream course_file;
    fstream fac_data;
    string date;
    int numCourses = 0;
    int choice;
    while (true) {
        cout << endl;
        for (int x = 0; x < 20; x++)
        {
            cout << "-";
        }
        cout << "\nMain Menu:" << endl;
        cout << "1. Student Login" << endl;
        cout << "2. Faculty Login" << endl;
        cout << "3. Admin Login" << endl;
        cout << "4. Faculty Information" << endl;
        cout << "5. Exit" << endl;
        for (int x = 0; x < 20; x++)
        {
            cout << "-";
        }
        cout << "\nEnter your choice: ";
        cin >> choice;
        system("cls");
        switch (choice) {
        case 1:
            int j;

            if (stud == 0)

            {
                cout << "\nNo student has been registered yet\nContact admin" << endl;
            }
            else
            {
                for (j = 0; j < 3; j++)
                {
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }
                    cout << "\nEnter your login ID: ";
                    cin >> stud_id;
                    cout << endl;
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }
                   
                   cout << "\nEnter your password: ";
                   cin >> pass_stud;
                   cout << endl;
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }
                    
                    bool found = false;
                    int index = 0;
                    if (stud_id != student.login_ID || pass_stud != student.password)
                    {
                        cout << "\nInvalid ID or Password\nTry Again"<<endl;
                        continue;
                    }
                    else
                        break;
                }
                if (j == 3)
                {
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }
                    cout << "\nYou have entered wrong Id password three times" << endl;
                    cout << "\nSign up again or contact admin" << endl << "Thank you"<<endl;
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }
                    exit(0);
                }
                else
                {
                    while (true)
                    {
                        for (int x = 0; x < 20; x++)
                        {
                            cout << "-";
                        }

                        cout << "\nYOU HAVE LOGGED IN AS A STUDENT\n";
                        for (int x = 0; x < 20; x++)
                        {
                            cout << "-";
                        }
                        cout << "\nPRESS 1 TO ENROLL IN A COURSE.\nPRESS 2 TO VIEW FEE CHALLAN.\nPRESS 3 TO VIEW ATTENDANCE.\nPRESS 4 TO VIEW MARKS.\nPRESS 5 TO RETURN TO MAIN MENU.   :" << endl;
                        for (int x = 0; x < 20; x++)
                        {
                            cout << "-";
                        }
                        cout << "\nenter your choice : ";
                        cin >> option;
                        system("cls");
                        if (option == 1)
                        {
                            c1.data_display();
                            student.enroll_in();
                            if (student.code_course_Selected == c1.code)
                            {
                                for (int x = 0; x < 20; x++)
                                {
                                    cout << "-";
                                }
                                cout << "\nCourse enrolled" << endl;
                                for (int x = 0; x < 20; x++)
                                {
                                    cout << "-";
                                }

                           cout<<"\nCourse name is " << c1.subject_name<<endl;
                                a++;
                                break;
                            }
                        }
                        else if (option == 2)
                        {
                            student.fee_challan();
                        }
                        else if (option == 3)
                        {
                            for (int x = 0; x < 20; x++)
                            {
                                cout<<"-";
                            }
                            cout << "\nYour attendance for course " << c1.subject_name <<" on date "<<date<<" is " << c1.attendance << endl;
                            for (int x =0 ; x < 20 ; x++)
                            {
                                cout << "-";
                            }
                            break;
                        }
                        else if (option == 4)
                        {
                            string check;
                            cout << "\nYou want to check grades of quiz or assignment:";
                            cin >> check;
                            if (check == "quiz")
                            {
                                cout << "your grade for quiz # " << quiz << " is " << c1.quiz_grade << endl;
                            }
                            else if (check == "assignment")
                            {
                                cout << "your grade for assignment # " << assessment << " IS " << c1.assignment_grade << endl;
                            }
                        }
                        else if (option == 5)
                        {
                            break;
                        }

                    }
                }
            }
            break;

        case 2:
            int facultyChoice;
           if(facul>0) 
           {
                int x;
                for (x = 0; x < 3; x++)
                {

                    cout << "Enter your login ID: ";
                    cin >> faculty_id;
                    cout << "Enter your password: ";
                    cin >> pass_fac;
                    if (faculty_id != f1.login_ID || pass_fac != f1.password)
                    {
                        cout << "WRONG ID OR PASSWORD.TRY AGAIN.\n";
                        continue;
                    }
                    else
                        break;
                }
                if (x == 3)

                {
                    cout << "YOU HAVE ENTERED WRONG PASSWORD THREE TIMES!";
                    cout << "\nLOGIN AGAIN TO ENTER AS A FACULTY MEMBER OR CONTACT ADMIN\n";

                    exit(0);
                }
                else
                {
                    bool found = false;
                    int index = 0;
                    cout << "\nFaculty Menu:" << endl;
                    cout << "1. See students enrolled in course." << endl;
                    cout << "2. Mark Attendance" << endl;
                    cout << "3. Create quiz or assignment" << endl;
                    cout << "4. Mark quiz or assignment" << endl;
                    cout << "5. Return to Main Menu" << endl;
                    cout << "Enter your choice: ";
                    cin >> facultyChoice;
                    system("cls");
                    if (facultyChoice == 1)
                    {
                        if (c1.faculty_name == f1.name)
                        {
                            if (a == 0)
                                cout << "No student enrolled yet" << endl;
                            else
                                cout << "Student enrolled in " << c1.subject_name << " is " << student.name;
                        }
                        break;
                    }

                    else if (facultyChoice == 2)
                    {
                        cout << "enter the attendance for the student" << endl;
                        cout << "enter date(mm/dd/yy)format : ";
                        cin >> date;
                        cin.ignore(3);
                        cout << "enter slot : " << endl;
                        cin >> c1.slot;
                        cout << "Mark attendance " << endl;
                        cout << "enter P for present and A for absent" << endl;
                        cin >> c1.attendance;
                        course_file.open("course.txt", ios::out | ios::app);
                        if (!course_file)
                        {
                            cout << "SORRY" << endl;
                            cout << "FILE CREATION FAILED" << endl;
                        }
                        else
                        {
                            cout << "CONGRATULATION!" << endl;
                            cout << "FILE CREATED SUCCESSFULLY" << endl;
                            course_file << c1.slot << endl << c1.attendance << endl;
                            course_file.close();
                        }
                        break;
                    }
                    else if (facultyChoice == 3)
                    {
                        cout << "What do you want to create?" << endl;
                        cout << "Press 1 for creating Quiz and 2 for creating Assignment\n";
                        cout << "Enter your choice : ";
                        cin >> option1;
                        switch (option1)
                        {
                        case 1:
                        {
                            quiz++;
                            cout << "Quiz no. " << quiz << "created successfully";
                        }
                        break;
                        case 2:
                        {
                            assessment++;
                            cout << "Assignment # " << assessment << "Created successfully" << endl;
                        }
                        break;
                        }
                    }

                    else if (facultyChoice == 4)
                    {
                        cout << "Press\n1 to mark quiz\n2 to mark assignment" << endl;
                        cout << "enter your choice : ";
                        cin >> option4;
                        switch (option4)
                        {
                        case 1:

                            if (quiz == 0)
                                cout << "no quiz created yet" << endl;
                            else
                            {

                                cout << "enter grade for quiz # " << quiz << endl;
                                cin >> c1.quiz_grade;
                                
                                course_file.open("course.txt", ios::out | ios::app);
                                if (!course_file)
                                    cout << "FILE CREATION FAILED.\n";
                                else
                                {
                                    cout << "FILE CREATED SUCESSFULLY.\n";
                                    course_file << c1.quiz_grade << endl;
                                    course_file.close();
                                }
                            }

                            break;
                        case 2:


                            if (assessment == 0)
                                cout << "NO ASSIGNMENT IS YET CREATED.\n";
                            else
                            {
                                cout << "enter grade for assignment # " << assessment << " OF " << student.name << "   :   ";
                                cin >> c1.assignment_grade;
                                
                                course_file.open("course.txt", ios::out);
                                if (!course_file)
                                    cout << "FILE CREATION FAILED.\n";
                                else
                                {
                                    cout << "FILE CREATED SUCESSFULLY.\n";
                                    course_file << c1.assignment_grade << endl;
                                    course_file.close();
                                }
                            }

                        }
                    }
                    else if (facultyChoice == 5)
                    {
                        break;
                    }


                    else
                    {
                        cout << "Invalid login ID or password. Please try again." << endl;

                    }

                }

            }
            else
                cout << "\nno faculty member added yet.contact admin" << endl;
            break;
        case 3:
            int ad_choice;
            cout << "Enter your login ID: ";
            cin >> admin_id;
            cout << "Enter your password: ";
            cin >> pass_admin;
            if (admin_id == "admin1" && pass_admin == "admin123")
            {
                while (1) {
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }cout << "\nYou logged in as an ADMIN\n";
                    for (int x = 0; x < 20; x++)
                    {
                        cout << "-";
                    }
                    cout << "\nMenu:" << endl;
                    cout << "Press\n";
                    cout << "1. Offer Semester" << endl;
                    cout << "2. Enter Student Data" << endl;
                    cout << "3. Add Faculty" << endl;
                    cout << "4. Create Courses" << endl;
                    cout << "5. Offer Courses" << endl;
                    cout << "6. Return to Main Menu" << endl;
                    cout << "Enter your choice: ";
                    cin >> ad_choice;
                    system("cls");
                    if (ad_choice == 1)
                    {
                        cout << "OFFER SEMESTER(fall or spring)" << endl;
                        cin >> admin.sem;
                        admin.semester_selection();

                    }
                    else if (ad_choice == 2)
                    {

                        cout << "ENTER STUDENT'S DATA : \n";
                        student.main_data();
                        stud++;
                        stud_data.open("student.txt", ios::out);
                        if (!stud_data)
                            cout << "FILE CREATION FAILED.\n";
                        else
                        {
                            cout << "FILE CREATED SUCESSFULLY.\n";
                            stud_data << student.login_ID << endl;
                            stud_data << student.password << endl;
                            stud_data << student.name << endl;
                            stud_data.close();
                        }

                    }
                    else if (ad_choice == 3)
                    {
                        
                        cout << "ENTER FACULTY MEMBER'S DATA : \n";
                        f1.main_data();
                        facul++;
                        fac_data.open("faculty.txt", ios::out);
                        if (!fac_data)
                            cout << "FILE CREATION FAILED.\n";
                        else
                        {
                            cout << "FILE CREATED SUCESSFULLY.\n";
                            fac_data << f1.login_ID << endl;
                            fac_data << f1.password << endl;
                            fac_data << f1.name << endl;
                            fac_data.close();

                        }
                    }
                    else if (ad_choice == 4)
                    {
                        cout << "ENTER COURSE DETAILS : \n";
                        c1.data_in();
                        course_file.open("courses.txt", ios::out);
                        if (!course_file)
                            cout << "FILE CREATION FAILED.\n";
                        else
                        {
                            cout << "FILE CREATED SUCESSFULLY.\n";
                            course_file << c1.subject_name << endl;
                            course_file << c1.credithours << endl;
                            course_file << c1.code << endl;
                            course_file << c1.faculty_name << endl;
                            course_file.close();
                        }
                    }
                    else if (ad_choice == 5)
                    {
                        c1.data_display();

                    }
                    else if (ad_choice == 6)
                    {
                        break;
                    }
                }
            }
            break;
        case 4:

            if (facul == 0) {
                cout << "No faculty members yet. Please contact the admin to assign faculty members." << endl;
            }
            else
            {
                cout << "Faculty has been recorded" << endl;
                cout <<"Faculty Name : "<< f1.name << endl;
                cout << "Faculty Login Id : "<<f1.login_ID << endl;
            }
            break;


        case 5:
            cout << "Exiting program..." << endl;
            exit(0);

        default:

            cout << "Invalid choice. Please try again." << endl;
            continue;

        }

    }

    return 0;
}

