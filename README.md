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
    
    int day = 1; visible to the package
    
    
    
    
    
    
    
    
    
    
