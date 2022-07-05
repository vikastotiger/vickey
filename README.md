import java.util.*;
import javafx.scene.control.TextInputControl;

public class main
{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int i=0;
        int Phonebook,Contact;
        Phonebook objmain=new Phonebook();
        while(i==0)
        {
            System.out.println("Menu\n1.Add contact\n2.Dispaly all contacts\n3.search contact by phone\n4.Remove contact\n5.Exit");
            System.out.println("enter your choice: ");
            int n=Integer.ParsenInt(sc.nextLine());
            if(n==1)
            {
                Contact obj=new TextInputControl.Content();
                System.out.println("Add  a  contact  : ");
                System.out.println("enter the first name:  ");
                obj.setFirstName(sc.nextLine());
                System.out.println("enter the last name: ");
                obj.setlastName(sc.nextLine());
                System.out.println("enter the phone number.: ");
                obj.setphonenumber( Long.parseLong(sc.nextLine()));
                System.out.println(" Enter the email ; ");
                obj.setemailId(sc.nextLine());
            }
            if(n==2)
            {
                  System.out.println("the contact in the list are :");
                  List<Contact>obj=objmain.viewAllcontacts();
                  for(Contact temp:obj)
                  {
                        System.out.println("first name :"+temp.getFpirstName());
                        System.out.println("last name :"+temp.getLastName());
                        System.out.println("phone number ;"+temp.getPhoneNumber());
                        System.out.println("EmailId :"+temp.getEmailId());
                        
                  }
            }
            if(n==3)
            {
                System.out.println("Enter the Phone number to search contact:");
                    Long n1=Long.parseLong(sc.nextLine());
                    Contact obj1=objmain.viewContactGivenPhone(n1);
                    System.out.println("The contact is:");
                    System.out.println("First Name:"+obj1.getFirstName());
                    System.out.println("Last Name:"+obj1.getLastName());
                    System.out.println("Phone No.:"+obj1.getPhoneNumber());
                    System.out.println("Email:"+obj1.getEmailId());
            }
            if(n==4)
            {
                    System.out.println("Enter the Phone number to remove:");
                    Long n1=Long.parseLong(sc.nextLine());
                    System.out.println("Do you want to remove the contact(Y/N):");
                    char ch=sc.nextLine().charAt(0);
                    if(ch=='Y')
                    {
                        boolean f1=objmain.removeContact(n1);
                        if(f1)
                        System.out.println("The contact is successfully deleted");
                        else
                        System.out.println("Contact is not found");
                    }
                    if(ch=='N')
                    {
                        System.out.println("ok");
                    }
                    
                }
            if(n==5)
            {
                    System.exit(0);
            }
        }
    }
}
            
            
                
            
                
                
            
        
