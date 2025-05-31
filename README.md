# SCT_ST_02
import java.util.Scanner;

public class GuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random rand = new Random();

        int numberToGuess = rand.nextInt(100) + 1; // Random number between 1 and 100
        int userGuess = 0;
        int attempts = 0;

        System.out.println("Welcome to the Guessing Game!");
        System.out.println("I have picked a number between 1 and 100. Can you guess it?");

        while (userGuess != numberToGuess) {
            System.out.print("Enter your guess: ");
            userGuess = scanner.nextInt();
            attempts++;

            if (userGuess == numberToGuess) {
                System.out.println("🎉 Correct! You guessed it in " + attempts + " attempts.");
            } else {
                // Simple GAI (Guessing AI) style hint
                int diff = Math.abs(userGuess - numberToGuess);
                if (userGuess > numberToGuess) {
                    if (diff > 20) {
                        System.out.println("Too high! You're way off.");
                    } else {
                        System.out.println("A bit too high.");
                    }
                } else {
                    if (diff > 20) {
                        System.out.println("Too low! You're far behind.");
                    } else {
                        System.out.println("A bit too low.");
                    }
                }
            }
        }

        scanner.close();
    }
}


