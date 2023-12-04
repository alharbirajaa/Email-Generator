import java.util.*;  // to take input
import java.text.*;
public class Email          
{  
   //Used in generateRandomPassword()
   private static final Random random = new Random(); 
   private static final String CharLower = "abcdefghijklmnopqrstuvwxyz";
   private static final String CharUpper = CharLower.toUpperCase();
   private static final String Numbers = "0123456789";
   private static final String SYMBOLS = "@$#";
   /*Attributes*/
   private String FirstName, LastName, email, password, department, alternateEmail;
   private Date dateOfBirth;
   // Used take the user department
   char choice;
   /*Constructer*/      
   public Email(String FName, String LName){
     FirstName = FName;
     LastName = LName; 
     setDateOfBirth();
     setAlternateEmail();
     setDepartment();
     password = generateRandomPassword();
     email = generateEmail();
   }       
   /*Methods*/
   public String setDepartment(){  //To ask the user about which department
      while(choice != 'a' && choice != 'c' && choice != 'i' && choice !='m'){
        System.out.println("Choose your department : ");
        System.out.println("a. Applied Linguistic\nc. Computer Science and Engineering\ni. Interior Design\nm. Management Science");
        Scanner sc = new Scanner(System.in);
        choice = sc.next().charAt(0);
        if (choice == 'a' || choice == 'A')
           return department = "Applied Linguistic";
        else if (choice == 'c' || choice == 'C')      
           return department ="Computer Science and Engineering";
        else if (choice == 'i' || choice == 'I')
           return department ="Interior Design"; 
        else if (choice == 'm' || choice == 'M')
           return department ="Management Science" ;
        else
           System.out.println("Please enter valid choice.");
             
    } return department; }
   public String generateEmail(){    //create an email for the student based on the department
       String dep="";
       if(department.equals("Applied Linguistic")) dep = "al";
       else if(department.equals("Computer Science and Engineering")) dep = "cse";
       else if(department.equals("Interior Design")) dep = "id";
       else if(department.equals("Management Science")) dep = "ms"; 
       return FirstName.toLowerCase() + "." + LastName.toLowerCase() + "@" + dep + ".yuc.com";
   }
   public String generateRandomPassword(){        //Create a random password
       int passLength = 12;
       StringBuilder pass = new StringBuilder(passLength);
       String lowerAlpha = generateRandomString(CharLower, 4);
       String upperAlpha = generateRandomString(CharUpper, 4);
       String numbers = generateRandomString(Numbers, 2);
       String symbols = generateRandomString(SYMBOLS, 2);
       pass.append(lowerAlpha).append(upperAlpha).append(numbers).append(symbols);
       List<String> result = Arrays.asList(pass.toString().split(""));
       Collections.shuffle(result);
       return String.join("", result); 
   }
   private static String generateRandomString(String input, int size) {
       StringBuilder result = new StringBuilder(size);
       for (int i = 0; i < size; i++) {
           int index = random.nextInt(input.length());
           result.append(input.charAt(index));
       }
       return result.toString();
   }
   public void setDateOfBirth() {  // Take the user Date of birth
       Scanner s = new Scanner(System.in);
       System.out.println("Enter your Date of Birth:");
       System.out.print("Day:");
       int day = s.nextInt();
       System.out.print("Month:");
       int month = s.nextInt();
       System.out.print("Year:");
       int year = s.nextInt();
       String date = year+"/"+month+"/"+day;
       dateOfBirth = new Date(date);
       SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd");
       simpleDateFormat.format(dateOfBirth);
   }
   public void setAlternateEmail(){   // Take The user alternate email 
       Scanner n = new Scanner(System.in);
       System.out.print("Enter alternate email: ");
       alternateEmail = n.next(); 
   }
   // get methods to all Attributes
   public String getAlternateEmail() {return alternateEmail;}
   public String getEmail() {return email;}    
   public String getPassword() {return password;}
   public String getDepartment() {return department;}
   public Date getDateOfBirth() {return dateOfBirth;}
   //@Override - To Display the Details//
   public String toString() {
    return "\nFirst Name : "+FirstName+"\nLast Name : "+LastName+"\nDepartment Name : "+department+"\nEmail : "+email+"\nAlternate Email : "+alternateEmail;
  }
}
