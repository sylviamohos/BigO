# Big O

What is the RUNTIME complexity of this algorithm?

public int example(int[] array) {

    int total = 0;
    for (int i = 0; i < array.length; i++) {
        total += array[i];
    }
    return total;
}

Solution:  O(n)

Explanation:  Here n is the length of the array. The code inside the for loop runs n times.


What is the SPACE complexity of this algorithm?

public int example(int[] array) {

    int total = 0;
    for (int i = 0; i < array.length; i++) {
        total += array[i];
    }

    return total;
}

Solution: O(1)

Explanation:  Constant space is needed outside of the input. We only need a single variable that does not scale with the input - total.


What is the RUNTIME complexity of this algorithm?

public int example(int[] array) {
    
    int total = 0;
    for (int i = 0; i < array.length; i += 2) {
        total += array[i];
    }

    return total;
}

Solution: O(n)

Explanation: Here n is the length of the array. The code inside the for loop runs n/2 times, which is O(n).


What is the RUNTIME complexity of this algorithm?

public int example(int[] array) {
    
    int total = 0;
    for (int i = 0; i < array.length; i++) {
        for (int j = 0; j <= array.length; j++) {
            total += array[i];
        }
    }

    return total;
}

Solution: O(n^2)

Explanation:  Here n is the length of the array. But the code inside the loop doesn't just run n times, it runs n^2 times. For each element in the array it loops over the entire array again, which is n*n, or n^2.


What is the RUNTIME complexity of this algorithm?

public void example(int[] array) {

    int min = array[0];
    int max = array[0];

    for (int item : array) {
        if (min > item) {
            min = item;
        }
    }

    for (int item : array) {
        if (max < item) {
            max = item;
        }
    }
}

Solution: O(n)

Explanation:  Here n is the length of the array. The code inside each for loop runs n times. Since one loop runs and then the other, we can think of this as n + n or 2n. Remember we drop the coefficients so we still end up with O(n).


What is the RUNTIME complexity of this algorithm?

public void example(int[] array) {

    int max = array[0];

    for (int item : array) {
        if (max < item) {
            max = item;
        }
    }

    for (int a : array) {
        for (int b : array) {
            System.out.println(a + ", " + b);
        }
    }

    return max;
}

Solution: O(n^2)

Explanation:  The code inside the first for loop runs n times, where n represents the length of the array. The System.out.println code runs n^2 times, where n still represents the length of the arry, due to the nested for loops each running n times. That makes this algorithm run O(n^2 + n) overall, but remember we drop the non-dominant terms in the expression simplifying this to O(n^2).


What is the RUNTIME complexity of this algorithm?

public void logAtMost5(int n) {

    int max = 5;
    int iter = max;
    if (n < max) {
        iter = n;
    }

    for (int i = 1; i <= iter; i++) {
        System.out.println(i);
    }
}

Solution:  O(1)

Explanation:  We are looping either 5 times or n times, whichever is smaller. If n is 3, we are looping 3 times. If n is 100, we are looping 5 times. If n is 1,000, we are looping 5 times. When we think about Big O we care what happens when n becomes arbitrarily large. When n is arbitrarily large we are looping 5 times. That makes this algorithm perform in constant time.
