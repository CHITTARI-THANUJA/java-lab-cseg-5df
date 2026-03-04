java-lab-cseg-5df
experiments
## Experiment 1
## Title:1a(Implementation of Default Primitive Datatype)
```
class DefaultPrimitiveType {
    byte primbyte;
    short primshort;
    int primint;
    double primdouble;
    char primchar;
    float primfloat;
    long primlong;
    boolean primboolean;
    public static void main(String args[]) {
        DefaultPrimitiveType dDpt = new DefaultPrimitiveType();
        System.out.println("default value of byte:" + dDpt.primbyte);
        System.out.println("default value of short:" + dDpt.primshort);
        System.out.println("default value of int:" + dDpt.primint);
        System.out.println("default value of double:" + dDpt.primdouble);
        System.out.println("default value of char:" + dDpt.primchar + " '");
        System.out.println("default value of float:" + dDpt.primfloat);
        System.out.println("default value of long:" + dDpt.primlong);
        System.out.println("default value of boolean:" + dDpt.primboolean);
    }
}
```
## output:
![Output for 1a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/9dc3d2805e45b352b8553890a19e59ea6e9786f1/1a.png)

## Title:1b(Implementation of Quadratic Equation)
```
import java.util.Scanner;

public class QuadraticEquationSolution {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter value of a: ");
        double a = sc.nextDouble();

        System.out.print("Enter value of b: ");
        double b = sc.nextDouble();

        System.out.print("Enter value of c: ");
        double c = sc.nextDouble();

        double D = b * b - 4 * a * c;   // Discriminant

        if (D > 0) {
            System.out.println("Roots are real and distinct");

            double root1 = (-b + Math.sqrt(D)) / (2 * a);
            double root2 = (-b - Math.sqrt(D)) / (2 * a);

            System.out.println("Root 1 = " + root1);
            System.out.println("Root 2 = " + root2);

        } else if (D == 0) {
            System.out.println("Roots are real and equal");

            double root = -b / (2 * a);
            System.out.println("Root = " + root);

        } else {
            System.out.println("Roots are complex");

            double realPart = -b / (2 * a);
            double imaginaryPart = Math.sqrt(-D) / (2 * a);

            System.out.println("Root 1 = " + realPart + " + " + imaginaryPart + "i");
            System.out.println("Root 2 = " + realPart + " - " + imaginaryPart + "i");
        }

        sc.close();
    }
}
```
## Output:
![Output for 1b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/652b7e1c8134feb0718080b0124e4969990b20a2/1b.png)
## Experiment 2
## Title 2a:(Implement class Mechanism):
```
public class Rectangle{
        double length;
        double breadth;
        double area(){
                return length*breadth;
        }
        double perimeter(){
                return 2*(length+breadth);
        }
}
public class Main{
        public static void main(String[] args){
                Rectangle rect=new Rectangle();
                rect.length=10;
                rect.breadth=30;
                System.out.println("Area of Rectangle:"+(rect.area()));
                System.out.println("Perimter of Rectangle:"+(rect.perimeter()));
        }
}
```
## Output:
![Output for 2a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/2a.png)
## Title 2b(Implement Method Overloading):
```
class Sum{
        int add(int a,int b)
        {
                return a+b;
        }
        int add(int a,int b,int c)
        {
                return a+b+c;
        }
        double add(double a,double b)
        {
                return a+b;
        }
}
class Main{
        public static void main(String[] args){
                Sum s=new Sum();
                System.out.println("Sum of 2 integers:"+s.add(30,40));
                System.out.println("Sum of 3 integers:"+s.add(30,40,50));
                System.out.println("Sum of 2 real integers:"+s.add(30.55,40.4));
        }
}
```
## Output:
![Output for 2b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/2b.png)
## Title 2c(Implement Constructor):
```
class Student{
        String name;
        int age;
        double marks;
        Student(String name,int age,double marks){
                this.name=name;
                this.age=age;
                this.marks=marks;
        }
        void display(){
                System.out.println("Student name:"+name);
                System.out.println("Age:"+age);
                System.out.println("Marks:"+marks);
        }
        public static void main(String[] args){
                Student std=new Student("Rahul",29,80.9);
                std.display();
        }
}
```
## Output:
![Output for 2c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/2c.png)
## Additional Experiment 2
```
import java.util.Scanner;

class Fibonacci {

    int firstnumber;
    int secondnumber;
    int thirdnumber;
    int sum;
    int sizeOfFibsequence;

    // Constructor
    Fibonacci(int size) {
        firstnumber = 0;
        secondnumber = 1;
        thirdnumber = 0;
        sum = 0;
        sizeOfFibsequence = size;
    }

    void generateFibsequence() {

        while (sizeOfFibsequence > 0) {

            if (sizeOfFibsequence == 1)
                System.out.print(firstnumber + ".");
            else
                System.out.print(firstnumber + ", ");

            sizeOfFibsequence--;

            sum += firstnumber;

            thirdnumber = firstnumber + secondnumber;
            firstnumber = secondnumber;
            secondnumber = thirdnumber;
        }
    }

    int getFibsum() {
        return sum;
    }
}

public class Main {
    public static void main(String[] args) {

        System.out.print("Enter size of FibSequence: ");
        Scanner sc = new Scanner(System.in);

        int size = sc.nextInt();

        if (size > 0) {

            Fibonacci fib = new Fibonacci(size);

            System.out.println("\nFibonacci Series are:");
            fib.generateFibsequence();

            System.out.println("\nThe sum of Fibonacci Series: " + fib.getFibsum());
        } else {
            System.out.println("Fibonacci Sequence & sum cannot be calculated");
        }

        sc.close();
    }
}
```
## Output:
![Output for Additional Experiment 2](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/b2297a6e9dde4434c41f5386136ee27699bb0238/additional_2.jpg)
## Experiment 3
## Title 3a(Implement Constructor Overloading):
```
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.display();

        Student s2 = new Student("Thanuja", 19, 60);
        s2.display();
    }
}
class Student {
    String name;
    int age;
    double marks;

    Student() {
        name = "Not Assigned";
        age = 0;
        marks = 0.0;
    }

    Student(String name, int age, double marks) {
        this.name = name;
        this.age = age;
        this.marks = marks;
    }

    void display() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Marks: " + marks);
    }
}
```
## Output:
![Output for 3a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/3a.png)
## Title 3b(Implement Binary Search Mechanism):
```
class BinarySearch {
    int[] list;
    int size;

    BinarySearch(int size) {
        this.size = size;
        list = new int[size];
    }

    void setList() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter elements in ascending order:");
        for (int i = 0; i < size; i++) {
            list[i] = sc.nextInt();
        }
    }

    void getList() {
        System.out.print("List elements: ");
        for (int i = 0; i < size; i++) {
            System.out.print(list[i] + " ");
        }
        System.out.println();
    }

    int binarySearch(int key) {
        int low = 0, high = size - 1;

        while (low <= high) {
            int mid = (low + high) / 2;

            if (list[mid] == key)
                return mid;
            else if (list[mid] < key)
                low = mid + 1;
            else
                high = mid - 1;
        }
        return -1;
    }
}
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter size of list: ");
        int size = sc.nextInt();
        BinarySearch b = new BinarySearch(size);
        b.setList();
        b.getList();

        System.out.print("Enter key to search: ");
        int key = sc.nextInt();

        int index = b.binarySearch(key);

        if (index == -1)
            System.out.println("Key item does not exist");
        else
            System.out.println("Key item exists at position: " + index);
    }
}
```
## Output:
![Output for 3b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/3b.png)
## Title 3c(Implement Bubble sort):
```
class BubbleSort {
    void bubbleSort(int[] arr) {
        int n = arr.length;

        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
}
import java.util.Scanner;
public class Main {
public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter size of array: ");
        int size = sc.nextInt();

        int[] arr = new int[size];
        for (int i = 0; i < size; i++) {
            System.out.print("Enter element " + (i + 1) + ": ");
            arr[i] = sc.nextInt();
        }

        BubbleSort bs = new BubbleSort();
        bs.bubbleSort(arr);

        System.out.println("Sorted array:");
        for (int i : arr) {
            System.out.print(i + " ");
        }
    }
}
```
## Output:
![Output for 3c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/3c.png)
## Experiment 4
## Title 4a(Implement Single Inheritence):
```
class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void displayPersonDetails() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}

class Employee extends Person {
    double annualSalary;
    int yearOfJoining;
    String nationalInsuranceNumber;

    Employee(String name, int age, double salary, int year, String nin) {
        super(name, age);
        annualSalary = salary;
        yearOfJoining = year;
        nationalInsuranceNumber = nin;
    }

    void displayEmployeeDetails() {
        displayPersonDetails();
        System.out.println("Annual Salary: " + annualSalary);
        System.out.println("Year of Joining: " + yearOfJoining);
        System.out.println("National Insurance Number: " + nationalInsuranceNumber);
    }
}

public class TestEmployee {
    public static void main(String[] args) {
        Employee emp = new Employee("Yasmi", 19, 60000, 2022, "NJ123456A");
        emp.displayEmployeeDetails();
    }
}
```
## output:
![Output for 4a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/4a.png)
## Title 4b(Implement Multilevel Inheritance):
```
class Bicycle {
    String pedalType;

    void showBicycleInfo() {
        System.out.println("This is a bicycle with pedals");
        System.out.println("Pedal Type: " + pedalType);
    }
}

class Motorbike extends Bicycle {
    int engineCapacity;

    void showMotorbikeInfo() {
        System.out.println("This motorbike has an engine");
        System.out.println("Engine Capacity: " + engineCapacity + " cc");
    }
}

class ElectricBike extends Motorbike {
    int batteryCapacity;

    void showElectricBikeInfo() {
        System.out.println("This electric bike has an electric motor & battery");
        System.out.println("Battery Capacity: " + batteryCapacity + " Wh");
    }
}

public class TestVehicle {
    public static void main(String[] args) {
        ElectricBike eBike = new ElectricBike();

        eBike.pedalType = "Standard Pedals";
        eBike.engineCapacity = 250;
        eBike.batteryCapacity = 500;

        eBike.showBicycleInfo();
        eBike.showMotorbikeInfo();
        eBike.showElectricBikeInfo();
    }
}
```
## output:
![Output for 4b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/4b.png)
## Title 4c(Implement Abstract classes):
```
abstract class Figure {
    double dim1, dim2;

    Figure(double d1, double d2) {
        dim1 = d1;
        dim2 = d2;
    }

    abstract double area();
}

class Rectangle extends Figure {
    Rectangle(double length, double breadth) {
        super(length, breadth);
    }

    double area() {
        return dim1 * dim2;
    }
}

class Triangle extends Figure {
    Triangle(double base, double height) {
        super(base, height);
    }

    double area() {
        return 0.5 * dim1 * dim2;
    }
}

public class TestFigure {
    public static void main(String[] args) {
        Figure f1 = new Rectangle(23.4, 14.5);
        Figure f2 = new Triangle(12.3, 15.6);

        System.out.println("Area of Rectangle = " + f1.area());
        System.out.println("Area of Triangle = " + f2.area());
    }
}
```
## Output:
![Output for 4c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/4c.png)
## Aditional Experiment 1
```
import java.util.Scanner;

class InsertSubstring {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Main String: ");
        String mainString = sc.nextLine();

        System.out.print("Enter Sub String: ");
        String subString = sc.nextLine();

        System.out.print("Enter Position: ");
        int position = sc.nextInt();

        if (position < 0 || position > mainString.length()) {
            System.out.println("Invalid Position!");
        } else {
            String firstPart = mainString.substring(0, position);
            String secondPart = mainString.substring(position);
            String result = firstPart + subString + secondPart;

            System.out.println("Resultant String: " + result);
        }

        sc.close();
    }
}
```
## Output:
![Output for Additional Experiment 1](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/b2297a6e9dde4434c41f5386136ee27699bb0238/additional_1.jpg)
## Additional Experiment 3
```
import java.util.Scanner;

class PalindromeCheck {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a String: ");
        String str = sc.nextLine();

        int start = 0;
        int end = str.length() - 1;
        boolean isPalindrome = true;

        while (start < end) {
            if (str.charAt(start) != str.charAt(end)) {
                isPalindrome = false;
                break;
            }
            start++;
            end--;
        }

        if (isPalindrome)
            System.out.println("The string is a Palindrome.");
        else
            System.out.println("The string is NOT a Palindrome.");

        sc.close();
    }
}
```
## Output:
![Output for Additional Experiment 3](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/b2297a6e9dde4434c41f5386136ee27699bb0238/additional_3.jpg)
## Additional Experiment 4
```
import java.util.Scanner;

class PerfectNumber {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a Number: ");
        int num = sc.nextInt();

        int sum = 0;

        for (int i = 1; i <= num / 2; i++) {
            if (num % i == 0) {
                sum += i;
            }
        }

        if (sum == num)
            System.out.println(num + " is a Perfect Number.");
        else
            System.out.println(num + " is NOT a Perfect Number.");

        sc.close();
    }
}
```
## Output:
![Output for Adiitional Experiment 4](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/b2297a6e9dde4434c41f5386136ee27699bb0238/additional_4.jpg)
## Experiment 5
## Title 5a(Implement Interface):
```
class BubbleSort implements Sortable{
        public void sort(int[] arr){
                int size=arr.length;
                int temp=0;
                for(int i=0;i<size-1;i++){
                        for(int j=0;j<size-i-1;j++){
                                if(arr[j]>arr[j+1]){
                                        temp=arr[j+1];
                                        arr[j+1]=arr[j];
                                        arr[j]=temp;
                                }
                        }
                }
        }
}
class Selection implements Sortable{
        public void sort(int[] arr){
                int size=arr.length;
                int minIndex=0;
                int min;
                for(int i=0;i<size;i++){
                  min=arr[i];
                  for(int j=i+1;j<size;j++){
                      if(min>arr[j]){
                        min=arr[j];
                        minIndex=j;
                      }
                  }
                  for(int j=minIndex;j>i;j--){
                        arr[j]=arr[j-1];
                  }
                  arr[i]=min;
                }
        }
}
class TestSort{
        static void display(int arr[]){
                for(int ele :arr){
                  System.out.println(ele+" ");
                }
                System.out.println("\b\b");
        }
        public static void main(String[] args){
                int arr[]={9,7,4,3,6,8};
                int bar[]={8,6,4,3,7,9};
                Sortable s;
                s= new BubbleSort();
                s.sort(arr);
                System.out.println("After Sorting:");
                display(arr);
                s=new Selection();
                s.sort(bar);
                System.out.println("After Sorting:");
                display(bar);
        }
}
```
## Output:
![Output for 5a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/5a.png)
## Title 5b(Implement Runtime Polymorphism):
```
class TestVehicle{
        public static void main(String[] args){
                Vehicle v;
                v=new Car();
                v.run();
                v=new Bike();
                v.run();
                v=new Vehicle();
                v.run();
        }
}
class Vehicle{
        void run(){
                System.out.println("Vehicle is running");
        }
}
class Car extends Vehicle{
        void run(){
                System.out.println("Car is running");
        }
}
class Bike extends Vehicle{
        void run(){
                System.out.println("Bike is running");
        }
}
```
## Output:
![Output for 5b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/5b.png)
## Title 5c(Implement String Buffer):
```
class DeleteChar{
        public static void main(String[] args){
                StringBuffer sb=new StringBuffer("Java Programming");
                System.out.println(sb);
                sb.deleteCharAt(4);
                System.out.println(sb);
                sb.delete(0,4);
                System.out.println(sb);
        }
}
```
## Output:
![Output for 5c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/5c.png)
## Experiment 6
## Title 6a(Implement Exception Handling Mechanism):
```
import java.util.Scanner;

class ArrayIndexExceptionDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter size of array: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        try {
            System.out.print("Enter index to access: ");
            int index = sc.nextInt();
            System.out.println("Element at index " + index + " is " + arr[index]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index out of bounds!");
        }

        sc.close();
    }
}
```
## Output:
![Output for 6a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/6a.jpg)
## Title 6b(Implement Multiple Catch Clause):
```
import java.util.Scanner;

class MultipleCatchDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] arr = {10, 20, 30, 40, 50};

        try {
            System.out.print("Enter first number: ");
            int a = sc.nextInt();

            System.out.print("Enter second number: ");
            int b = sc.nextInt();

            int result = a / b;
            System.out.println("Result = " + result);

            System.out.print("Enter index to access array: ");
            int index = sc.nextInt();
            System.out.println("Element = " + arr[index]);
        }
        catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception occurred");
        }
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index Out Of Bounds Exception occurred");
        }
        catch (Exception e) {
            System.out.println("Some other exception occurred");
        }

        sc.close();
        System.out.println("Program continues...");
    }
}
```
## Output:
![Output for 6b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/6b.jpg)
## Title for 6c (Implement Bult-in Exception):
```
import java.util.Scanner;

class BuiltInException {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter a number to divide 100: ");
            int n = sc.nextInt();

            int result = 100 / n;
            System.out.println("Result = " + result);

            int[] arr = new int[3];
            System.out.println(arr[5]);
        }
        catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception occurred");
        }
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index Out Of Bounds Exception occurred");
        }
        catch (Exception e) {
            System.out.println("General Exception occurred");
        }
        finally {
            System.out.println("Program continues...");
            sc.close();
        }
    }
}
```
## Output:
![Output for 6c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/6c.jpg)
## Experiment 7
## Title 7a(Implement User Defined Exception):
```
class InvalidCountryException extends Exception {
          InvalidCountryException() {
              super();
              }
              InvalidCountryException(String message) {
              super(message);
              }
            }
class UserRegion {

    void registerUser(String userName, String userCountry) throws InvalidCountryException {

        if (!userCountry.equals("India")) {
            throw new InvalidCountryException("User outside India cannot be registered");
        } else {
            System.out.println("User registration done successfully");
        }
    }

    public static void main(String args[]) {

        UserRegion ur = new UserRegion();

        try {
            ur.registerUser("Ravi", "USA");
        }
        catch (InvalidCountryException e) {
            System.out.println(e.getMessage());
        }
    }
}
```
## Output:
![Output for 7a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/7a.jpg)
## Title 7b(Implement Thread class):
```
class GoodMorningThread extends Thread {
    public void run() {
        while (true) {
            System.out.println("Good Morning");
            try {
                Thread.sleep(1000); 
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}
  class HelloThread extends Thread {
     public void run() {
          while(true) {
            System.out.println("Hello");
         try {
            Thread.sleep(2000);
         }
         catch(InterruptedException e) {
               System.out.print(e);
           }
        }
    }
  }
class WelcomeThread extends Thread {
         public void run() {
          while(true) {
        System.out.println("Welcome");
         try {
           Thread.sleep(3000);
         }
         catch(InterruptedException e) {
         System.out.print(e);
         }
       }
     }
}
class TestThreads {
     public static void main(String args[]) {
            GoodMorningThread t1 = new GoodMorningThread();
            HelloThread t2 = new HelloThread();
            WelcomeThread t3 = new WelcomeThread();


            t1.start();
            t2.start();
            t3.start();
     }
}
```
## Output:
![Output for 7b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/7b.jpg)
## Title 7c(Implement Alive and join()]
```
class LongRunningTask extends Thread {
        public void run() {
      System.out.println("Long running task started...");
      try {
            for(int i=1;i<= 5;i++) {
      System.out.println("Working..." +i);
            Thread.sleep(1000);
        }
     }
      catch(InterruptedException e) {
       System.out.println(e);
   }
  System.out.println("Long running task completed!");
      }
     }
public class ThreadDemo {
    public static void main(String[] args) {

        LongRunningTask task1 = new LongRunningTask();

        System.out.println("Before starting task1: " + task1.isAlive());

        task1.start();

        System.out.println("After starting task1: " + task1.isAlive());

        try {
            System.out.println("Main thread waiting for task1 to complete using join()...");
            task1.join();
        } catch (InterruptedException e) {
            System.out.println(e);
        }

        System.out.println("After task1 completion: " + task1.isAlive());
        System.out.println("Main thread continues execution.");
    }
}
```
## Output:
![Output for 7c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d6bd804e1170a464cb04a7ac16c5540cb931c7c8/7c.jpg)
## Experiment 8
## Title 8a (Implement Daemaon Threads):
```
class DaemonThread extends Thread {
    public void run() {
        while (true) {
            System.out.println("Daemon Thread is running...");
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println("Exception occurred");
            }
        }
    }
}

class UserThread extends Thread {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("User Thread iteration: " + i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                System.out.println("Exception occurred");
            }
        }
    }
}

public class TestDaemon {
    public static void main(String[] args) {
        UserThread userThread = new UserThread();
        DaemonThread daemonThread = new DaemonThread();

        daemonThread.setDaemon(true);   // Setting daemon thread

        userThread.start();
        daemonThread.start();
    }
}
```
## Output:
![Output for 8a](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/71246de68bd20b86735edfecfcf2e7a6377d5eb3/8a.jpg)
## Title 8b(Implement Producer Consumer Problem):
```
class SharedBuffer {

    private int[] buffer;
    private int count = 0;
    private int in = 0;
    private int out = 0;

    SharedBuffer(int size) {
        buffer = new int[size];
    }

    synchronized void produce(int item) {
        while (count == buffer.length) {
            try {
                wait();
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }

        buffer[in] = item;
        in = (in + 1) % buffer.length;
        count++;

        notify();
    }

    synchronized int consume() throws InterruptedException {
        while (count == 0) {
            wait();
        }

        int item = buffer[out];
        out = (out + 1) % buffer.length;
        count--;

        notify();
        return item;
    }
}

class Producer extends Thread {

    private SharedBuffer buffer;

    Producer(SharedBuffer buffer) {
        this.buffer = buffer;
    }

    public void run() {
        for (int i = 1; i <= 10; i++) {
            buffer.produce(i);
            System.out.println("Produced: " + i);
        }
    }
}

class Consumer extends Thread {

    private SharedBuffer buffer;

    Consumer(SharedBuffer buffer) {
        this.buffer = buffer;
    }

    public void run() {
        try {
            for (int i = 1; i <= 10; i++) {
                int item = buffer.consume();
                System.out.println("Consumed item: " + item);
            }
        } catch (InterruptedException e) {
            System.out.println(e);
        }
    }
}

public class ProducerConsumerDemo {

    public static void main(String[] args) {

        SharedBuffer buffer = new SharedBuffer(5);

        Producer p = new Producer(buffer);
        Consumer c = new Consumer(buffer);

        p.start();
        c.start();
    }
}
```
## Output:
![Output for 8b](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/71246de68bd20b86735edfecfcf2e7a6377d5eb3/8b.jpg)
## Title 8c(Implement User Defined Package):
```
// ArithmeticOperation.java
package arithmetic;

public class ArithmeticOperation {

    public int add(int x, int y) {
        return x + y;
    }

    public int subtraction(int x, int y) {
        return x - y;
    }

    public int multiplication(int x, int y) {
        return x * y;
    }

    public int division(int x, int y) {
        return x / y;
    }
}
// Calculate.java
import arithmetic.ArithmeticOperation;
class Calculate {
    public static void main(String args[]) {

        ArithmeticOperation ae = new ArithmeticOperation();

        int sum = ae.add(10, 5);
        System.out.println("Addition: " + sum);

        int diff = ae.subtraction(10, 5);
        System.out.println("Subtraction: " + diff);

        int prod = ae.multiplication(10, 5);
        System.out.println("Multiplication: " + prod);

        int div = ae.division(10, 5);
        System.out.println("Division: " + div);
    }
}
```
## Output:
![Output for 8c](https://github.com/CHITTARI-THANUJA/java-lab-cseg-5df/blob/d2cd5dd8f03c3a3fe28fd6865aaae4c89b63bf86/8c.jpg)
##




