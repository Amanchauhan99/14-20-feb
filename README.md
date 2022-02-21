# 14-20-feb
1) intersection

package myProjects;

public class Intersection {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int []a= {1,2,3,4,5};
		int []b= {3,5,2,6,1};
		interSection(a,b);

	}
	private static int interSection(int[]a,int[]b) {
		for(int i=0;i<a.length;i++) {
			for(int j=0;j<b.length;j++) {
				if(a[i]==b[j]) {
					
					System.out.println(b[j]);
				}
			}
		}
		return 0;
	}

}

2)second largest no.

package myProjects;
import java.util.*;

import java.util.Arrays;

public class SecondLargestArray {



	public static void main(String[] args) {
 
		
		  System.out.println(secondlargest(a,6));
	}
private static int secondlargest(int[]a,int total) {
		Arrays.sort(a);
		return a[total-2];
		
		
		}
	}
  
3)  spiral
  
  package myProjects;
import java.util.*;

import java.util.Arrays;

public class SecondLargestArray {

	public static void main(String[] args) {

	    int R = 3; 
	    int C = 6; 
	    int arr[][] = { {1,  2,  3,  4,  5,  6}, {14,  15,  16,  17, 18, 7},  {13, 12, 11, 10, 9, 8} }; 
	     spiralPrint(R,C,arr);
	   

	}
  
  	private static int spiralPrint(int m, int n, int arr[][]) 
    { 
        int  k = 0, l = 0; 
           
        while (k < m && l < n) 
        { 
            for (int i = l; i < n; ++i) 
            { 
                System.out.print(arr[k][i]+" "); 
            } 
            k++; 
    
            for (int i = k; i < m; ++i) 
            { 
                System.out.print(arr[i][n-1]+" "); 
            } 
            n--; 
    
            if ( k < m) 
            { 
                for (int i = n-1; i >= l; --i) 
                { 
                    System.out.print(arr[m-1][i]+" "); 
                } 
                m--; 
            } 
   
            if (l < n) 
            { 
                for (int i = m-1; i >= k; --i) 
                { 
                    System.out.print(arr[i][l]+" "); 
                } 
                l++;     
            }      
           
        }
		return l; 
    }
	
}

4)frequency of odd and even  and sum of anti diagonal

package myProjects;

public class ArrayOddEven {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
    // anti diagonal
		int d[][]= {{4, 1, 3},{3, 5, 7},{8, 2, 6}};
		AntiDiagonal(d);
    //odd even
		  int a[][] = {{4, 1, 3},{3, 5, 7},{8, 2, 6},{6,4,45}};
	      OddEven(a);

	}
	private static int OddEven(int[][]a) {
		   int rows, cols, countOdd = 0, countEven = 0;  

	         rows = a.length;  
	       cols = a[0].length;  
	         
	       
	       for(int i = 0; i < rows; i++){  
	           for(int j = 0; j < cols; j++){  
	             if(a[i][j] % 2 == 0)  
	               countEven++;  
	             else  
	               countOdd++;  
	           }  
	       }  
	         
	       System.out.println("Frequency of odd numbers: " + countOdd);  
	       System.out.println("Frequency of even numbers: " + countEven);
		return countEven;  
	   }

	private static int AntiDiagonal(int[][]d) {
		int diagonal=2,sum = 0;
		for(int i=0;i<d.length;i++) {
			for(int j=0;j<d[0].length;j++) {
				if(i+j==diagonal) {
					sum=sum+d[i][j];
				}				
			}	
		}
		System.out.println(sum);
		return sum;
	}
	
	}
  
  6. Change all elements of row `i` and column `j` in a matrix to 0 if cell `(i, j)` is 0 

package myProjects;

import java.util.Arrays;

public class Zero {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
	    

	       int[][] mat =
	           {
	               { 1, 1, 0, 1, 1 },
	               { 1, 1, 1, 1, 1 },
	               { 1, 1, 0, 1, 1 },
	               { 1, 1, 1, 1, 1 },
	               { 0, 1, 1, 1, 1 }
	           };
	    
	           
	           convert(mat);
	    
	           for (int[] r: mat) {
	               System.out.println(Arrays.toString(r));
	           }
	}
	       
	
	public static void modifyMatrix1(int mat[ ][ ], int R, int C)
	{
	    int row[ ]= new int [R];
	    int col[ ]= new int [C];
	    int i, j;

	    for (i = 0; i < R; i++)
	    {
	    row[i] = 0;
	    }

	    for (i = 0; i < C; i++)
	    {
	    col[i] = 0;
	    }

	    for (i = 0; i < R; i++)
	    {
	        for (j = 0; j < C; j++)
	        {
	            if (mat[i][j] == 1)
	            {
	                row[i] = 1;
	                col[j] = 1;
	            }
	        }
	    }

	    for (i = 0; i < R; i++)
	    {
	        for (j = 0; j < C; j++)
	        {
	            if ( row[i] == 1 || col[j] == 1 )
	            {
	                mat[i][j] = 1;
	            }
	        }
	    }
	}
	 

	public static void changeRowColumn(int[][] mat, int M, int N, int x, int y)
	{
	    for (int j = 0; j < N; j++)
	    {
	        if (mat[x][j] != 0) {
	            mat[x][j] = -1;
	        }
	    }

	    for (int i = 0; i < M; i++)
	    {
	        if (mat[i][y] != 0) {
	            mat[i][y] = -1;
	        }
	    }
	}


	public static void convert(int[][] mat)
	{

	    if (mat == null || mat.length == 0) {
	        return;
	    }


	    int M = mat.length;
	    int N = mat[0].length;


	    for (int i = 0; i < M; i++)
	    {
	        for (int j = 0; j < N; j++)
	        {
	            if (mat[i][j] == 0)            
	            {

	                changeRowColumn(mat, M, N, i, j);
	            }
	        }
	    }
	

	    for (int i = 0; i < M; i++)
	    {
	        for (int j = 0; j < N; j++)
	        {
	            if (mat[i][j] == -1) {
	                mat[i][j] = 0;
	            }
	        }
	    }
	}
	}
