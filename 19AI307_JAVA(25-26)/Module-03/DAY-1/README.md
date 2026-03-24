# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
A jewelry store tracks gold rates for different types of customers. The base class is Customer with attributes like customerId, name, and purchaseWeight (in grams). There are two types of customers: RegularCustomer and PremiumCustomer. RegularCustomer gets a fixed discount of 2% on the gold rate per gram. PremiumCustomer gets a 5% discount plus a special cashback. The base gold rate per gram is input at runtime. For each customer, calculate the final price they pay:

## AIM:
To write a Java program demonstrating Inheritance and Aggregation by creating subclasses for different customer types and applying different pricing policies using inheritance.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a base class Customer with attributes customerId, name, and purchaseWeight.
4. Create two derived classes: RegularCustomer and PremiumCustomer extending Customer.
5. Implement a method in both subclasses to calculate the final price after discounts.
6. Input base gold rate per gram using Scanner in the main method.
7. Create customer objects and calculate final price.
8. Display results.
9. Stop the program.

## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: RAMYA S
RegisterNumber: 212224040268
*/
```

## SOURCE CODE:
```
import java.util.*;
import java.text.DecimalFormat;

class Customer {
    String customerId, name;
    double purchaseWeight, goldRatePerGram;

    Customer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        this.customerId = customerId;
        this.name = name;
        this.purchaseWeight = purchaseWeight;
        this.goldRatePerGram = goldRatePerGram;
    }

    double getDiscountRate() {
        return 0;
    }

    double calculateFinalPrice() {
        double discountAmount = goldRatePerGram * getDiscountRate() / 100;
        double effectiveRate = goldRatePerGram - discountAmount;
        return purchaseWeight * effectiveRate;
    }

    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: General");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
    }
}

class RegularCustomer extends Customer {
    RegularCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 2;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Regular");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
    }
}

class PremiumCustomer extends Customer {
    PremiumCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 5;
    }

    double calculateCashback() {
        return calculateFinalPrice() * 0.01;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Premium");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
        System.out.println("Cashback: " + df.format(calculateCashback()));
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String type = sc.nextLine().trim();
        String id = sc.nextLine().trim();
        String name = sc.nextLine().trim();
        double weight = sc.nextDouble();
        double goldRate = sc.nextDouble();

        Customer c;
        if (type.equalsIgnoreCase("Regular"))
            c = new RegularCustomer(id, name, weight, goldRate);
        else
            c = new PremiumCustomer(id, name, weight, goldRate);

        c.display();
    }
}
```
## OUTPUT:
![java31](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/14dc8b0a86e753d5e3ad7f7ea47059065871c1c7/19AI307_JAVA(25-26)/Module-03/DAY-1/java31.png)


## RESULT:
Thus, the Java program demonstrating Inheritance and Aggregation using customer types with different discount calculations was successfully executed.

# Ex.No:3(b) POLYMORPHISM

## QUESTION:
Write a Java program using method overriding. Create a superclass Bank with a method getInterestRate() returning 0. Create subclasses SBI, ICICI, and HDFC that override the method.

## AIM:
To write a Java program demonstrating runtime polymorphism using method overriding, where subclasses override a method of the superclass to provide specific implementation.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a superclass Bank with a method getInterestRate() returning 0.
4. Create subclasses SBI, ICICI, and HDFC that override the method to return different interest rates.
5. In the main() method, accept bank name at runtime.
6. Create an object of the appropriate subclass based on the input.
7. Call the overridden method using a reference of type Bank.
8. Display the interest rate.
9. End the program.

## PROGRAM:
 ```
/*
Program to implement a Polymorphism using Java
Developed by: RAMYA S
RegisterNumber: 212224040268
*/
```

## SOURCE CODE:
```
import java.util.*;
class Bank {
    double getInterestRate() {
        return 0;
    }
}

class SBI extends Bank {
    @Override
    double getInterestRate() {
        return 6.5;
    }
}

class ICICI extends Bank {
    @Override
    double getInterestRate() {
        return 7.0;
    }
}

class HDFC extends Bank {
    @Override
    double getInterestRate() {
        return 7.5;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String bankName = sc.nextLine().trim();
        Bank bank;
        if (bankName.equalsIgnoreCase("SBI")) {
            bank = new SBI();
            System.out.println("SBI Rate: " + bank.getInterestRate() + "%");
        } else if (bankName.equalsIgnoreCase("ICICI")) {
            bank = new ICICI();
            System.out.println("ICICI Rate: " + bank.getInterestRate() + "%");
        } else if (bankName.equalsIgnoreCase("HDFC")) {
            bank = new HDFC();
            System.out.println("HDFC Rate: " + bank.getInterestRate() + "%");
        } else {
            System.out.println("Invalid bank name.");
        }
    }
}
```





## OUTPUT:

![java32](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/508d76d2dc9f661dc9ddb5bb22d00b081114519e/19AI307_JAVA(25-26)/Module-03/DAY-2/java32.png)


## RESULT:

Thus, the Java program demonstrating Polymorphism using Method Overriding was successfully executed.

