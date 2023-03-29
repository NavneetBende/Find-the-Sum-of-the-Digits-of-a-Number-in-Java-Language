# Find-the-Sum-of-the-Digits-of-a-Number-in-Java-Language

Given an input integer as the number, our objective is to break down the number into it’s individual digits and sum them up together. To do so we’ll use the follow two operators,

Modulo Operator % : We’ll use this to extract the digits from the number.
Divide Operator / : We’ll use it to shorten the number by 1 digit.
Once we get the digits, we sum them up one by one with each iteration. Here are some of the methods to solve the above mentioned problem

Method 1: Using Brute Force
Method 2: Using Recursion I
Method 3: Using Recursion II
Method 4: Using ASCII Table
We’ll discuss these methods in the upcoming sections below.

Find the Sum of the Digits of a Number in Java
Method 1: Using Brute Force
Jave Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int num = 12345, sum = 0;



     //loop to find sum of digits
     while(num!=0){
         sum += num % 10;
         num = num / 10;
     }

     //output
       System.out.println ("Sum of digits : " + sum);
   }


 }
Output
15
Method 2: Using Recursion I
Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int num = 12345, sum = 0;
       System.out.println ("Sum of digits : " + getSum (num, sum));
   }

   static int getSum (int num, int sum)
   {

     if (num == 0)
       return sum;

     sum += num % 10;
     return getSum (num / 10, sum);
   }
 }
Output
15
Method 3: Using Recursion II
Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int num = 12345;
       System.out.println ("Sum of digits : " + getSum (num));
   }

   static int getSum (int num)
   {

     if (num == 0)
       return 0;

     return (num % 10) + getSum (num / 10);
   }

 }
Output
15
Method 4: Using ACSII Table
Java Code
Run
public class Main
{
  public static void main (String[]args)
  {

    String num = "9876543219876543219876";
    // you can also use BIGINTEGER in place of string
    // if you have to store a number like this
      System.out.println ("Sum of digits : " + getSum (num));
  }

  static int getSum (String num)
  {
    int sum = 0;

    // Traverse through the whole string(char array)
    for (int i = 0; i < num.length (); i++)
      {
	// Ascii value pf numbers start from 48
	// subtracting 48 will give us value in int
	sum = sum + num.charAt (i) - 48;
      }
    return sum;
  }
}
Output
120
