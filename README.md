## Interviewers ask these questions frequently, so practice it as many times as you can
### Writer : [CodeXam](https://github.com/Subham-Maity)

### Questions List
   * [Remove special characters](#problem-1---remove-special-characters-from-a-given-string-and-count-the-number-of-special-characters-in-the-string)
   * [String is rotation of another String](#problem-2---check-if-one-string-is-rotation-of-another-string)
   * [Reverse a String.](#problem-3---reverse-a-string)
   * [Reverse a Number](#problem-4---reverse-a-number)
   * [Palindrome](#problem-5---palindrome)
   * [Prime or not (input from the user)](#problem-6---prime-or-not-input-from-the-user)
   * [Leap Year Check](#problem-7---java-program-to-check-leap-year)
   * [find Largest among entered numbers](#problem-8---write-a-program-to-find-largest-among-entered-numbers)
   * [Fibonacci Series](#problem-9---fibonacci-series-using-recursion)

### Problem 1 - Remove special characters from a given string and count the number of special characters in the string.

###### Source 
Topic : String  Level : Easy

Tips: Use this replaceAll method and remember this [^a-zA-Z0-9] and replace this with space

```CodeXam.java```

```java

import java.util.Scanner;
public class CodeXam {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        //str.replaceAll is used to remove special characters from the string and store it in str1 
        String str1 = str.replaceAll("[^a-zA-Z0-9]", ""); 
        System.out.println(str1);
        System.out.println(str.length() - str1.length());
    }
}

```

### Problem 2 - Check if one String is rotation of another String.

###### Source
Topic : String  Level : Easy

Tips: main concept is to concatenate the string with itself and check if the second string is present in the concatenated string or not.

```CodeXam.java```

```java

public class CodeXam {
  public void isRotation(String s1, String s2) {
    //base case
    if (s1.length() != s2.length()) {
      System.out.println("Not a rotation");
      return;
    }

    //concatenate s1 with itself and check if s2 is substring of it
    String s3 = s1 + s1; //waterbottlewaterbottle 
    if (s3.contains(s2)) {//waterbottlewaterbottle.contains(erbottlewat) 
      System.out.println("Rotation");
    } else {
      System.out.println("Not a rotation");
    }
  }


  public static void main(String[] args) {
    CodeXam codeXam = new CodeXam();
    codeXam.isRotation("ABCD", "DCAB");
  }

}
```

### Problem 3 - Reverse a String.

###### Source
Topic : String  Level : Easy

Tips: take a empty string and append the last character of the string and run the loop till the length of the string.



```CodeXam.java```

```java
public class CodeXam{
  public static void main(String[] args) {
    String str = "Hello World";
    String reverse = "";
    for (int i = str.length() - 1; i >= 0; i--) {
      reverse = reverse + str.charAt(i);
    }
    System.out.println("Reversed string is:");
    System.out.println(reverse);


  }
}
```

### Problem 4 - Reverse a Number.

###### Source
Topic : Numeric  Level : Easy
Topic : Numeric  Level : Easy

Tips:
Iteration 1:

```
number = 1234
remainder = 1234 % 10 = 4
reverse = 0 * 10 + 4 = 0 + 4 = 4
number = 1234 / 10 = 123
Now the value of the number and reverse variable is 123 and 4, respectively.
```

Iteration 2:

```
number = 123
remainder = 123 % 10 = 3
reverse = 4 * 10 + 3 = 40 + 3 = 43
number = 123 / 10 = 12
Now the value of the number and reverse variable is 12 and 43, respectively.
```

Iteration 3:

```
number = 12
remainder = 12 % 10 = 2
reverse = 43 * 10 + 2 = 430 + 2 = 432
number = 12 / 10 = 1
Now the value of the number and reverse variable is 1 and 432, respectively.
```

Iteration 4:

```
number = 1
remainder = 1 % 10 = 1
reverse = 432 * 10 + 1 = 4320 + 1 = 4321
number = 1 / 10 = 0
```

```CodeXam.java```

```java
public class CodeXam{
    public static void main(String[] args) {
        int num = 12345;
        int rev = 0;
        while(num != 0) {
            int digit = num % 10;
            rev = rev * 10 + digit;
            num /= 10;
        }
        System.out.println(rev);

   }
}
```

### Problem 5 - Palindrome

###### Source
Topic : String  Level : Easy

Tips: take a empty string and append the last character of the string and run the loop till the length of the string.

```CodeXam.java```

```java
public class CodeXam{
    public static void main(String[] args) {
        String str = "madam";
        String rev = "";
        for (int i = str.length() - 1; i >= 0; i--) {
            rev = rev + str.charAt(i);
        }
        if (str.equals(rev)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not Palindrome");
        }
    }
}
```
### Problem 6 - Prime or not (input from the user)

###### Source
Topic : Numeric  Level : Easy

Tips: 
```java
Takes the number 

For Case 1 number is 6 & For Case 2 number is 7

Take count = 0

When the loop will start, each time we will keep dividing that number from one to the same number. After we have zero remainders, we will increase the count by one

like this :

        Case1 Range (1-6)                                                Case2 Range (1-7)  

Iteration 1: 6 / 1  remainder = 0  count = 1            | Iteration 1:    7 / 1  remainder = 0  count = 1
                                                        |
Iteration 2: 6 / 2  remainder = 0  count = 1+1          | Iteration 2:    7 / 2  remainder = 3  count = 1 
                                                        |
Iteration 3: 6 / 3  remainder = 0  count = 1+1+1        | Iteration 3:    7 / 3  remainder = 1  count = 1
                                                        |      
Iteration 4: 6 / 4  remainder = 2  count = 1+1+1        | Iteration 4:    7 / 4  remainder = 3  count = 1
                                                        |     
Iteration 5: 6 / 5  remainder = 1  count = 1+1+1        | Iteration 5:    7 / 5  remainder = 2  count = 1
                                                        |      
Iteration 6: 6 / 6  remainder = 0  count = 1+1+1+1 = 4  | Iteration 6:    7 / 6  remainder = 1  count = 1
                                                        |        
                                                        | Iteration 7:    7 / 7  remainder = 0  count = 1+1 = 2



Now Check count == 2 

If the count equals 2, then the number is a prime number; otherwise, it is not a prime number  
```

```CodeXam.java```

```java
// Approach 1:
import java.util.Scanner;
class CodeXam {
    public static void main(String[] args) {
        boolean isPrime = false;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter any number to check prime or not:");
        int n = sc.nextInt();
 
        if (n == 1 || n ==0) {
            System.out.println(n + " is not prime number");
        } else {
            for (int i = 2; i <= n / 2; ++i) {
                // condition for non-prime number
                if (n % i == 0) {
                    isPrime = true;
                    break;
 
                }
            }
            if (!isPrime)
                System.out.println(n + " is a prime number.");
            else
                System.out.println(n + " is not a prime number.");
        }
    }
}
 

// Approach 2:
import java.util.Scanner;
public class CodeXam{
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter a number to check prime or not");
    int num = sc.nextInt();
    int count = 0;
    for(int i = 1; i <= num; i++){
      if(num % i == 0){
        count++;
      }
    }
    if(count == 2){
      System.out.println(num + " is a prime number");
    }else{
      System.out.println(num + " is not a prime number");
    }
  }
}
```

### Problem 7 - Java Program to Check Leap Year

###### Source
Topic : Numeric  Level : Easy

Tips:
```java
However, there is still a small error that must be accounted for. To eliminate this error, 
the Gregorian calendar stipulates that a year that is evenly divisible by 100 (for example, 1900)
is a leap year only if it is also evenly divisible by 400.

For this reason, the following years are not leap years:

1700, 1800, 1900, 2100, 2200, 2300, 2500, 2600

This is because they are evenly divisible by 100 but not by 400.

The following years are leap years: 1600, 2000, 2400

This is because they are evenly divisible by both 100 and 400.
```

```CodeXam.java```

```java
//Approach 1
import java.util.Scanner;
public class CodeXam {
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        int year = sc.nextInt();
        if ((year % 400 == 0) || ((year % 4 == 0) && (year % 100 != 0))) {
            System.out.println(year + " : is a leap year");
        }
        else {System.out.println(year + " : is not a leap year.");
        }
    }
}


//Approach 2
import java.util.Scanner;
public class CodeXam {
  public static void main(String[] args)
  {
    int year;
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter a year");
    year = sc.nextInt();
    if (year % 4 == 0)
    {
      if (year % 100 != 0)
      {
        System.out.println("It's a leap year !");
      }
      else if (year % 400 == 0)
      {
        System.out.println("It's a leap year !");
      }
      else
      {
        System.out.println("It's not a leap year");
      }
    }
    else
    {
      System.out.println("It's not a leap year");
    }
  }
}
```
### Problem 8 - Write a Program to find Largest among entered numbers

###### Source
Topic : String  Level : Easy

Tips: Store the number in an array and then compare the numbers in the array to find the largest number.

```CodeXam.java```

```java
import java.util.Scanner;
public class CodeXam {
    public static void main(String[] args){
        int n, max;
       Scanner s = new Scanner(System.in);
       System.out.print("Enter no. of elements you want in array:");
         n = s.nextInt();
        int a[] = new int[n];
       System.out.println("Enter all the elements:");
        for(int i = 0; i < n; i++)
        {
            a[i] = s.nextInt();
        }
        max = a[0];
        for(int i = 0; i < n; i++)
        {
            if(max < a[i])
            {
                max = a[i];
            }
        }
        System.out.println("Maximum value:"+max);
    }
}
```
### Problem 9 - Fibonacci Series using Recursion

###### Source
Topic : Recursion Level : Easy

Tips: 

```java

Supppose we want 7th index position fibonacci so here 7 is our nth postion
        now 13 is the 7th fibonachhi number
        so n = 7 and result will be 13

        explain:

        fib(n-1) means fib(7-1) = fib 6th position index
        so, 6th position index is 8

        fib(n-2) means fib(7-2) = fib 5th position index
        so, 5th position index is 5


        now,
        fib(n-1)+fib(n-2)

        fib(7-1)+fib(7-2)

        8  +  6

        = 13
        
        Tree Visualization:
        
        
                          fib(5) 
                    _______________________
                     /                \
               fib(4)                fib(3)   
             /        \              /       \ 
         fib(3)      fib(2)         fib(2)   fib(1)
        /    \       /    \        /      \
  fib(2)   fib(1)  fib(1) fib(0) fib(1) fib(0)
  /     \
fib(1) fib(0)
Optimized tree for recursion for code above

    fib(5) 

    fib(4)

    fib(3)

    fib(2)

    fib(1)
```

```CodeXam.java```

```java
//Approach 1
public class CodeXam {
    public static int fib(int n) {
        if(n == 1|| n==2)
            return n-1;
        else
            return fib(n-1)+fib(n-2);
    }
    public static void main(String args[]) {
        System.out.println(fib(8));
    }
}

//Approach 2
public class CodeXam {
    public static int fib(int n) {
        if(n == 0||n == 1)
            return n;
        else
            return fib(n-1)+fib(n-2);
    }
    public static void main(String args[]) {
        System.out.println(fib(8));
    }
}
```

