# Ex.No:2(A) CLASS AND OBJECT

## QUESTION:
Create a class Person with attributes name and age. Write a method greet() that prints: Hello, my name is <name> and I am <age> years old.

import java.util.Scanner;


## AIM:
To write a Java program that demonstrates the concept of Class and Object using a Person class with attributes and a method.


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class named Person with attributes name and age.
4. Define a method greet() that prints the message using the attributes.
5. In the main() method, create an object of the Person class.
6. Read the name and age values from the user.
7. Call the greet() method using the object.
8. End the program.





## PROGRAM:
 ```
/*
Program to implement a Class and Objects using Java
Developed by: RAMYA S
RegisterNumber:212224040268
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

class prog {
    String name;
    int age;

    prog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void greet() 
    {
        System.out.println("Hello, my name is " + name + " and I am " + age + " years old.");
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
       
        String name = scanner.nextLine(); 
        int age = scanner.nextInt();      

        prog person = new prog(name, age); 
        person.greet(); 

    }


}

```





## OUTPUT:

![Screenshot 2025-11-16 212511](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/f4678ded3f5d700b48ed69952ea8e2696ab06d80/19AI307_JAVA(25-26)/Module-02/DAY-1/Screenshot%202025-11-16%20212511.png)


## RESULT:

Thus, the Java program to implement a Class and Object using a Person class was successfully executed and verified.

# Ex.No:2(B) METHODS

## QUESTION:
Write a method int cube(int x) that calls a method int square(int x) internally to calculate the cube as x * square(x).



## AIM:
To write a Java program that demonstrates calling one method from another method to compute the cube of a number.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a method square(int x) that returns the square of x.
4. Create a method cube(int x) that calls square(x) and returns x * square(x).
5. In the main method, read an integer from the user.
6. Call the cube() method and display the result.
7. Stop the program.





## PROGRAM:
 ```
/*
Program to implement a Methods using Java
Developed by: RAMYA S
RegisterNumber: 212224040268
*/
```

## SOURCE CODE:
```
import java.util.*;
public class Main
{
    static int square(int x)
    {
        return x*x;
    }
    static int cube(int x)
    {
        return x*square(x);
    }
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int num=sc.nextInt();
        int result=cube(num);
        System.out.println(result);
    }
}
```




## OUTPUT:
![java22](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/17d1b46f75f555eafc990d99c8d9e5297e25ca2f/19AI307_JAVA(25-26)/Module-02/DAY-2/java22.png)


## RESULT:
Thus, the Java program to calculate the cube of a number by calling the square method internally was successfully implemented and executed.


# Ex.No:2(C) ACCESS SPECIFIERS

## QUESTION:
Write a Java program to create a class called BankAccount with private instance variables accountNumber and balance. Provide public getter and setter methods to access and modify these variables.

## AIM:
To write a Java program that demonstrates the use of access specifiers, specifically using private for data hiding and public methods to access and modify values.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class BankAccount with private variables accountNumber and balance.
4. Provide public getter and setter methods for both variables.
5. Inside the main method, create an object of BankAccount.
6. Use setter methods to assign values to accountNumber and balance.
7. Display the values using getter methods.
8. Stop the program.





## PROGRAM:
 ```
/*
Program to implement a Access Specifiers using Java
Developed by: RAMYA S
RegisterNumber:212224040268 
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

public class Main 
{
    static class BankAccount 
    {
        private String accountNumber;
        private double balance;
        public String getAccountNumber()
        {
            return accountNumber;
        }
        public void setAccountNumber(String accountNumber) 
        {
            this.accountNumber = accountNumber;
        }
        public double getBalance() 
        {
            return balance;
        }
        public void setBalance(double balance)
        {
            this.balance = balance;
        }
    }

    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        BankAccount account = new BankAccount();
        String accNo = sc.nextLine();
        double bal = sc.nextDouble();
        account.setAccountNumber(accNo);
        account.setBalance(bal);
        System.out.println("Account Number: "+account.getAccountNumber());
        System.out.println("Balance: "+account.getBalance());
    }
}
```







## OUTPUT:

![java23](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/025b00cfa6e057b13e81ffd84dd75ef76213a9db/19AI307_JAVA(25-26)/Module-02/DAY-3/java23.png)

## RESULT:
Thus, a Java program to implement Access Specifiers using private variables with public getter and setter methods was executed successfully.




