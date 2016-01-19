# BCC-Risk-Code

package interviewCode;

import java.awt.List;
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.lang.reflect.Array;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Arrays;

public class interviewCode {

	public static String [] lines = null;
	public static String [][] twod =new String [10][10];
	public static void main (String args[])
	{
		String fileName = "C:\\Users/user/it.txt";
		String line;
		try {
			line = new String(Files.readAllBytes(Paths.get(fileName)));
			lines = line.split("\n");
			for (int c = 0 ; c < lines.length; c++ )
			{
					twod [c] =  (lines[c].split(":"));
			}
		}
		catch(FileNotFoundException ex)
		{
			System.out.println("file not found ");
			
		}
		catch(IOException  ex){
			System.out.println("here");
		}
		getName("53237");
		String [] IDs = {"28112","53237","93823"};
		getTreat(IDs);
		Search("www.badbank.com");
		ordered();
	}
	
	
	

	public static void getName (String Number){
		
		for (int c =0 ; c < lines.length ;c++){
			
			if (Number.equals( twod[c][0] )){
				System.out.println(twod[c][1]);
			}
			
		}
		
	}
	public static void getTreat(String [] A){
		int c = 0 ;
		int i;
		for (i = 0 ; i < A.length;i++){
			for (int j = 0 ; j<lines.length;j++){
				if (A[i].equals(twod[j][0])){
					c = c + Integer.parseInt(twod[j][3].trim());
				}
			}
		}
		c=c/i;
		System.out.println("Average threat :"+c);
		
	}
	
	public static void Search (String url){
		for (int j = 0 ; j < lines.length ; j ++){
			if (twod[j][2].toLowerCase().contains(url.toLowerCase())){
				System.out.print(twod[j][0]+"\n");
			}
		}
		
		
	}
	public static void ordered(){
		for (int c = 5 ; c>0 ;c--){
			for (int i=0; i < lines.length;i++ ){
				if (c==(Integer.parseInt( twod[i][3].trim())))
						{
							System.out.println(twod[i][0]);
							System.out.println(twod[i][3]);
						}
			}
		}
	}
	
}
