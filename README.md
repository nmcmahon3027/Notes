# Notes
//interface EJ Media Youtube)

(14)**Interfaces**

    Planet Earth = new Planet();

    Earth.size = 25000;

    Planet Jupiter = new Planet();
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
 
 //CLASS: Food.java
 //CLASS: HamburgerJoint.java (main)
 
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
    
        super.printSomething();//Now it prints from BaseClass
                                //uses printSomthing() method from super class (BaseClass)
                                //this OVERWRITES this method and used method from super
        //System.out.println("This was printed from ChildClass");
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
    
   //**(Pt 9)**
   //**The for loop
   
     class forloop { 
    public static void main(String[] args){
    
     //3 main parts
     //for(initizialation section/parameter, conditional section *how far(when to end for loop),
    //changed section (what to do EACH time the loop runs)
    
      for(int start = 0; start <= 10; start++)      //or +=2 (adding 2)
     { 
        System.out.print(start);
 
 
      }
      //OUTPUT: 012345678910
      
      
    //**(Pt10)
    //**While loop
    
    //while loops check a CONDITION and continues if it is true

    class whileloop {
    public static void main(String[] args) {

    int topNumber = 15;
    int bottomNumber = 1;

    while(bottomNumber < topNumber) {

    System.out.print("this is a loop");
    bottomNumber++; //Must increment to avoid never ending loop
    }

        //OUTPUT: this is a loop (14 times)
        //if false, not output
        
        
 //**(Pt 11) 
 //**the do-while loop
 //do comes first ==>STATEMENT then CONDITIONS 
 //should get at least ONE line of output
 
 
    class dowhile {
    public static void main(String[] args) {
    
        int topNumber = 15;
        int bottomNumber = 1;
        
      do 
        {
        System.out.print("this is a loop");
        bottomNumber++;
        
      }
      while(bottomNumber < topNumber);
      
   //**(Pt 12)
   //**Arrays**
   
    class Arrays {
    public static void main(String[] args) {
    
    int[] numbers;          //defined/created array
    numbers = new int[5];       //how many ELEMENTS (or variables I suppose) will be stored in the array
    
    numbers [0] = 35;              // numbers[index] = 35;
    numbers [1] = 65;
    numbers [2] = 135;
    numbers [3] = 335;
    numbers [4] = 535;
    
    System.out.print(numbers[1]); //numbers @ index 1
        }
     }   
     //OUTPUT:65
     
     
     class Arrays {
    public static void main(String[] args) {
    
    String[] candy;          
    candy = new String[2];       
    
    candy [0] = "mint";              
    candy [1] = "rock";
    
     System.out.print(candy[0]);
     
     }
     }  
     
     //OUTPUT: mint
     
     
      class Arrays {
    public static void main(String[] args) {  //QUICKER WAY to initialize
    
    int[] numbers = {5, 9, 45}; //value 5 @ index 0, value 9 @ index 1, etc
    
    System.out.print(numbers[2]);
    }
     } 
    //OUTPUT: 45
   
//**(pt.28)**Look at this to understand
//OOP and the life cycle of the object

//ex: 
// 3 classes: ChildClass, MiddleClass, SuperClass

    ChildClass extends MiddleClass
    MiddleClass extends SuperClass

ChildClass-->MiddleClass-->SuperClass-->MiddleClass--ChildClass-->main


//**(Pt 30)
//** Primitive and Object Reference variables

    public class Road {

    int x = 20; //primitive variable
            //1.Declare 2.give name 3.assign a value

    int y = x;
    double decimal = 5.5;

    public static void main(String[] args) {

    Road mile15 = new Road(); //Object Reference variable
                            //Represents a way to get to that object
                            //Like a street sign
                            //the sign is not the street itself
                            //Here it is constructed
                            //mile15 (the name) its POINTING to the actual object in memory
                       
    Road Maple = mile15;//Use Road class and create new reference 
                    //ALSO POINTING to same object  
                    //INSTANCE OF ROAD OBJECT 
                    
    Road Smith = new Road(); //Builds a NEW INSTANCE of Road (another Road Object)                   

    }

//(Pt.31)
//**Getters & Setters**
//Always 2 methods: A GET & a SET
//Point is to encapsulate variables

    public class Orc {

    private int height;
    
    public void setHeight (int height) {

    if(height < 10) {
    this.height = height;
    System,out.println("Orc met Criteria");
    }else{
    System.out.println("Please enter a height under 10 feet");
    }    

    }

    public int getHeight() {

    return height;
     }
 
     }
 
 //**(Pt. 38)**
 //**Polymorphism**
 
 
 -Normal way we have created Objects:
 
 Beat beatleObj = new Beatle();
 ^          ^           ^
 Reference              Object we created
 Type
 
 -Create Objects FROM SUPER CLASS
 
 Insect beatleObj = new Beatle();
 ^
 reference type (Super Class Insect)
 
 //Polymorphosm is FLAVORS or VERSIONS of that type
 
 Super Class:Insect-->Sub Class: Beatle
  v         v
Obj Beatle Obj Beatle

Polymorphism Arrays:
5 classes:
App.java    Beatle.java     Roach.java  Spider.java     Insect.java

    public class App {

    public static void main(String[] args) {

    Insect allInsects[] = new Insect[4];//# of OBJECTS(0,1,2,3)  //specifying SUPER CLASS
                                    //Declaring Array type of Insect (super class type)
    allInsects[0] = new Roach();
    allInsects[1] = new Beatle();       //can put any subclass of insect inside array
    allInsects[2] = new Spider();
    allInsects[3] = new Spider();

    for (int i = 0; i < allInsects.length; i++); //loop through the array

    allInsects [i].eat(); //can call any of the SUPER CLASS MEHTODS

    }

    }
    }

(Inheritence) Classes (Other Insects)

CLASS: Beatle.java

    public class Beatle extends Insect {

    }

CLASS: Roach.java 

    public class Roach extends Insect {

//if I were to do this below it would OVERWRIDEs Super class method

    void eat() { //MUST have the same name (eat) to take presidence
    System.out.println("A Roach has Eaten");  //OUTPUT: A Roach has Eaten
                                          //        Eat (x3)

    }
    }

CLASS: Spider.java

    public class Spider extends Insect {

    }

(Super)CLASS: Insect

    public class Insect {

    void eat() {
    System.out.println("Eat");

    }
    }
    
**(Pt.32 More Metrhods)

    public class Methods {
    
    void numberTrees(int trees) { //RECIEVING METHOD//Fancy Name: Parameter 2. Local varianle
                                  //A PLACEHOLDER for value passed in 
                                  //**"void" DOES NOT RETURN a valur to the calling method ** 
                                  //@ return;   doesnt go back bc void
    
        trees = trees +1;
        int trees2 = 4;     //Declared and given value HERE, thats why its not in the ( )
        System.out.println(trees + trees2);
        
      }  
      
      int returnNumber(int x) { //Has to RETURN (an int) bc not void  
     //int             int  ==>    must match
           x = x + 1;
           returnx;
       }
       
       public static void main(String [] args) {
       
       Methods testTree = new Methods();
       
       testTree.numberTrees(7); //the CALLING METHOD//Argument 2. Passing a value
                                //Always SEND ARGUMENTS TO RECIEVING METHOD: numberTrees (up top)
       System.out.println(testTree.returnNumber(55));
       
       }

//OUTPUT: 12

//**(Pt.39)**
//**Abstract classes and methods**

    public abstract class Mammal { //If making an Abstract Method, Class needs to be Abstract too!
    
    public abstract void hair(); //Abstract methods are BLANK, fill out later
    public abstract void breathe();
                                    //CANNOT create objects off of abstract methods
                                    //Must extend super class from subclasses if you want to
                                    //MUST: if you put abstract methods in super class, MUST USE THEM IN SUBCLASS!!
    }

 //**(Pt.56)
 //**Error handling and catching exceptions
 
    class ErrorHandling {
    
    publuc static void main(String[] args) {
    
       try { //Risky code gets wrapped in try block
        int[] testArray;
        
        testArray = new int[3];//set size to 3 elements
        
        testArray[0] = 1;
        testArray[1] = 2;
        testArray[2] = 3;
        
                                             //(1st ex.) System.out.println(testArray[2]); //OUTPUT: 3
        System.out.println(testArray[99]);                                
        
        //Try-catch
        //Try block is the guarded or 'risky' code
        //Catch block 'traps' the exception and allows you to do something
        //if you have a TRY BLOCK, MUST have a CATCH BLOCK
        
        } catch(IndexOutOfBoundsException er); { //takes 2 arguments
                                                // IndexOutOfBoundsException is a java class, obj./var of class
        
            System.out.println("An out of Bounds exception occured");
            //OUTPUT: An out of Bounds exception occured
    }
    }
    }
    //If dont know what kind of Exception to use, use the generic Exception:
    // }catch (Exception er) {
    
//**ArrayLists (pp: CHAPTER 2 in text)

 //To declare a List“object” whose elements will reference Stringobjects:
     List<String> myList = new ArrayList<String>();
  
  //The initial List is empty and has a default initial capacity of 10 elements
  //To add string to the list:
  
        myList.add("Bashful");
        myList.add("Awful");
        myList.add("Jumpy");
        myList.add("Happy");
        
   
        
   //myList = [0]       [1]     [2]     [3]     
          "Bashful"   "Awful"  "Jumpy"  "Happy"
          
   //Adding an element with subscript  2:
   
        myList.add(2, "Doc");
        
   //The subscripts  of "Jumpy" and "Happy" have changed  from [2],[3] to [3],[4]     
    
     //myList = [0]       [1]     [2]    [3]    [4]   
          "Bashful"   "Awful"  "Doc"  "Jumpy"   "Happy"
          
 //When no subscript is  specified, an element is added at the end of the list:
 
        myList.add("Dopey");                                //[5]"Dopey"
        
  //Removing an Element:
  
   
    //myList = [0]       [1]     [2]    [3]    [4]        [5]
          "Bashful"   "Awful"  "Doc"  "Jumpy"   "Happy"    "Dopey"
          
           myList.remove(1);
           
      //myList = [0]       [1]     [2]      [3]       [4]        
          "Bashful"   "Doc"     "Jumpy"    "Happy"   "Doepy"           
           
           
 //Replacing
    
            mylist.set(2, "Sneezy"); //Replaces Jumpy w/ Sneezy
    
  //MUST use the get() method to access an element 
  
        String dwarf = myList.get(2); //value of dwarf becomes "Sneezy"
        
  //Search an ArrayList:
  
        myList.indexOf("Sneezy"); //retruns: 2
        
        return of -1 indicates UNSUCCESSFUL SEARCH
        
 //Generic Collections
 
// The general declaration for generic collection is
 
        CollectionClassName<E> variable= new CollectionClassName<E>();
        
        //The <E> indicates a type parameter
        //primitive types will be autoboxed
        
 //Example Application of ArrayList
 
        ArrayList<Integer> someInts = new ArrayList<Integer>();
        int[] nums = {5, 7, 2, 15};
        for (int i = 0; i < nums.length; i++) {
        someInts.add(nums[i]);  //nums[i]is an int; it is automatically wrapped in an Integer object
        }
        // Display the sum
        int sum = 0;
        for (int i = 0; i < someInts.size(); i++) {
   
        sum += someInts.get(i);
        }
        System.out.println("sum is " + sum);
        
   //Create class for objects stored in directory
   
        public class DirectoryEntry {
            
            String name;
            String number;
           
        }
        
        private ArrayList<DirectoryEntry> theDirectory = new ArrayList<DirectoryEntry>(); //Create Directory
        theDirectory.add(new DirectoryEntry("Jane Smith", "555-5467"));
        intindex = theDirectory.indexOf(new DirectoryEntry(aName,""));
        //Method indexOfsearches theDirectoryby applying the equalsmethod for class DirectoryEntry.                                 //Assume DirectoryEntry's equalsmethod compares namefields.
        
  //Reallocate Method
  
        private void reallocate () {
        capacity *= 2; 
        theData = Arrays.copyOf(theData, capacity);
        }
        
  //KWArrayList as a COLLECTION OF OBJECTS
  
        private Object[] theData;  
        
        //REMOVE parameter type <E> from the class heading
        //replace each reference to data type E by Object
