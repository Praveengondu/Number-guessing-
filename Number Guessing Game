import java.util.Random;
import java.util.Scanner;

public class AdvancedNumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean exit = false;
        int totalRounds = 0;
        int roundsWon = 0;

        while (!exit) {
            System.out.println("\n=== Number Guessing Game ===");
            System.out.println("1. Play Game");
            System.out.println("2. View Rules");
            System.out.println("3. View Score");
            System.out.println("4. Exit");
            System.out.print("Choose an option (1-4): ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    boolean roundResult = playGame(scanner);
                    totalRounds++;
                    if (roundResult) {
                        roundsWon++;
                    }
                    break;
                case 2:
                    viewRules();
                    break;
                case 3:
                    viewScore(totalRounds, roundsWon);
                    break;
                case 4:
                    exit = true;
                    System.out.println("Thank you for playing! Goodbye!");
                    break;
                default:
                    System.out.println("Invalid choice. Please select 1, 2, 3, or 4.");
            }
        }

        scanner.close();
    }

    private static boolean playGame(Scanner scanner) {
        Random random = new Random();
        int min = 1;
        int max = 100;
        int maxAttempts = 7;
        int targetNumber = random.nextInt((max - min) + 1) + min;
        int attempts = 0;
        boolean hasGuessedCorrectly = false;

        System.out.println("\nI have selected a number between " + min + " and " + max + ".");
        System.out.println("You have " + maxAttempts + " attempts to guess the correct number.");

        while (!hasGuessedCorrectly && attempts < maxAttempts) {
            System.out.print("Enter your guess: ");
            int guess = scanner.nextInt();
            attempts++;

            if (guess < min || guess > max) {
                System.out.println("Please enter a number between " + min + " and " + max + ".");
            } else if (guess < targetNumber) {
                System.out.println("Too low! Try again.");
            } else if (guess > targetNumber) {
                System.out.println("Too high! Try again.");
            } else {
                System.out.println("Congratulations! You guessed the correct number: " + targetNumber);
                hasGuessedCorrectly = true;
                System.out.println("It took you " + attempts + " attempts.");
            }
        }

        if (!hasGuessedCorrectly) {
            System.out.println("Sorry, you have used all " + maxAttempts + " attempts. The correct number was " + targetNumber + ".");
        }

        return hasGuessedCorrectly;
    }

    private static void viewRules() {
        System.out.println("\n=== Game Rules ===");
        System.out.println("1. The computer will randomly select a number between 1 and 100.");
        System.out.println("2. You need to guess the number.");
        System.out.println("3. After each guess, you will be told whether your guess is too high, too low, or correct.");
        System.out.println("4. You have a maximum of 7 attempts to guess the correct number.");
        System.out.println("5. Each round you win will be counted towards your score.");
        System.out.println("===================");
    }

    private static void viewScore(int totalRounds, int roundsWon) {
        System.out.println("\n=== Your Score ===");
        System.out.println("Total rounds played: " + totalRounds);
        System.out.println("Rounds won: " + roundsWon);
        if (totalRounds > 0) {
            double winRate = ((double) roundsWon / totalRounds) * 100;
            System.out.println("Win rate: " + String.format("%.2f", winRate) + "%");
        }
        System.out.println("===================");
    }
}
