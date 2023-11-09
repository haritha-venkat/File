# File

# Aim:
To write a C# program to store the student details in file using structure concept.

# Algorithm:
## Step 1:
Create a file using FileStream.

## Step 2:
Create a structure for student details.

## Step 3:
Get the number of students and their details from user.

## Step 4:
Define a function to write the details of student into the created file.

## Step 5:
Pass the details of student to the function.

## Step 6:
File has been created and written with student details.
# Program:
NAME: harithashree.v

REG.no.: 212222230046

```python
using System;
using System.IO;
struct student
{
    public string name;
    public int age;
    public string department;
    public int percentage;
};
class HelloWorld
{

    void writer(string name, int age, string department, int percentage, int i)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Append, FileAccess.Write);
        StreamWriter sw = new StreamWriter(fs);
        sw.WriteLine("Name of the student {0} is {1}", i, name);
        sw.WriteLine("Age of the student {0} is {1}", i, age);
        sw.WriteLine("Department of the student {0} is {1}", i, department);
        sw.WriteLine("percentage of the student {0} is {1}", i, percentage);

        sw.Close();
        fs.Close();
    }
    static void Main()
    {
        int n, i;
        FileStream fs = new FileStream("file.txt", FileMode.Create, FileAccess.Write);
        fs.Close();
        Console.WriteLine("Enter the number of Students");
        n = Convert.ToInt32(Console.ReadLine());
        student[] s = new student[n];
        for (i = 0; i < n; i++)
        {
            Console.WriteLine("Enter the name");
            s[i].name = Console.ReadLine();
            Console.WriteLine("Enter the age");
            s[i].age = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Enter the department");
            s[i].department = Console.ReadLine();
            Console.WriteLine("Enter the percentage");
            s[i].percentage = Convert.ToInt32(Console.ReadLine());
            HelloWorld hw = new HelloWorld();
            hw.writer(s[i].name, s[i].age, s[i].department, s[i].percentage, i + 1);
            Console.WriteLine();
        }
    }
}
```

## Output:

![image](https://github.com/haritha-venkat/File/assets/121285701/c00309be-0974-468b-8be5-4c5f53f26bae)


## Result:

Thus a C# program to store the student details in file using structure concept is implemented successfully.

