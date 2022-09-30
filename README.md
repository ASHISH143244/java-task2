# java-task2
task2:
ATM_Interface
Code:


import java.util.Scanner;
public class ATM_Interface {
    public static void main(String [] args)
    {
        int pinNo = 1308;
        boolean bool = true;
        int option;
        int balanceRem = 500000;
        int withdrawAmt = 0;
        int depositAmt = 0;
        int transferAmt = 0;
        int temp;
        System.out.println("WELCOME TO OIB ATM SYSTEM\n \n");
        Scanner sc = new Scanner(System.in);
        System.out.println(" Insert the ATM Card");
        System.out.println(" Enter Correct Credentials");
        System.out.println(" Enter 4 digit pincode");
        
        int code = sc.nextInt();
        if(pinNo == code)
        {
            while(bool)
            {
                System.out.println("Select a option");
                System.out.println("1. Transaction Data\n 2. Withdraw\n 3. Deposit\n 4. Transfer\n 5. EXIT");
                option = sc.nextInt();
                switch(option)
                {
                    case 1:
                        System.out.println("History");
                        System.out.println(" Available Balance: " + balanceRem);
                        break;
                        
                    case 2:
                        System.out.println(" Enter the withdrawal Amount:");
                        temp= sc.nextInt();
                        if(temp>balanceRem)
                        {
                            System.out.println(" Oops! Low Balance You cannot withdraw the Amount");
                        }
                        else{
                            withdrawAmt += temp;
                            balanceRem -= temp;
                            System.out.println("------------ Collect Your Cash-------------");
                            System.out.println(balanceRem + " is remaining balance in your account ");
                            
                        }
                        break;
                        
                        case 3:
                        System.out.print(" Enter Deposit Amount");
                        temp= sc.nextInt();
                        System.out.println( " Place Your Cash Carefully in the Deposit Slot");
                        depositAmt += temp;
                        balanceRem += temp;
                        System.out.println(" Current Balance: " + balanceRem);
                        break;
                        
                        case 4:
                            while(true)
                            {
                               System.out.println(" Enter the account number of the Beneficiary");
                               int accNo = sc.nextInt();
                               System.out.println(" Enter the IFSC code of the bank of the beneficiary");
                               String ifsccode = sc.next();
                               System.out.println(accNo);
                               System.out.println(" Please confirm the account no of the beneficiary");
                               System.out.println(" 1. Yes\n 2. No");
                               int select = sc.nextInt();
                               if(select == 1)
                               {
                                   System.out.println(" Fund Transfer: ");
                                   temp = sc.nextInt();
                                   transferAmt += temp;
                                   balanceRem -= temp;
                                   System.out.println(" Fund Transfertred Successfully");
                                   break;
                               }
                               else {
                                   System.out.println(" Invalid Account Number");
                               }
                            }
                            break;
                            
                        case 5:
                            System.out.println("Thank You For Banking With Us");
                            bool=false;
                            break;
                            
                }
            }
        }
        else
        {
            System.out.println("Oops! You have Entered the Wrong Pin");
        }
}
}
