import java.util.*;
import java.io.*;
import java.math.*;
class Solution {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);
        int N = in.nextInt();
        int Q = in.nextInt(); 

        boolean[] coins = new boolean[N];
        int tailsCount = 0;

        for(int i = 0; i < coins.length; i++){
            coins[i] = true;
        }

        for (int i = 0; i < Q; i++) {
            int L = in.nextInt();
            int R = in.nextInt();

            for(; L <= R; L++){
                coins[L] = !coins[L];
            }

            for(int j = 0; j < coins.length; j++){ //Visualize the coins
                if(coins[j]){
                    System.out.print("0 "); //tail
                } else {
                    System.out.print("X "); //head
                }
                
            }
            System.out.println(" ");
        }

        for(int i = 0; i < coins.length; i++){
            if(coins[i]){
                tailsCount++;
            }
        }

        System.out.println(tailsCount);
    }
}