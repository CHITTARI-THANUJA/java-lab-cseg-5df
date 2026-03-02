# java-lab-cseg-5df
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
![Output for 1a]()

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
![Output for 1b]
## Experiment 2
