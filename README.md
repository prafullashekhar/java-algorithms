# java-algorithms
contains important questions based on useful java algorithms.

Question 1:
A person wants to determine the most expensive computer keyboard and USB drive that can be purchased with a give budget - b. 
Given price lists for keyboards and USB drives and a budget, find the cost to buy them. 
If it is not possible to buy both items, return -1.
    ex- b=60
        keyboards = [40, 50, 60]
        drives = [5. 8, 12]
     print 58;
     
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int s = in.nextInt();
        int n = in.nextInt();
        int m = in.nextInt();
        Integer[] keyboards = new Integer[n];
        for(int keyboards_i=0; keyboards_i < n; keyboards_i++){
            keyboards[keyboards_i] = in.nextInt();
        }
        int[] pendrives = new int[m];
        for(int pendrives_i=0; pendrives_i < m; pendrives_i++){
            pendrives[pendrives_i] = in.nextInt();
        }
        
        Arrays.sort(keyboards, Collections.reverseOrder());//Descending order
        Arrays.sort(pendrives);//Ascending order
        
        int max = -1;
        for(int i = 0, j = 0; i < n; i++){
            for(; j < m; j++){
                if(keyboards[i]+pendrives[j] > s) break; //This prevents j from incrementing
                if(keyboards[i]+pendrives[j] > max)
                    max = keyboards[i]+pendrives[j];
            }
        }
        System.out.println(max);
    }
}
