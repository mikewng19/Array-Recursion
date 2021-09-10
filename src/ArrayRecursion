 
//Michael Wong

import java.util.Random;
import javax.swing.JOptionPane;

/**
 * A class that performs some simple array operations recursively
 */
public class ArrayRecursion {
    // instance var's

    private int[] list;       // array of ints
    private int count;         // number of elements

    /**
     * Create an ArrayRecursion object. Creates an array with between 10 and 15
     * elements, and fills it with random positive 2-digit ints
     */
    public ArrayRecursion() {
        Random r = new Random();
        count = r.nextInt(6) + 10;
        list = new int[count];

        for (int i = 0; i < count; i++) {
            list[i] = r.nextInt(90) + 10;
        }
    }

    /**
     * Return the list as a string
     *
     * @return a string containing all the ints stored in list
     */
    public String toString() {
        String out = "";
        for (int i = 0; i < count; i++) {
            out += list[i] + "  ";
        }
        return out + "\n";
    }

    /**
     * Returns the smallest value in the array.
     *
     * @return the smallest value in the array
     */
    public int getSmallest() {

        return recursiveGetSmallest(list, count);
    }

    // recursive "helper" method returns the smallest value in list.
    // called by public method getSmallest()
    private int recursiveGetSmallest(int[] list, int count) {
        
        //Base case:
        //If we have reached the end of the array, return the final value of
        //the array.
        if (count == 1) {
            return list[count];

        } else {
            
            //Compares the last element of an array with one array with 1 less
            //index/size containing all but the last element, and return smaller
            //value
            return Math.min(list[count - 1],
                    recursiveGetSmallest(list, count - 1));
        }

    }

    /**
     * Reverse the elements of the array
     */
    public void reverse() {
        recursiveReverse(list, 0, count);
    }

    // recursive "helper" method to reverse the array.
    // called by public method reverse()
    private void recursiveReverse(int[] list, int first, int count) {
        
        //Base case:
        //Since first and count will eventually equal the same
        //value(if unchecked). It will make unnecessary swaps.
        //This if statement prevents that from happening.
        if (first < count) {

            int tempValue = list[first]; //Contains the value of the first value 
            //of the array

            list[first] = list[count - 1]; //The first index of the array
            //gets the last value....

            list[count - 1] = tempValue; //Now the last index
            //gets the first value....

            recursiveReverse(list, first + 1, count - 1); //Increase the
            //first value to point to the next index, count now points to one
            //index before now.
        }
    }

    /**
     * Does the array contain two or more consecutive ints, ascending or
     * descending?
     *
     * @return true if array contains any consecutive ints; otherwise false
     */
    public boolean hasConsecutives() {
        return recursiveHasConsecutives(list, count);
    }

    // recursive "helper" method called by public method hasConsecutives()
    private boolean recursiveHasConsecutives(int[] list, int count) {
       
        //If count has reached 1, all of the values on the array have
        //been read and there is no consecutive elements.
        if (count == 1) {
            
            
            return false; 
        }
        
        //Contains the value of current index minus one less index.        
        int temp = list[count - 1] - list[count - 2];
        
        //since consecutive terms are just 1 number apart, they can only
        //equal two things. -1 or 1 (depending on the order of the array).
        if (temp == -1 || temp == 1) {
            
         
            return true; //Returns true because it found consecutive elements.
            
        } else {
            
            return recursiveHasConsecutives(list, count - 1);  //recursion
            //Shift the 'last index' one over from the current last index.
        }
    }

    public static void main(String[] args) {
        ArrayRecursion list = new ArrayRecursion();

        System.out.println("\nOriginal:  " + list);

        System.out.println("Smallest value in the array is "
                + list.getSmallest());
        list.reverse();
        System.out.println("\nReversed:  " + list);

        System.out.println("The list "
                + (list.hasConsecutives() ? "has" : "does not have")
                + " consecutive ints in consecutive elements");
    }
}
