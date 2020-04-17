#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I
a) O(n)
    Linear run time, as input size grows, the loop will run longer at a constant rate.


b) O(n (log n))
    Outer loop is O(n), linear.  Inner loop is O(log n), diminishing iterations by half (j *= 2).  First answer was O(n^2) because I didn't consider the inner loop being cut in half.

<!-- O(n^2)
    Loop within a loop, quadratic (polynomial), as input size grows runtime rate increases.  Only good for small inputs, does not scale for very large input. -->


c) O(n)
    Linear constant rise in run time as input size grows, the runtime grows at a constant rate.

<!-- O(log n)
    Linear constant rise in run time, diminishing input for every recursion.  As input size grows, runtime rate does not increase very quckly. -->

## Exercise II

Take in n stories (100)
    set floor = 0
    define function test_egg_break parsing floors into array([0:100])
        set base case to if stories are less than 2
        divide stories in half (bottom half = [0:50], top half = [51:100])
            find top_middle_index of top half (top half = 75)
            find bottom_middle_index of bottom half (bottom half = 25)
            test if egg will break top_middle_index (75)
                if egg breaks
                    test if egg breaks on bottom_middle_index (25)
                        if egg breaks
                            recursively call function test_egg_break sending new array [bottom(0):bottom_middle_index-1(24)] 
                        else if egg doesn't break (25)
                            set floor = 25
                            recurisively call function test_egg_break sending
                            new array [bottom_middle_index+1(26):top_middle_index-1(74)]
                else if egg doesn't break (75)
                    set floor = 75
                        recurisively call function test_egg_break sending new array [top_middle_index+1(76):top(100)]
    return floor

    Time complexity: O(log n) as input size grows, runtime increases slowly/logarithmically . It's essentially a binary search tree, dividing in half each time.

    Space complexity: 0(n) as input size grows, space needed to run increases at a linear rate.