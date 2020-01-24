# aspeed-rng-testing

To duplicate these results clone NIST Statistical Test Suite source code from:
 https://github.com/terrillmoore/NIST-Statistical-Test-Suite

Then, follow the instructions to build it.

Copy the rng-dump binaries to NIST-Statistical-Test-Suite/sts/data folder and execute

oscar@ubuntu18:~/NIST/NIST-Statistical-Test-Suite/sts$ ./assess 3355000

           G E N E R A T O R    S E L E C T I O N
           ______________________________________

    [0] Input File                 [1] Linear Congruential
    [2] Quadratic Congruential I   [3] Quadratic Congruential II
    [4] Cubic Congruential         [5] XOR
    [6] Modular Exponentiation     [7] Blum-Blum-Shub
    [8] Micali-Schnorr             [9] G Using SHA-1

   Enter Choice: 0


                User Prescribed Input File: data/dump_m7-bundled.bin

                S T A T I S T I C A L   T E S T S
                _________________________________

    [01] Frequency                       [02] Block Frequency
    [03] Cumulative Sums                 [04] Runs
    [05] Longest Run of Ones             [06] Rank
    [07] Discrete Fourier Transform      [08] Nonperiodic Template Matchings
    [09] Overlapping Template Matchings  [10] Universal Statistical
    [11] Approximate Entropy             [12] Random Excursions
    [13] Random Excursions Variant       [14] Serial
    [15] Linear Complexity

         INSTRUCTIONS
            Enter 0 if you DO NOT want to apply all of the
            statistical tests to each sequence and 1 if you DO.

   Enter Choice: 1

        P a r a m e t e r   A d j u s t m e n t s
        -----------------------------------------
    [1] Block Frequency Test - block length(M):         128
    [2] NonOverlapping Template Test - block length(m): 9
    [3] Overlapping Template Test - block length(m):    9
    [4] Approximate Entropy Test - block length(m):     10
    [5] Serial Test - block length(m):                  16
    [6] Linear Complexity Test - block length(M):       500

   Select Test (0 to continue): 0

   How many bitstreams? 100

   Input File Format:
    [0] ASCII - A sequence of ASCII 0's and 1's
    [1] Binary - Each byte in data file contains 8 bits of data

   Select input mode:  1

     Statistical Testing In Progress.........

     Statistical Testing Complete!!!!!!!!!!!!


Finally, save the reports :

oscar@ubuntu:~/NIST/NIST-Statistical-Test-Suite/sts$ mv experiments/AlgorithmTesting/finalAnalysisReport.txt experiments/AlgorithmTesting/rng_mode7_nist_statistical_report.txt

