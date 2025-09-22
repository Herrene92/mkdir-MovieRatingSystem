import java.util.Scanner;

public class MovieRatingSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String userName = scanner.nextLine();

        String[] movies = new String[5];
        int[] ratings = new int[5];

        for (int i = 0; i < 5; i++) {
            System.out.print("Enter movie #" + (i + 1) + ": ");
            movies[i] = scanner.nextLine();

            int rating;
            do {
                System.out.print("Rate \"" + movies[i] + "\" (1-10): ");
                rating = scanner.nextInt();
            } while (rating < 1 || rating > 10);
            ratings[i] = rating;
            scanner.nextLine(); // consume newline
        }

        int total = 0;
        for (int rating : ratings) {
            total += rating;
        }
        double average = total / 5.0;
        System.out.printf("\nAverage rating: %.2f\n", average);

        if (average >= 9) {
            System.out.println("You are a cinephile!");
        } else if (average >= 7) {
            System.out.println("You enjoy movies quite a bit.");
        } else if (average >= 5) {
            System.out.println("You have mixed feelings about movies.");
        } else {
            System.out.println("You are a tough critic!");
        }

        boolean hasMasterpiece = false;
        boolean hasDislike = false;

        for (int rating : ratings) {
            if (rating == 10) hasMasterpiece = true;
            if (rating < 4) hasDislike = true;
        }

        if (hasMasterpiece) {
            System.out.println("Wow! You found a masterpiece.");
        }
        if (hasDislike) {
            System.out.println("That movie didn’t impress you much.");
        }

        boolean allHigh = true;
        boolean anyLow = false;

        for (int rating : ratings) {
            if (rating < 7) allHigh = false;
            if (rating < 3) anyLow = true;
        }

        if (allHigh) {
            System.out.println("You seem to enjoy most movies.");
        } else if (anyLow) {
            System.out.println("You have strong opinions on movies!");
        }

        System.out.print("\nEnter your favorite genre (Action, Comedy, Horror, Drama, Sci-Fi): ");
        String genre = scanner.nextLine();

        switch (genre.toLowerCase()) {
            case "action":
                System.out.println("You love excitement and thrills!");
                break;
            case "comedy":
                System.out.println("You enjoy a good laugh.");
                break;
            case "horror":
                System.out.println("You have a taste for fear!");
                break;
            case "drama":
                System.out.println("You appreciate deep storytelling.");
                break;
            case "sci-fi":
                System.out.println("You love futuristic and imaginative worlds!");
                break;
            default:
                System.out.println("Interesting choice!");
        }

        String recommendation = genre.equalsIgnoreCase("sci-fi") ? "Interstellar" : "The Dark Knight";
        System.out.println("Movie recommendation: " + recommendation);

        scanner.close();
    }
}
