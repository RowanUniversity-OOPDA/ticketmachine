ticketmachine
=============
import java.util.Scanner;

public class TicketMachine
{
    
    private double price; 
    private double balance;
    private double totalSold;
    private String type;
    private int amtFrees = 0; //amount of free tickets the customer has currently.
    

    
    public TicketMachine(String kind, )// (subway vs locomotive)
    {
        kind= type;
        price = cost;
        balance = 0;
        totalSold = 0;
        
    }
    
    public double getPrice() {
        return price;
    }
    
    public double getBalance() {
        return balance;
    }
    
    public void insertMoney() {
        System.out.println("Your balance is" + balance + ". To pay, please begin to insert money.");
        Scanner paid = new Scanner(System.in);
        double inserted = paid.nextDouble();
        balance = balance - inserted;
    }

    public void printTicket () { //will add to this
        System.out.println("################");
        System.out.println("Ticket");
        System.out.println("Price:" + "$"+ price);
        
        
        balance = 0;
    }
    
    
    
    public String askTo() {
        System.out.println("Please enter your desired destination:");
        Scanner dest = new Scanner (System.in);
        String destination = dest.nextLine();
        return destination;
    }
    
    public String askFrom() {
        System.out.println("Please enter where you are traveling from:");
        Scanner where = new Scanner (System.in);
        String from = where.nextLine();
        return from;
    }
    
    
    
    public void schedule() {
        Schedule sch = new Schedule(machine.askFrom(), machine.askTo());
    }
    
    public void askUseFree() { 
        System.out.println("You have " + amtFrees + " tickets available. Would you like to use one of them for this ticket? (y/n)")
        Scanner free = new Scanner (System.in);
        String free1 = free.nextLine();
        if (free1 == "y") {
            price = 0.00;
            amtFrees--;
        }
        
        
    }
        
        
        
    public void subwayPrices() {
       
        String membership = acc.returnMembership(); //allens method that returns the type of membership
            
            if (membership == "platinum") {
                price = 0.00; 
            }
            else if (membership == "gold") {
                if (amtFrees>0) {
                    machine.askUseFree();//would you like to use free, sets to 0 if so, and subtracts from amount
                    
                }
                else {
                    price = price - (price * .5);
                }
            }
            else if (membership == "silver" ) {
                if (amtFrees > 0) {
                    machine.askUseFree();
                }
                else{
                    price = price - (price * .25);
                }
            }
            balance =+ price;
            
        }
     
  public quantity() { 
      
    System.out.println("How many tickets would you like to buy?")
        Scanner quantitiy = new Scanner(System.in);
        int quant = quantity.nextInt();
        
        
        if (quant > 0) {
            for(int i = 1; i < quant; i++) {
                machine.subwayPrices();
              
            
        }
        else {
            balance = price;
        }
    }
                
      public void start() {
          System.out.println("What kind of ticket would you like to buy, subway or locomotive?");
        }
            
            
            
           
                        
        
            
    public void UseMachine() {// Main method, will make another for the locomotive.
        TicketMachine machine = new TicketMachine();
        
        
        System.out.println("What kind of ticket would you like to buy, subway or locomotive?");
        Scanner x = new Scanner(System.in);
        String y = x.nextLine();
        if (y == "subway") {
            price = 5.00;
        }
        
        System.out.println("Welcome to the Ticket Machine. Would you like to login first? (y/n), or register as a new guest (r)?");
        Scanner login = new Scanner(System.in);  
        String input = login.nextLine();
        if (input == "y") {
     
            //method to direct to allens login
           amtFree = machine.findAmountFree(); //allens method that returns how many free tickets customer has left
            
           //ask to and from which will feed to schedule class
           machine.schedule();
           
           if (y == "subway" ) {
               machine.subwayPrices()://sets price of ticket(s)
          
            }
            if (y == "loco") {
                //something from schedule class that sets price for this specific train ride and then discounts accordingly
            }
        }
        if( input == "n") {
            machine.schedule();
            price =price;
        }
        
        if(input == "r") {
            machine.register(); //allens method to register
            amtFree = machine.findAmountFree(); //allens method that returns how many free tickets customer has left
            //ask to and from which will feed to schedule class
           machine.schedule();
           if (y == "subway" ) {
               machine.subwayPrices()://sets price of ticket(s)
          
            }
            if (y == "loco") {
                //something from schedule class that sets price for this specific train ride and then discounts accordingly
            }
            
            
        }
        
        machine.quantity();
        
        
        while (balance > 0 ) {
            machine.insertMoney();
        }
        if (balance < 0) {
            double change = -(0-balance);
            System.out.println("Your change is" + balance);
        }
        machine.printTicket();
        totalSold++; //quant field
        //return to account how many current member bought
    }
    
    
}
                    
            

    
    

