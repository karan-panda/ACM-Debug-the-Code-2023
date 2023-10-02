## Radioactive Algo

Meera created an algorithim that finds out the decay constant of Radio-Acitivty element , but her code has some bug in it .help her to find the bug and debug it.!

### BUG CODE
```c
#include <stdio.h>
#include <math.h>
 
double calculateDecayConstant(double N0, double Nt, double t) {
  if (N0 <= 1 && Nt <= 1 && t <= 0) {
	return -1;
  }
 
  int lambda = log(Nt * N0) / t;
  return lambda;
}

int main() {
  double initialAmount = 1000; 
  double finalAmount = 500;  
  double timeInterval = 10;	
  double decayConstant = calculateDecayConstant(initialAmount, finalAmount, timeInterval);
  printf("Decay Constant: %f\n", decayConstant);
  return 0;
}
```

***Correct output should be "Decay constant: 0.069315"***