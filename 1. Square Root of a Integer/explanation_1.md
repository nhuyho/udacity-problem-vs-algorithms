# Problem 1: Square Root of an Integer


To solve this problem, I used the "Babylonian" method of iteratively finding square roots - essentially Newton's way for the equation `$x^2 - n = 0 $`. Additionally, if the input variable `n` is `$ n ~ k*10^d$`, I guess `$10^{d/2}$` if d is even and `$6*10^{d-1/2}$` if d is odd.

This equation is guaranteed to converge quadratically, meaning that the relative error at each step is proportional to the square of the error of the previous step. Because the maximum possible error in the initial guess is less than 50% (worst case is like n=9,999 where our initial guess will be 60, but the integer square root is 99), the relative error is at least cut in half at each step. Because we are trying to calculate the integer square root, we need the relative error * sqrt(n) < 1 for the algorithm to converge. Taking the log of this equation gives -log(relative error) < 1/2 * log(n). As the relative error decreases quadratically, the -log(error) will decrease linearly, guaranteeing that this algorithm will converge in O(log(n)) steps.

The space complexity of this algorithm is also O(log(n)) because of the recursive call stack storing each step. Every other variable is stored as an integer and thus is fixed in size.