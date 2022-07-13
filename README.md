# C1
Write a structure that will store the names, surnames, job tittle, salaries and how many years they have worked in a company for 3 employees. To increase the salary based on how many years they have been working, write a program like the sample output below, and then print all the employees' names, surnames, and their final(new) salaries. The use of Structure array is mandatory
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
