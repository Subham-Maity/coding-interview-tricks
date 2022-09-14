### Chapters 
* String 
   * [Remove special characters](#problem-1---remove-special-characters-from-a-given-string-and-count-the-number-of-special-characters-in-the-string)
   * [String is rotation of another String](#problem-2---check-if-one-string-is-rotation-of-another-string)

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

