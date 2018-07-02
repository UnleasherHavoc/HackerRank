import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    // Complete the catAndMouse function below.
    static String catAndMouse(int a, int b, int c) {
        int dist_ac=Math.abs(c-a);
        int dist_bc=Math.abs(c-b);
        //all in same location
            if(dist_ac==0&&dist_bc==0)
           {
               return "Mouse C";
           }
        //A is at C
      else  if(dist_ac==0)
      {
            return "Cat A";
        }
        //B is at C
       else  if(dist_bc==0)
       {
            return "Cat B";
        }
        
        
        //A and B have equal distance from C
        if(dist_ac==dist_bc)
        {
            return "Mouse C";
        }
        //A is more away than C
        else if(dist_ac>dist_bc)
        {
            return "Cat B";
        }
              else{
            
                  return "Cat A";
                   }
       
     }

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) throws IOException {
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        int q = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        for (int qItr = 0; qItr < q; qItr++) {
            String[] xyz = scanner.nextLine().split(" ");

            int x = Integer.parseInt(xyz[0]);

            int y = Integer.parseInt(xyz[1]);

            int z = Integer.parseInt(xyz[2]);

            String result = catAndMouse(x, y, z);

            bufferedWriter.write(result);
            bufferedWriter.newLine();
        }

        bufferedWriter.close();

        scanner.close();
    }
}
