package internship;

import java.util.Scanner;
import java.util.Random;

public class NumberGuessingGame {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        Random rd = new Random(0);

        int lowerRange = 1;
        int upperRange = 100;
        int maxAttemps = 10;
        int round = 0;
        int totalAttemp = 0;

        System.out.println("Welcome to the number Gusseing Game");

        while(true){
            int secretNumber = rd.nextInt(upperRange - lowerRange + 1);
            int attempts = 0;

            System.out.println("Round " + (round + 1));

        while(attempts < maxAttemps) {
            System.out.println("Guess the number between " + lowerRange + " and " + upperRange + " : " );

            int userGUess = sc.nextInt();
            attempts++;

            if(userGUess < secretNumber) {
                System.out.println("Too low! Try again");
            }
            else if(userGUess > secretNumber){
                    System.out.println("Too high! Try again");
                }
            else{
                System.out.println("Congratulations! You gussed the number " + secretNumber + " in " + attempts + " attempts.");
                totalAttemp += attempts;
                break;
            }

            if(attempts == maxAttemps){
                System.out.println("Sorry, you have used all the attempts. the correct number was " + secretNumber);
            }
        }

        round ++;

            System.out.println("Do you want to play again? (yes/no): ");
            String playAgain = sc.next();

            if(!playAgain.equalsIgnoreCase("yes")){
                break;
            }
        }
        System.out.println("Game over! You played " + round + " round and took " + totalAttemp + " attempts.");
    }
}
