#  Exception Handling Execution

This program is a school assignment designed to execute exception handling in Java(OOP).

## How it works
The program includes a method for each exception, with user prompts and proper handling using try-catch blocks. 
 
 * It covers various types of exceptions, including IO exceptions, runtime exceptions, and custom simulations.
   
1.IOException: Simulates reading a non-existent file.

```java
public class simulateIOException {
private static void simulateIOException() {
  Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a filename to read (non_existent_file.txt): ");
        String filename = scanner.nextLine();
        try {
            BufferedReader reader = new BufferedReader(new FileReader(filename));
            reader.readLine();
        } catch (IOException e) {
            System.out.println("IOException caught: " + e.getMessage());
        }
    }
}


2.FileNotFoundException: Demonstrates a specific exception when a file is missing.
```java
public class simulateFileNotFoundException {
   private static void simulateFileNotFoundException() {
    Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a filename to open (non_existent_file.txt): ");
        String filename = scanner.nextLine();
        try {
            FileInputStream fis = new FileInputStream(filename);
        } catch (FileNotFoundException e) {
            System.out.println("FileNotFoundException caught: " + e.getMessage());
        }
    }

}

3.EOFException: Handles attempts to read beyond the content of a file.
```java
public class simulateEOFException {
  private static void simulateEOFException() {
    Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a filename to read integers (empty_file.txt): ");
        String filename = scanner.nextLine();
        try (DataInputStream dis = new DataInputStream(new FileInputStream(filename))) {
            while (true) {
                dis.readInt();
            }
        } catch (EOFException e) {
            System.out.println("EOFException caught: End of file reached");
        } catch (IOException e) {
            System.out.println("IOException caught: " + e.getMessage());
        }
    }

}


4.SQLException: Simulates a database connection error.
```java
public class simulateSQLException {
  private static void simulateSQLException() {
        // Database connection simulation
        System.out.println("Simulating SQLException (no actual DB connection).");
        try {
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/non_existent_db", "user", "password");
        } catch (SQLException e) {
            System.out.println("SQLException caught: " + e.getMessage());
        }
    }

}


5.ClassNotFoundException: Simulates a failure to load a class at runtime.
```java
public class simulateClassNotFoundException {
  private static void simulateClassNotFoundException() {
    try {
        Class.forName("com.nonexistent.ClassName");
    } catch (ClassNotFoundException e) {
        System.out.println("ClassNotFoundException caught: " + e.getMessage());
    }
}

}

6.ArithmeticException: Handles division by zero scenarios.
```java
public class simulateArithmeticException {
   private static void simulateArithmeticException() {
    Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Enter a number to divide 10 by: ");
            int divisor = scanner.nextInt();
            int result = 10 / divisor;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("ArithmeticException caught: " + e.getMessage());
        } catch (InputMismatchException e) {
            System.out.println("InputMismatchException caught: Please enter a valid integer.");
            scanner.next(); // Clear the invalid input
        }
    }

}

7.NullPointerException: Simulates accessing a method on a null reference.
```java
public class simulateNullPointerException {
  private static void simulateNullPointerException() {
    try {
        String str = null;
        System.out.println(str.length());
    } catch (NullPointerException e) {
        System.out.println("NullPointerException caught: " + e.getMessage());
    }
}

}

8.ArrayIndexOutOfBoundsException: Manages invalid array index access.
```java
public class simulateArrayIndexOutOfBoundsException {
  private static void simulateArrayIndexOutOfBoundsException() {
    Scanner scanner = new Scanner(System.in);

        try {
            int[] arr = new int[5];
            System.out.print("Enter an index to access (0-4): ");
            int index = scanner.nextInt();
            System.out.println(arr[index]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBoundsException caught: " + e.getMessage());
        } catch (InputMismatchException e) {
            System.out.println("InputMismatchException caught: Please enter a valid integer.");
            scanner.next(); // Clear the invalid input
        }
    }

}

9.ClassCastException: Demonstrates type casting errors.
```java
public class simulateClassCastException {
  private static void simulateClassCastException() {
    try {
        Object obj = Integer.valueOf(10);
        String str = (String) obj;
    } catch (ClassCastException e) {
        System.out.println("ClassCastException caught: " + e.getMessage());
    }
}

}

10.IllegalArgumentException: Handles invalid arguments passed to a method.
```java
public class simulateIllegalArgumentException {
  private static void simulateIllegalArgumentException() {
    try {
        Thread.sleep(-1);
    } catch (IllegalArgumentException e) {
        System.out.println("IllegalArgumentException caught: " + e.getMessage());
    } catch (InterruptedException e) {
        System.out.println("InterruptedException caught: " + e.getMessage());
    }
}

}

11.NumberFormatException: Catches invalid string-to-integer conversions.
```java
public class simulateNumberFormatException {
  private static void simulateNumberFormatException() {
    Scanner scanner = new Scanner(System.in);

    try {
        System.out.print("Enter a string to convert to an integer: ");
        String input = scanner.next();
        int num = Integer.parseInt(input);
    } catch (NumberFormatException e) {
        System.out.println("NumberFormatException caught: " + e.getMessage());
    }
}

}


## where to find the main code

The main method sequentially calls these simulation methods to execute handling various exceptions. This is located in the file I shared above.


