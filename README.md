### Problem 1 - Remove special characters from a given string and count the number of special characters in the string.

###### Source 
Topic : String  Level : Easy

Tips: Use this replaceAll method and remember this [^a-zA-Z0-9] and replace this with space

Java 8

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


