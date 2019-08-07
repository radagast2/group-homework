# 学生信息管理系统

学生信息管理系统可以录入学生的姓名，性别，年龄，出生日期以及成绩，并为他们安排学号，根据姓名以及学号更改信息。


## 1.使用方式
进入Visual Studio打开代码，运行程序出现如下界面

![ 初始界面](denglu.png "登录界面")

输入0,1,2,可分别进行信息查看，信息录入与信息修改，操作结束后输入3退出系统

## 2.未来版本预期

1.加入更多信息，并能够更加灵活地对信息进行修改  
2.加入学生查找功能，根据某一类信息查找学生  
3.制作便于使用的页面

## 3.代码

主体部分  

```
namespace PrintStuXinXI
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("**************欢迎来到学生管理系统***************");

            EXE e = new EXE();
            string str = "";
            while (str != "end")
            {
                Console.WriteLine("-----请选择-----");
                Console.WriteLine("0-> 查看信息");
                Console.WriteLine("1-> 新增学生");
                Console.WriteLine("2-> 修改信息");
                Console.WriteLine("3-> 退出系统");
                switch (Console.ReadLine())
                {
                    case "0":
                        e.exe0();
                        break;
                    case "1":
                        Console.WriteLine();

                        e.exe1();
                        break;
                    case "2":
                        Console.WriteLine("开始修改：");
                        e.exe2();
                        break;
                    default:
                        Console.WriteLine("退出系统成功！");
                        str = "end";
                        break;

                }
            }

        }
    }
```
查看部分
```
public class EXE
    {
        List<Student> Students = new List<Student>();
        List<Student> students = new List<Student>();
        #region 新增
        public void exe0()
        {
            Console.WriteLine("");
            Console.WriteLine("");
            Console.WriteLine("姓名\t性别\t年龄\t出生日期\t成绩");
            foreach (var item in students)
            {
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}\t{5}", item.StuName, item.StuSex, item.StunAge, item.Studate, item.Sorce);
            }

            // return students;
        }
```
录入部分
```
        public void exe1()
        {


            int i = 1;
            string str = "";
            while (str != "ok")
            {
                Console.WriteLine("请输入第{0}个学生的姓名：", i);
                string name = Console.ReadLine();
                Console.WriteLine("请输入第{0}个学生的性别：", i);
                string sex = Console.ReadLine();
                Console.WriteLine("请输入第{0}个学生的年龄：", i);
                string age = Console.ReadLine();
                Console.WriteLine("请输入第{0}个学生的出生日期：", i);
                string date = Console.ReadLine();
                Console.WriteLine("请输入第{0}个学生的成绩：", i);
                string sorce = Console.ReadLine();
                Students.Add(new Student { StuName = name, StuSex = sex, StunAge = age, Studate = date, Sorce = sorce });
                i = i + 1;
                Console.WriteLine("输入 ok 停止新增，按空格键继续。。");
                str = Console.ReadLine();
            }
        

            for (int z = 0; z < Students.Count; z++)
            {
                students.Add(new Student { StuName = Students[z].StuName, StuSex = Students[z].StuSex, StunAge = Students[z].StunAge, Studate = Students[z].Studate, Sorce = Students[z].Sorce });
            }
            Console.WriteLine("");
            Console.WriteLine("");
            Console.WriteLine("姓名\t性别\t年龄\t出生日期\t成绩");
            foreach (var item in students)
            {
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}\t{5}", item.StuName, item.StuSex, item.StunAge, item.Studate, item.Sorce);
            }

            
        }
```
## 4.作者
电气1703   左运扬  
U201711701

 