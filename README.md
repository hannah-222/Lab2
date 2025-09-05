# Lab2
// lab2.java
// Hannah Shane
// September 5, 2025
// calculates primes using Sieve of Eratosthenes
// demonstrates command line arguments and methods
// answers to performance questions:
    
    // 1. I tested out 100 million and it worked but took a while to run. 
    //    I didn't go any higher than that because of I didn't want to crash my computer or wait too long.

    // 2. Printing the numbers affects performance because the output will be slower than it takes to compute the primes. 
    //    When you don't print the numbers, it runs much faster because the computer doesn't have to spend time outputting each prime number after it finds them.
    
    // 3. The factors that limit my program from finding larger prime numbers are time and memory, but mainly time.

    //NOTE: Wasn't sure if it was just VSCode or maybe an error in the starter code, but vsCode was giving an error for lines 27-30. 
    //      Turns out in the starter code it was "+ N" instead of "+ num" and 
    //      instead of N = interger.parseInt(args[0]) that was in the starter code, it was changed to num = integer.parseInt(args[0]) 
    //      to match the int num = 0 and showPrimes (num).

public class lab2 {

    public static void main(String[] args) 
    {
        int num = 0;
        
        //add code to get num from command line argument
        if (args.length > 0)
        {
            num = Integer.parseInt( args[0] );
            System.out.println( "N = " + num);
            // call showPrimes only if argument is provided
            showPrimes( num );
        }
        else
        {
            System.out.println("Missing argument");
        }
    }//main
    
    public static void showPrimes(int N)
    {
        if (N < 2) {
            System.out.println("No primes less than 2.");
            return;
        }
        boolean[] isPrime = new boolean[N+1];
        isPrime[0] = false;
        isPrime[1] = false;
        for (int i = 2; i <= N; i++) {
            isPrime[i] = true;
        }
        for (int i = 2; i<= Math.sqrt(N); i++) 
        { 
            if (isPrime[i]) 
            {
                for (int a = i * i; a <= N; a += i) 
                {
                    isPrime[a] = false;
                }
            }
        }	
        for (int i = 2; i <= N; i++) 
        {
            if (isPrime[i]) 
            {
                System.out.print(i + " ");
            }
        }	
        System.out.println();
    }//showPrimes

       
     

}//lab211
