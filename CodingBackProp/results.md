
# Backpropagation 

##  Modifications
The `Train` and `Error` methods were updated to include:
1. **Cross-Entropy Loss**: Added to prevent the vanishing gradient problem associated with Mean Squared Error (MSE) during confident but incorrect predictions. 
2. **Weight Decay ($L_2$ Regularization)**: Added to the input-hidden and hidden-output weight updates (excluding biases) to penalize large weights and improve generalization.

## Experimental Results
The program runs four distinct training configurations on the exact same train/test data split over 1,000 epochs. 

```text
Begin neural network back-propagation demo

Generating 1000 artificial data items with 4 features
Generating weights and biases:
-5.03 -7.79 -0.66  5.43  3.15 -1.34 -2.92  8.88 -7.97  2.85
-9.43 -5.04 -3.60  9.80  3.64  3.10 -4.35  2.31  4.09  4.04
 9.00 -8.13 -6.78 -2.36  5.96 -6.61  5.88 -3.86  6.46  7.73
 1.13  4.33  3.99 -9.73  9.84  6.13  7.17 -8.75  0.29  0.51
-4.54  9.88  3.82
Done

Creating train (80%) and test (20%) matrices
Done

Training data:
[  0]  -1.09  -9.10   0.85   5.52   0.00   0.00   1.00
[  1]  -1.92   8.16   6.53  -1.54   0.00   1.00   0.00
[  2]   7.94   3.66  -2.63  -3.38   0.00   1.00   0.00
[  3]  -5.01  -4.07  -6.24   2.87   0.00   1.00   0.00
. . .
[799]   1.61   2.00  -5.77  -7.44   0.00   1.00   0.00

Test data:
[  0]   0.18   5.94   7.58  -3.33   0.00   1.00   0.00
[  1]   7.48  -3.41  -0.58  -8.75   0.00   0.00   1.00
[  2]  -0.73  -9.31   1.91  -6.77   0.00   0.00   1.00
[  3]  -6.13  -0.95   5.70   1.62   0.00   0.00   1.00
. . .
[199]   7.97  -5.35  -4.93  -0.51   0.00   0.00   1.00


=== MSE ===
epoch = 100  error = 0.0525
epoch = 200  error = 0.0343
epoch = 300  error = 0.0385
epoch = 400  error = 0.0319
epoch = 500  error = 0.0245
epoch = 600  error = 0.0211
epoch = 700  error = 0.0211
epoch = 800  error = 0.0175
epoch = 900  error = 0.0187
Train acc = 0.9900
Test acc  = 0.9900
Sum of squared weights = 417.13

=== CrossEntropy ===
epoch = 100  error = 0.1329
epoch = 200  error = 0.1031
epoch = 300  error = 0.1223
epoch = 400  error = 0.0815
epoch = 500  error = 0.1102
epoch = 600  error = 0.1261
epoch = 700  error = 0.0960
epoch = 800  error = 0.1087
epoch = 900  error = 0.0613
Train acc = 0.9863
Test acc  = 0.9750
Sum of squared weights = 2816.78

=== MSE + decay ===
epoch = 100  error = 0.0944
epoch = 200  error = 0.0977
epoch = 300  error = 0.0793
epoch = 400  error = 0.0757
epoch = 500  error = 0.0731
epoch = 600  error = 0.0825
epoch = 700  error = 0.0779
epoch = 800  error = 0.0718
epoch = 900  error = 0.0904
Train acc = 0.9688
Test acc  = 0.9500
Sum of squared weights = 521.18

=== CrossEntropy + decay ===
epoch = 100  error = 0.2681
epoch = 200  error = 0.2739
epoch = 300  error = 0.2338
epoch = 400  error = 0.2724
epoch = 500  error = 0.2526
epoch = 600  error = 0.2092
epoch = 700  error = 0.2534
epoch = 800  error = 0.2219
epoch = 900  error = 0.2233
Train acc = 0.9450
Test acc  = 0.9300
Sum of squared weights = 265.31

End back-propagation demo
```