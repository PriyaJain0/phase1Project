# phase1Project
package com.Mphasis.PracticeCode.FileCreatation;

import java.io.File;
import java.io.IOException;
import java.util.ArrayList;
import java.util.Scanner;

public class Project {
  static  String pathMyPc="E:\simplilern\";
  
  //create File ....
  public static void genaretFile(String fileName) throws IOException 
  {
    String filePath=pathMyPc;
    ArrayList<String> aList=new ArrayList<String>();
    
    System.out.println("Enter the name of the file to be added");
    String finalname=filePath+fileName;
    
    File f=new File(finalname);
    boolean b=f.createNewFile();
    if(b!=true) 
    {
      System.out.println("the file not created");
    }
    else 
    {
      aList.add(fileName);
      System.out.println("file created");
    }
    
   
  //Delete Function
  
  public static void deleteFile(String fileName) {
    String path=pathMyPc;

    String finalfile=path+fileName;
    File file=new File(finalfile);
    file.delete();
    System.out.println("file deleted");
    
  }
  //Searching Function
  
  public static void serchFile(String serchingFileName) {
    String path=pathMyPc;
    File f=new File(path);
    File filename[]=f.listFiles();
    int count=0;
    for(File ff:filename) {
      
      if(ff.getName().equals(serchingFileName))
      {
        count++;
        break;
      }else {
        count=0;
      }
    }
    if (count!=0) {
      System.out.println("You have "+serchingFileName+" File :)");
      
    }else {
      System.out.println("File is not found");
    }
  }
  
  //Display File List...
  
  public  static void displayFile() {
    String path=pathMyPc;
    File f=new File(path);
    File filename[]=f.listFiles();
    System.out.println("Your File List - ");
    for(File ff:filename) {
      System.out.println(ff.getName());
    }
  }
  
  
  
  //Main Method Start....
  
  public static void main(String[] args) throws IOException {
    
    Scanner scanner =new Scanner(System.in);
    boolean c=true;
    //for stop Main menu;
    
    
    while(c) {
      System.out.println("***********Welcome to LookMe.com ***********");
      System.out.println("•Retrieve all file names -: Press 1");
      System.out.println("•Display menu for File operations- : Press 2");
      System.out.println("•Exit program -: Press 3");
      System.out.println();
      boolean b=true;
      int x=scanner.nextInt();
      switch (x) {
      case 1:{
        displayFile();
        System.out.println();
        break;
      }
      case 2: 
      {  while(true) {
        System.out.println("** Select any option number from below and press Enter **");
        System.out.println();
        System.out.println("Add / Create a File : Press 1");
        System.out.println("Delete a file : Press 2");
        System.out.println("Search for a file : Press 3");
        System.out.println("Show Previous Menu : Press  4");
        System.out.println();
        int i=scanner.nextInt();
        
        if(i<=0 || i>=6) {                  //If No is not range the,,,,It working
          
          System.out.println("Please select a valid option from  above.");
          System.out.println();
      
        }else{ 
                if(i==1){
                  System.out.println("Enter the File Name for Create");
                    
                  String  FileForCreate=scanner.next();
                  genaretFile(FileForCreate);
                  System.out.println();
                  
                }
                else if(i==2) {
                  System.out.println("Enter the File Name for Delete");
                  String FileForDelete=scanner.next();
                  deleteFile(FileForDelete);
                  System.out.println();
                }
                else if(i== 3) {
                  System.out.println("Enter the File Name for Serching");
String FileForSerching=scanner.next();
                  serchFile(FileForSerching);
                  System.out.println();
                }
                else if(i==4) {
                  
                  System.out.println("Welcome in Main menu");
                  System.out.println();
                  break;
                }
          
          
              
            }
            
            
      }
      break;
        }
      
      case 3:{
        System.out.println("Program exited successfully");
        c=false;
        break;
        
      }
      }
      
      
      
      
    }
    
  }

}
