# CMPS 2200  Recitation 01

**Name (JAKE JOHNSTON):**_________________________  

In this recitation, we will investigate asymptotic complexity. Additionally, we will get familiar with the various technologies we'll use for collaborative coding.

To complete this recitation, follow the instructions in this document. Some of your answers will go in this file, and others will require you to edit `main.py`.


## Setup
- Login to Github.
- Click on the assignment link sent through canvas and accept the assignment.
- Click on your personal github repository for the assignment (e.g., https://github.com/tulane-cmps2200/recitation-01-your_username).
- [Clone](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository) the repository to your local device
- Complete the lab task
- [Add, commit, and push](https://docs.github.com/en/github/managing-files-in-a-repository/managing-files-using-the-command-line/adding-a-file-to-a-repository-using-the-command-line) your completed lab back up to GitHub.
  - You will need to issue `git add` for all files that you have modified, e.g., `main.py`, `README.md`, and any others that you modify as well.
  - For example, on the command line, in the same directory as your cloned lab:
```
$ git add main.py
$ git commit -m "Implement Required Functions"
$ git push origin main
```

You'll work with a partner to complete this recitation. You will be able to code together in the same `repl.it` instance. You can choose whose repl.it instance you will share. This person will click the "Share" button in their repl.it instance and email the lab partner.

## Turning in your work
- Only one team member needs to push your completed lab to github.
- In the README.md file, include the name of the team members.


## Comparing search algorithms

We'll compare the running times of `linear_search` and `binary_search` empirically.

- [x] 1. In `main.py`, the implementation of `linear_search` is already complete. Your task is to implement `binary_search`. Implement a recursive solution using the helper function `_binary_search`.

- [x] 2. Test that your function is correct by calling from the command-line `pytest main.py::test_binary_search`

- [x] 3. Write at least two additional test cases in `test_binary_search` and confirm they pass.

- [x] 4. Describe the worst case input value of `key` for `linear_search`? for `binary_search`?

**The worst case input value for the key in linear search if the key is in the list would be if the key is at the end of the list. The worst case input value for the key in binary search if the key is in the list would be if the key is at eaither the beginning or the end of the list**

- [x] 5. Describe the best case input value of `key` for `linear_search`? for `binary_search`?

**The best case input value for the key in linear search if the key is in the list would be if the key is at the beginning of the list. The best case input value for the key in binary search if the key is in the list would be if the key is in the center of the list**

- [x] 6. Complete the `time_search` function to compute the running time of a search function. Note that this is an example of a "higher order" function, since one of its parameters is another function.

- [x] 7. Complete the `compare_search` function to compare the running times of linear search and binary search. Confirm the implementation by running `pytest main.py::test_compare_search`, which contains some simple checks.

- [x] 8. Call `print_results(compare_search())` and paste the results here:

**|        n |   linear |   binary |
  |----------|----------|----------|
  |       10 |    0.002 |    0.003 |
  |      100 |    0.005 |    0.005 |
  |     1000 |    0.045 |    0.005 |
  |    10000 |    0.438 |    0.008 |
  |   100000 |    4.632 |    0.020 |
  |  1000000 |   49.137 |    0.032 |
  | 10000000 |  496.063 |    0.037 |**

- [x] 9. The theoretical worst-case running time of linear search is $O(n)$ and binary search is $O(log_2(n))$. Do these theoretical running times match your empirical results? Why or why not?

**The theoretical running times do match the empirical results because the linear search times follow a somewhat linear line, while the binary search times follow a more logarithmic trend of log_2(x)**

- [x] 10. Binary search assumes the input list is already sorted. Assume it takes $\Theta(n^2)$ time to sort a list of length $n$. Suppose you know ahead of time that you will search the same list $k$ times.
  + What is worst-case complexity of searching a list of $n$ elements $k$ times using linear search? **O(kn)**
  + For binary search? **O(n^2 + k * log_2(n))**
  + For what values of $k$ is it more efficient to first sort and then use binary search versus just using linear search without sorting? **When n^2 + k * log_2(n) < kn , it will be more efficient to sort and search a binary list. kn - klog_2(n) > n^2 , which means it will only be more efficient when: k > (n^2)/(n - log_2(n))**
