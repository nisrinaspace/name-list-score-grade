#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

struct studentType {
    string firstName;
    string lastName;
    double score;
    char grade;
};

char calculateGrade(double score) {
    if (score >= 90) return 'A';
    else if (score >= 80) return 'B';
    else if (score >= 70) return 'C';
    else if (score >= 60) return 'D';
    else return 'F';
}

int main() {
    studentType s[20] = {
        {"Nisrina", "Ayuni", 96, ' '},
        {"Khawarizmi", "Hikayah", 84, ' '},
        {"Putri", "Awaliah", 73, ' '},
        {"Merisa", "Dwi", 67, ' '},
        {"Winda", "Octavia", 91, ' '},
        {"Devira", "Shafa", 88, ' '},
        {"Nina", "Fadilah", 79, ' '},
        {"Azza", "Nala", 82, ' '},
        {"Marshanda", "Adheisya", 95, ' '},
        {"Alfina", "Dian", 76, ' '},
        {"Widya", "Tri", 89, ' '},
        {"Faiza", "Salsabila", 93, ' '},
        {"Salwa", "Nazhira", 68, ' '},
        {"Nabila", "Ramadhani", 85, ' '},
        {"Aisyah", "Naura", 77, ' '},
        {"Jesica", "Briliani", 81, ' '},
        {"Kalila", "Prianto", 90, ' '},
        {"Fairuz", "Athaya", 72, ' '},
        {"Refa", "Ramadhani", 97, ' '},
        {"Kayyisa", "Nur", 70, ' '}
    };

    double highest = 0;

    for (int i = 0; i < 20; i++) {
        s[i].grade = calculateGrade(s[i].score);
        if (s[i].score > highest)
            highest = s[i].score;
    }

    cout << left << setw(25) << "Name"
         << setw(10) << "Score"
         << setw(10) << "Grade" << endl;
    cout << string(45, '-') << endl;

    for (int i = 0; i < 20; i++) {
        cout << left << setw(25)
             << (s[i].lastName + ", " + s[i].firstName)
             << setw(10) << s[i].score
             << setw(10) << s[i].grade << endl;
    }

    cout << "\nHighest test score: " << highest << endl;
    cout << "Student(s) with the highest score:" << endl;
    for (int i = 0; i < 20; i++) {
        if (s[i].score == highest)
            cout << "  " << s[i].lastName << ", " << s[i].firstName << endl;
    }

    return 0;
}
