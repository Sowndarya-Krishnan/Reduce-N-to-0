# Reduce-N-to-0
package com.project;
import java.util.Scanner;


public class Zero {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the number: ");
        int n = scanner.nextInt();
        int j = 0;

        while (n > 0) {
            if (isPrime(n)) {
                n--;
                j++;
            } else {
                int i = greatestPrime(n);
                n = i;
                j++;
            }
            System.out.println("step no" +j+"we obtain" +n);
        }

        System.out.println(j);
    }

    public static boolean isPrime(int n) {
        if (n <= 1) {
            return false;
        }

        for (int i = 2; i <= Math.sqrt(n); i++) {
            if (n % i == 0) {
                return false;
            }
        }

        return true;
    }

    public static int greatestPrime(int n) {
        for (int i = n / 2; i > 1; i--) {
            if (n % i == 0) {
                if (isPrime(i)) {
                    return i;
                }
            }
        }

        return 0; // Default return value if no prime factor found
    }
}
