# member-inner-class-local-inner-class-in-java



//progrm to demonstrate member inner class and local inner class
import java.io.*;
import java.util.*;
class Bank    //outer class
{
    long cash=500000000;
    int bal=45000;
    Console c=System.console();
    Scanner sc=new Scanner(System.in);
    Bank()   
    {
     System.out.print("Welcome to Bank");
    }
    void balanceInfo()
    {
        System.out.println("present balance="+bal);
    }
                                        //method containing local inner class
    void transfer() 
    {

        System.out.println("transfer successfully");
                                                //local innerclass

      
    }
    void login()
    {
        String uname=c.readLine("enter username=");
        char name[]=c.readPassword("enter password=");
        String pass=new String(name);
        if(uname.equals("cust")&&pass.equals("cust"))
        {
            Bank b=new Bank();
            b.balanceInfo();
            b.transfer();
                                             //local inner class
                   class InnerLocker
       {
                                              //local inner class method
            void locker()                         
         {
            System.out.println("do u want to check the locker");
            String id=c.readLine("enter locker id=");
            char lpass[]=c.readPassword("enter password=");
            String login=new String(lpass);
            if(id.equals("Anmol")&&login.equals("Anmol123"))
            {
                System.out.println("WELCOME TO YOUR SAFETY LOCKER");
                System.out.println("your locker contains:");
                System.out.println("home property doc.");
                System.out.println("gold");
                System.out.println("total cash="+cash);
            }
            else
            {
                System.out.println("Invalid id");
                System.out.println("Enter valid id");
       
            }                               //local inner class method end
         }                                  //local inner class end
        }                                   // transfer method end


                            //object creation for local inner class
        InnerLocker il=new InnerLocker();
            il.locker();
        }
        else if(uname.equals("emp")&&pass.equals("admin"))
        {
            Bank b=new Bank();
            b.balanceInfo();
            BankEmp bm=new BankEmp();
            bm.deposit();
            bm.withdraw();
        }
        else
        {
            System.out.println("invalid login");
        }
       
        
    }


                  //Member inner class of Bank class
    class BankEmp
    {
        int amount;
        void deposit()
        {
            System.out.println("enter amount u wanted to withdraw");
            amount=sc.nextInt();
            bal=bal+amount;
            balanceInfo();
        }
        void withdraw()
        {
            System.out.println("enter amount to withdraw");
            amount=sc.nextInt();
             bal=bal-amount;
             balanceInfo();
        }
    }//Member inner class end
}//outer class end(Bank)

                                          //Main class
class NetBankAcc1
{
    public static void main(String[] args)
    {
        Bank c1=new Bank();
        c1.login();
      //  Transfer c2=new Transfer();
        //c2.transfer();
        //c1.withdraw();
        //c1.deposit();
        //BankEmp b1=new BankEmp();
        Bank bm=new Bank();
        bm.login();
       //InnerLocker il=new InnerLocker();
         //   il.locker();
    }
}
