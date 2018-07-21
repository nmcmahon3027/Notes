# Notes
//interface EJ Media Youtube)

(14)**Interfaces**
    Planet Earth = new Planet();

    Earth.size = 25000;

    Planet Hupiter = new Planet();
    //Planet is its own interface
    
    **Converting/ Casting**
    
    double source = 150.50;//variable to variable casting
    int destination = (int) source;
    
    int I = 125;
    byte B = (byte) I; //be aware of ranges (-127 to 127) This is EXPLICIT CASTING (can see)
    //byte to int better
    
    //declaring new object
    //NEED Java's METHODS to cast objects
    //BELOW: Object to Variable
   
    Integer wholeNumber = new Integer(400); //this is an object
    //Integer has a corresponding OBJECT in java==> Integer int, char Character, byte Byte
    //basically each object has a corresponding DATA TYPE
    int dest = wholeNumber.intValue(); //storing 400 into dest
    //METHOD .intValue() is coming from class Integer(pre-canned class)
    System.out.print(dest);
    
    String to Object
    
    String val = "47"; //ONLY numeric, if "47ccc" NOOO go, Exception errors!
    int intObject = Integer.parseInt(val);
    System.out.print(val);
    
    //OUTPUT: 47
    
    
    (pt. 16)
    **Constructors**
    
    //Constructor names MUST MATCH class name!!
    
    public class Addition{
    
    int firstNumber;
    int secondNumber;
    
    public int getNumber() {
    
      return(firstNumber + secondNumber);
      }
      
      Addition() {  //constructor
      
        firstNumber = 10;
        secondNumber = 20;
        }
      Addition(int L, int B) { //these arguments are what makes this Addition unique
        
        firstNumber = L;
        secondNumber = B;
      }
    
    
    (Pt 17)
    **Access Modifiers**
    
    public class ClassTemplate { //only PUBLIC or DEFAULT
    
    int day = 1; //visible to the package
    public int week = 7; // world visible
    protected int month = 31; //visible to package. the default
    private int year = 365; //vis. to class only
    
    public int printWeek () { //has access to all (private or not) so those variables are not messed up
                               //METHODS SHOULD mostly ALWAYS be public so other classes(etc.) can be used
        return week + day + month + year;
        }
      }//access private varibales through public methods 
      //variables you set resticitions on
      
      
    (Pt. 18)
    //**Void and Return Methods**
//void basically means not returning a value
 //If void is in method, NOT RETURNING ANYTHING
 
 ++CLASS: Food.java
 ++CLASS: HamburgerJoint.java (main)
 
 public class Food {
 
 private String foodA; //private variables is good practice
 
 public Food (String A) { //constructor
 
        foodA = A;
  
 }
 
 public String getFood() {
 //making PUBLIC METHOD it has access to PRIVATE VARIABLE: String foodA==>bc its in the same class
 
 return foodA;//use return when a value is returned   //sout tab (syso)
 }    
 
 void systemPrint() { void ONLY if nothing is returned
 
    System.out.println(foodA);
 
 }
 
 //CLASS: HamburgerJoint
 
 public class HaburgerJoint {
 
    public static void main(String[] args) {
    
    Food servingA = new Food("Hamburger");  //DECLARE OBJECT, Food class
    
    System.out.println(servingA.getFood()); 
    servingA.systemPrint(); //void method
    
    }
    
    
    //**(Pt 19)
    //**static variables and static methods**
    
    public class Registration {
    
        private String usernameA;// Object or Instance variables DO GO AWAY
        private static in usernameCount = 0;//static variables NEVER go away 
        
        //use class name to refer to STATIC VARIABLES
    
        public Registration (String A) { //CONSTRUCTOR 
        
            usernameA = A;
            usernameCount++;
            
           } 
           
    public String putUsernameDatabase() { //return method
    
        return usernameA; //puts username into database
        
        }
        
    public static int getUsernameCount() {//static method  
    
        return usernameCount;
        
        }
     }   
    
    
    
    
    
    //**Main.java**
    
    public class Main {
    
        public static void main(String[] args) {
        
            Registration newuser1 = new Registration("Mary");//new (keyword) invokes CONSTRUCTOR Registation
            System.out,println(newuser1.putUsernameDatabase()
                    + " username created and entered into datanase");
                    
             Registration newuser2 = new Registration("Larry");
            System.out,println(newuser2.putUsernameDatabase()
                    + " username created and entered into datanase");
                    
            System.out.println(Registration.getUsernameCount()); //Boss:"Get me the # of users"        
            
    
    //NOTE: STATIC METHODS & STATIC VARIABLES go together like 2 pees in a pod!
    //Static method should go after Static variable 
    
    
    
    
