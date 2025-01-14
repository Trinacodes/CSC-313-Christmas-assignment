# CSC-313-Christmas-assignment
1. public class NigeriaFlagSingleLoop {
    public static void main(String[] args) {
        int height = 6; // Number of rows
        int width = 9; // Number of columns

        for (int i = 0; i < height * width; i++) {
            if (i % width < width / 3 || i % width >= 2 * width / 3) {
                System.out.print("G"); // Green stripe
            } else {
                System.out.print("W"); // White stripe
            }
            if (i % width == width - 1) {
                System.out.println();
            }
        }
    }
}

Using Nested loop

public class NigeriaFlagNestedLoop {
    public static void main(String[] args) {
        int height = 6; // Number of rows
        int width = 9; // Number of columns

        for (int i = 0; i < height; i++) {
            for (int j = 0; j < width; j++) {
                if (j < width / 3 || j >= 2 * width / 3) {
                    System.out.print("G"); // Green stripe
                } else {
                    System.out.print("W"); // White stripe
                }
            }
            System.out.println();
        }
    }
}

2. import java.util.Arrays;

public class Statistics {
    public static void main(String[] args) {
        int[] data = {2, 5, 5, 9, 4, 7, 0, 9, 6, 11, 12};

        // Calculate mean
        double mean = calculateMean(data);
        System.out.println("Mean: " + mean);

        // Calculate median
        double median = calculateMedian(data);
        System.out.println("Median: " + median);

        // Calculate standard deviation
        double standardDeviation = calculateStandardDeviation(data, mean);
        System.out.println("Standard Deviation: " + standardDeviation);
    }

    // Method to calculate mean
    public static double calculateMean(int[] data) {
        int sum = 0;
        for (int num : data) {
            sum += num;
        }
        return (double) sum / data.length;
    }

    // Method to calculate median
    public static double calculateMedian(int[] data) {
        Arrays.sort(data);
        int middle = data.length / 2;
        if (data.length % 2 == 0) {
            return (data[middle - 1] + data[middle]) / 2.0;
        } else {
            return data[middle];
        }
    }

    // Method to calculate standard deviation
    public static double calculateStandardDeviation(int[] data, double mean) {
        double sum = 0;
        for (int num : data) {
            sum += Math.pow(num - mean, 2);
        }
        return Math.sqrt(sum / data.length);
    }
}

3. import java.util.Scanner;

public class UserInputArray {
    public static void main(String[] args) {
        // Declare an array of length 10
        int[] array = new int[10];
        Scanner scanner = new Scanner(System.in);

        // Assign elements to the array by accepting input from the user
        for (int i = 0; i < array.length; i++) {
            System.out.println("Please enter a number for index " + i + ":");
            array[i] = scanner.nextInt();
        }

        // Print out the input entered by the user using a for-each loop
        System.out.println("You entered the following numbers:");
        for (int num : array) {
            System.out.print(num + " ");
        }
        scanner.close();
    }
}
4. import java.util.Scanner;

public class UserInput2DArray {
    public static void main(String[] args) {
        // Declare a 2D array of size 10 by 10
        int[][] array = new int[10][10];
        Scanner scanner = new Scanner(System.in);

        // Assign elements to the array by accepting input from the user
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                System.out.println("Please enter a number for index [" + i + "][" + j + "]:");
                array[i][j] = scanner.nextInt();
            }
        }

        // Print out the input entered by the user using a for-each loop
        System.out.println("You entered the following numbers:");
        for (int[] row : array) {
            for (int num : row) {
                System.out.print(num + " ");
            }
            System.out.println();
        }
        scanner.close();
    }
}
