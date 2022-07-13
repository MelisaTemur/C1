# C1
//STRUCTURES IN C
#include <stdio.h>
#include <math.h>

struct Employee {
	int ID;
	char name[100];
	char surname[100];
	char title[100];
	float salary;
	float year;
} e[3];

int main()
{
	int i = 0;

	printf("Enter %d Employees Details\n", (sizeof e / sizeof e[0]));

	for (i = 0; i < (sizeof e / sizeof e[0]); i++)
	{
		printf("Employee %d\n", i + 1);
		printf("Name: ");
		scanf("%s", &e[i].name);
		printf("Surname: ");
		scanf("%s", &e[i].surname);
		printf("Title: ");
		scanf("%s", &e[i].title);
		printf("Salary: ");
		scanf("%f", &e[i].salary);
		printf("Year of Service: ");
		scanf("%f", &e[i].year);
	}

	printf("%d Employees Details with Raise\n", (sizeof e / sizeof e[0]));
	for (i = 0; i < (sizeof e / sizeof e[0]); i++)
	{
		e[i].salary = e[i].salary + (e[i].salary * (e[i].year / 100));
		printf("Name: %s, Surname: %s, New Salary %.lf\n", e[i].name, e[i].surname, e[i].salary);
	}
}
