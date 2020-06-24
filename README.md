// 2019112801 woo yebin

//import java.io.*;
import java.util.Scanner;

public class CountAlphabet {
  	public static void main(String[] args) throws Exception {
    		String URLString = "http://websitetips.com/articles/copy/lorem/ipsum.txt";
    		java.net.URL url = new java.net.URL(URLString);
		String[] alphabet = {"A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K",
			"L","M", "N", "O", "P", "Q", "R", "S", "T", "U","V", "W", "X", "Y", "Z"};
		int[] number = new int[26];
    		try ( Scanner input = new Scanner(url.openStream()))
    		{
    			while(input.hasNext()){
    				String line = input.nextLine();
    				String[] Arr = line.split("");
    				for (int i=0;i<Arr.length;i++){
    					for(int j=0; j<26; j++){
    						if((Arr[i].toUpperCase()).equals(alphabet[j])){
    							number[j]++;
    						}
    					}
    				}
    			}
			System.out.println("----------------------------------------------------");
    			for(int x = 0; x<13; x++) System.out.print(" "+alphabet[x]+","+alphabet[x].toLowerCase());
    			System.out.println();
    			for(int k = 0; k<13; k++) System.out.printf("%4d",number[k]);
    			System.out.println();
			System.out.println("----------------------------------------------------");
    			for(int x = 13; x<26; x++) System.out.print(" "+alphabet[x]+","+alphabet[x].toLowerCase());
    			System.out.println();
    			for(int k = 13; k<26; k++) System.out.printf("%4d",number[k]);
    			System.out.println("\n----------------------------------------------------");


    		}
    		catch(java.net.MalformedURLException ex){
    			System.out.println("Invalid URL");
    		}
    		catch (java.io.IOException ex){
    			System.out.println("IO Errors");
    		}
  	}

  /* Add methods if necessary */
}
