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
    
    
    //**(Pt 20) 
    //**MORE static variables**
    
    //2 main ways of referenceing static variables: through static variables or the constructor (name)
    
    //1
    newuser2.usernameCount++;
    System.out.println(newuser2.usernameCount);
    
    //2
    Registration.usernameCount++;
    System.out.println(Registration.usernameCount);
    
    //Also, you can RESET  a static variable
    Registration.usernameCount = 0;
    System.out.println(Registration.usernameCount);
    
    
    //**(Pt.21)
    //**Variable Scope**
    
    //when creating a variable or object inside a method, its usable ONLY inside THAT METHOD
    //If want other method to be able to reference those variables, must DEFINE them OUTSIDE METHOD IN CLASS
    
    public class Scope {
    
    
    
    //var. outside method, alailable to other methods
    public static void main(String[] args) { //start local
    
    int number = 7; //local variable-DECLARING it & INITIALIZING it
    
    //a variable doesnt get init. until its assigned a value
    
    }//end local
    
    
    public class Scope {
    
    static int number = 7; //MUST be STATIC for other methods to reach it
    
    //var. outside method, alailable to other methods
    public static void main(String[] args) { 
    
    //int number = 7; 
    
    
    
    }
    
    static void getNumber() {
    
        System.out.println(number);//can be reached because static int outside methods, 
                                    //static methods need static variables
                                    //GREEN = GLOBAL 
        
    }
    
    }
    
    
    //**(Pt22)
    //**"this" keyword**
    
    public class This {
    
        private int one;        //Object or Instance var.
        public This (int one) {
        
        this.one = one;     //local var.
        
   }
   
   public static void main(String [] args) {
   
        This testThis = new This (79);
        
        System.out.println(testThis.one);
        
        
     }
     
    // OUTPUT: 79
    
    //**(Pt.23)
    //**default Constructor**
    
   //psvm (tab) for main method
   
   public class NewEmpty {
   
   //public NewEmpty() {  //EXPLICIT CONSTRUCTOR, SAME as new NewEmpty(); below
   
   }
   
    int x = 10;
    int y = 11;
    
    public static void main(String args[]) {
    
        NewEmpty test = new NewEmpty(); //DEFAULT/IMPLICIT CONSTRUCTOR, NO ARGUMENTS ALLOWED
                                        //IMPLICT bc didnt type out above
                                        
                         //Creates a COPY (or Instantiates class NewEmpty() ) & calls it test              
        System.out.println(test.x);
    }
    
    }

    //**(Pt. 24)**
    //**Constructors vs methods**
    
    //construcor comes first then the methods
    //CONSTRUCTORS CANNOT RETURN values, METHODS can
    //NO void or static in Constructors!!
    //Access modifiers (public, protected, etc.) CAN be used by BOTH (SIGNITURES)
    
    
    //**(Pt.25)**
    //**Using "super" keyword in methods**
    
    
  public class ChildClass extends BaseClass { //ChildClass aka a SUBCLASS 
                                              //Inherites all from BaseClass
                                              //Inherites methods & variables defined in BaseClass
    public void printSomething() { //presidence over same method from BaseClass
        
        System.out.println("This was printed from ChildClass");
    }
    
    public static void main(String [] args) {
    
        ChildClass testSuper = new ChildClass();
        
        testSuper.printSomething();
        
      }
      
   }   
   
   //CLASS: BaseClass
   
   public class BaseClass {
   
     public void printSomething() {
        
        System.out.println("This was printed from BaseClass");//named the same so doesnt get printed
    }
   
   
   }
    
