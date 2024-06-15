import java.util.InputMismatchException;
import java.util.Random;
import java.util.*;

public class GuessTheNumber {
    static final int LOWER_LIMIT = 1;
    static final int UPPER_LIMIT = 100;
    static final int ATTEMPTS_LIMIT = 10;

    public static void main(String[] args) {
        displayHeader();

        Scanner sc = new Scanner(System.in);
        Random random = new Random();

        int roundsPlayed = 0;
        int totalMarks = 0;

        boolean playAgain = true;

        while (playAgain) {
            int targetNumber = random.nextInt(UPPER_LIMIT - LOWER_LIMIT + 1) + LOWER_LIMIT;

            System.out.println("\nRound " + (roundsPlayed + 1) + ": Guess the number between " + LOWER_LIMIT + " and " + UPPER_LIMIT);

            countdownAnimation();

            int attempts = 0;

            while (attempts < ATTEMPTS_LIMIT) {
                System.out.print("Enter your guess: ");

                try {
                    int userGuess = scanner.nextInt();

                    if (userGuess < LOWER_LIMIT || userGuess > UPPER_LIMIT) {
                        System.out.println("Please enter a guess between " + LOWER_LIMIT + " and " + UPPER_LIMIT + ".");
                    } else {
                        if (userGuess == targetNumber) {
                            displayWinAnimation();
                            int roundScore = Math.max(0, 100 - (attempts * 10));
                            System.out.println("Congratulations! You guessed the correct number " + targetNumber + " in " + (attempts + 1) + " attempts. \nRound Score: " + roundScore);
                            totalMarks += roundScore;
                            break;
                        } else if (userGuess < targetNumber) {
                            System.out.println("Too low! Try again.");
                        } else {
                            System.out.println("Too high! Try again.");
                        }

                        attempts++;
                    }
                } catch (InputMismatchException e) {
                    System.out.println("Please enter a valid integer.");
                    scanner.next();
                }
            }

            if (attempts == ATTEMPTS_LIMIT) {
                System.out.println("\nSorry, you've reached the maximum number of attempts. The correct number was " + targetNumber + ".");
            }

            roundsPlayed++;

            System.out.println("Round " + roundsPlayed + " Total Score: " + totalMarks);

            System.out.print("\nDo you want to play again? (yes/no): ");
            playAgain = scanner.next().toLowerCase().equals("yes");
        }

        System.out.println("\nGame Over! Total Score: " + totalMarks);

        scanner.close();
    }

    private static void displayHeader() {
        System.out.println("");
        System.out.println("*      Welcome to Guess the Number       *");
        System.out.println("*    Can you guess the secret number?    *");
        System.out.println("*    You have " + ATTEMPTS_LIMIT + " attempts per round.       *");
        System.out.println("\n");
    }

    private static void displayWinAnimation() {
        System.out.println("\n*");
        System.out.println("   Congratulations!!!   ");
        System.out.println("        You Win!        ");
        System.out.println("    \\o/       \\o/       ");
        System.out.println("     |         |        ");
        System.out.println("    / \\       / \\       ");
        System.out.println("*\n");
    }

    private static void countdownAnimation() {
        for (int i = 3; i > 0; i--) {
            System.out.print("\rGet ready in " + i + "...");
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
        System.out.println("\rGet ready!              ");
    }
}
