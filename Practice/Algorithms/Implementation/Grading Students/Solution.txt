import java.io.*;
import java.math.*;
import java.text.*;
import java.util.*;
import java.util.regex.*;

public class Solution {

    
    static int[] gradingStudents(int[] grades) {
       
        for(int i=0;i<grades.length;i++){
            if(grades[i]<38){}
            else{int  lastdigit=grades[i]%10;
                 int temp=0;
                              if(lastdigit<=5&&lastdigit!=0)
                              {
                                  lastdigit=5-lastdigit;
                                  temp =grades[i]+lastdigit;
                                                                                              
                              }
                            else
                            {  lastdigit=10-lastdigit;
                               temp =grades[i]+lastdigit;
                            }
                
                 if(temp-grades[i]<3){grades[i]=temp;}
                
                
                
            }
            
            
        }
        
        return grades;
    }

    private static final Scanner scan = new Scanner(System.in);

    public static void main(String[] args) throws IOException {
        BufferedWriter bw = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        int n = Integer.parseInt(scan.nextLine().trim());

        int[] grades = new int[n];

        for (int gradesItr = 0; gradesItr < n; gradesItr++) {
            int gradesItem = Integer.parseInt(scan.nextLine().trim());
            grades[gradesItr] = gradesItem;
        }

        int[] result = gradingStudents(grades);

        for (int resultItr = 0; resultItr < result.length; resultItr++) {
            bw.write(String.valueOf(result[resultItr]));

            if (resultItr != result.length - 1) {
                bw.write("\n");
            }
        }

        bw.newLine();

        bw.close();
    }
}
