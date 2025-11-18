# Experiment-4
#include <stdio.h>

struct Employee {
    int id;
    char name[50];
    float salary;
};

int main() {
    int n, i, j;
    struct Employee emp[100], temp;

    printf("Enter number of employees: ");
    scanf("%d", &n);

    // Input employee details
    for(i = 0; i < n; i++) {
        printf("\nEnter details of employee %d:\n", i + 1);
        printf("ID: ");
        scanf("%d", &emp[i].id);
        printf("Name: ");
        scanf("%s", emp[i].name);
        printf("Salary: ");
        scanf("%f", &emp[i].salary);
    }

    // Sort by salary (descending)
    for(i = 0; i < n - 1; i++) {
        for(j = 0; j < n - i - 1; j++) {
            if(emp[j].salary < emp[j + 1].salary) {
                temp = emp[j];
                emp[j] = emp[j + 1];
                emp[j + 1] = temp;
            }
        }
    }

    // Display sorted employee data
    printf("\n---------------------------------------------\n");
    printf("Employee ID\tName\t\tSalary\n");
    printf("---------------------------------------------\n");

    for(i = 0; i < n; i++) {
        printf("%d\t\t%s\t\t%.2f\n", emp[i].id, emp[i].name, emp[i].salary);
    }

    printf("---------------------------------------------\n");

    return 0;
}
