```csharp
using System;
using System.Collections.Generic;
using System.Linq;

public class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

public class Program
{
    public static void Main()
    {
        List<Student> students = new List<Student>
        {
            new Student { Id = 1, Name = "Triet", Age = 16 },
            new Student { Id = 2, Name = "Nhi", Age = 14 },
            new Student { Id = 3, Name = "Khoa", Age = 18 },
            new Student { Id = 4, Name = "An", Age = 17 },
            new Student { Id = 5, Name = "Nghia", Age = 15 }
        };

        //a.In toàn bộ danh sách học sinh
        Console.WriteLine("Danh sach toan bo hoc sinh:");
        foreach (var student in students)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
        Console.WriteLine();

        //b.Tìm và in ra danh sách các học sinh có tuổi từ 15 đến 18
        var studentsAge15To18 = students.Where(s => s.Age >= 15 && s.Age <= 18).ToList();
        Console.WriteLine("Danh sach hoc sinh có tuoi tu 15 den 18:");
        foreach (var student in studentsAge15To18)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
        Console.WriteLine();

        //c.Tìm và in ra học sinh có tên bắt đầu bằng chữ "A"
        var studentsNameStartingWithA = students.Where(s => s.Name.StartsWith("A")).ToList();
        Console.WriteLine("Danh sach hoc sinh co ten bat dau bang chu 'A':");
        foreach (var student in studentsNameStartingWithA)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
        Console.WriteLine();

        //d.Tính tổng tuổi của tất cả học sinh
        var totalAge = students.Sum(s => s.Age);
        Console.WriteLine($"Tong tuoi cua tat ca hoc sinh: {totalAge}");
        Console.WriteLine();

        //e.Tìm và in ra học sinh có tuổi lớn nhất
        var oldestStudent = students.OrderByDescending(s => s.Age).First();
        Console.WriteLine("Hoc sinh co tuoi lon nhat:");
        Console.WriteLine($"Id: {oldestStudent.Id}, Name: {oldestStudent.Name}, Age: {oldestStudent.Age}");
        Console.WriteLine();

        //f.Sắp xếp danh sách học sinh theo tuổi tăng dần và in ra danh sách sau khi sắp xếp
        var sortedStudents = students.OrderBy(s => s.Age).ToList();
        Console.WriteLine("Danh sach hoc sinh sau khi sap xep theo tuoi tang dan:");
        foreach (var student in sortedStudents)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
    }
}
