# number-guessing-game-
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    int guess, target;
    int attempts;
    char playAgain;

    // Seed random number generator
    srand(time(0));

    do {
        // Generate random number from 1 to 100
        target = rand() % 100 + 1;
        attempts = 0;

        cout << "\n===== NUMBER GUESSING GAME =====\n";
        cout << "I have selected a number between 1 and 100.\n";
        cout << "Try to guess it!\n";

        // Guessing loop
        do {
            cout << "\nEnter your guess: ";
            cin >> guess;
            attempts++;

            if (guess > target) {
                cout << "Too High! Try again.\n";
            }
            else if (guess < target) {
                cout << "Too Low! Try again.\n";
            }
            else {
                cout << "\nCongratulations! You guessed the number.\n";
                cout << "Number of attempts: " << attempts << endl;

                // Simple score
                int score = 100 - (attempts - 1) * 10;
                if (score < 0)
                    score = 0;

                cout << "Your score: " << score << endl;
            }

        } while (guess != target);

        cout << "\nDo you want to play again? (y/n): ";
        cin >> playAgain;

    } while (playAgain == 'y' || playAgain == 'Y');

    cout << "\nThank you for playing!\n";

    return 0;
}