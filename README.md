# Homework2

import java.io.*;
import java.util.Scanner;
import java.lang.Math;

public class Homework2 {

    public static void main(String[] args) throws IOException{

	Scanner keyboard = new Scanner(System.in);
  
  //importing prompt for users to insert input and output files name 
	System.out.print("Enter the input file name: ");
	String inFile=keyboard.next();
	System.out.print("Enter the output file name: ");
	String outFile =keyboard.next();

 
	PrintWriter pw = new PrintWriter(outFile);
  //This will open the file
	File file = new File(inFile);
	Scanner inputFile = new Scanner(file);
  //This will read the data from the file
	while (inputFile.hasNext()) {
	    String line =inputFile.nextLine();

      //Tokenize the line 
	    String[] tokens = line.split(",");
      //this displays teh contents of the tokens array 
	    for(String token : tokens)
		System.out.println(token);
      //converts the token to a double
	    double price = Double.parseDouble(tokens[2]);
      //converts the second token to a double
	    double discount = Double.parseDouble(tokens[3]);
      
      //calculating the total
	    double total = price - (price * (discount/100));
      //calculating the tax
	    double tax = total * 0.08875;
      //printing out the results 
	    System.out.println("The total is " + total);
	    System.out.println("The tax is " + tax);

      //printing out the highest price
	    if (total > price)
		System.out.println("The highest price item is " + price);
	    else
		System.out.println("The highest price item is " + total);
      //printing out the lowest price
	    if (total < price)
		System.out.println("The lowest price item is " + price);
	    else
	        System.out.println("The lowest price itme is " + total);

    System.out.println("Report Completed ");
}
//closing the files
inputFile.close();
pw.close();
}
}
