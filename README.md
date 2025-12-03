#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int number, guess, attempts = 0;
    srand(time(0));
    number = rand() % 100 + 1; 
    
    printf("Guess the number (between 1 and 100):\n");

    while (attempts < 5) {
        printf("Attempt %d: ", attempts + 1);
        scanf("%d", &guess);
        attempts++;

        if (guess == number) {
            printf("🎉 Congratulations! You guessed the number in %d attempts!\n", attempts);
            break;
        } 
        else if (guess < number) {
            if (number - guess <= 5) 
                printf("A little low!\n");
            else 
                printf("Too low!\n");
        } 
        else {
            if (guess - number <= 5) 
                printf("A little high!\n");
            else 
                printf("Too high!\n");
        }
    }

    if (attempts == 5 && guess != number) {
        printf("❌ Sorry, you've used all attempts. The number was %d.\n", number);
    }

    return 0;
}
