//1)Enhanced Console-based Calculator:

import java.util.*;

public class calculator {
    static Scanner sc=new Scanner(System.in);
      void basicoperation(){
        System.out.println("1.addition");
        System.out.println("2.subtraction");
        System.out.println("3.multiplication");
        System.out.println("4.division");
        System.out.println("select the basic operation :");
        int n=sc.nextInt();
        switch(n){
            case 1:
               System.out.println("enter 1st number :");
               int a=sc.nextInt();
               System.out.println("enter 2nd number :");
               int b=sc.nextInt();
               System.out.println(a+b);
               break;
            case 2:
               System.out.println("enter 1st number :");
               int c=sc.nextInt();
               System.out.println("enter 2nd number :");
               int d=sc.nextInt();
               System.out.println(c-d);
               break;
            case 3:
               System.out.println("enter 1st number :");
               int e=sc.nextInt();
               System.out.println("enter 2nd number :");
               int f=sc.nextInt();
               System.out.println(e*f);
               break;
            case 4:
            try{
                System.out.println("enter 1st number :");
                double g=sc.nextDouble();
                System.out.println("enter 2nd number :");
                double h=sc.nextDouble();
                System.out.println(g/h);
                break;
            }
                catch(ArithmeticException t){
                    System.out.println(t.getMessage());

                }
                default:
    System.out.println("Invalid selection.");

        }
      }
      void scientificoperations(){
        System.out.println("1.square root");
        System.out.println("2.exponentiation to e");
        System.out.println("3.power");
        System.out.println("select the scientific operation :");
        int n1=sc.nextInt();
        switch (n1){
            case 1:
             System.out.println("enter number :");
             double r=sc.nextDouble();
             System.out.println(Math.sqrt(r));
             break;
             case 2:
             System.out.println("enter number :");
             double l=sc.nextDouble();
             System.out.println(Math.exp(l));
             break;
             case 3:
             System.out.println("enter base :");
             double b=sc.nextDouble();
             System.out.println("enter exponent :");
             double p=sc.nextDouble();
             System.out.println(Math.pow(b,p));
             break;
             default:
    System.out.println("Invalid selection.");

        }
      }
      void unitconversions(){
        System.out.println("1.farenhit to celsius ");
        System.out.println("2.celsius to farenhit");
        System.out.println("3.celsius to kelvin");
        System.out.println("4.kelvin to celsius");
        System.out.println("5.rupees to dollars");
        System.out.println("6.dollars to rupees");
        System.out.println("select operation in unit conversions :");
        int u=sc.nextInt();
        switch(u){
            case 1:
            System.out.println("enter temperatue :");
            double t =sc.nextDouble();
            System.out.println((5.0/9.0)*(t-32));
            break;
            case 2:
            System.out.println("enter temperatue :");
            double tf =sc.nextDouble();
            System.out.println(((9.0/5.0)*(tf))+32);
            break;
            case 3:
            System.out.println("enter temperature in celsius :");
            double c=sc.nextDouble();
            System.out.println(c+273);
            break;
            case 4:
            System.out.println("enter temperature in kelvin :");
            double c1=sc.nextDouble();
            System.out.println(c1-273);
            break;
            case 5:
            System.out.println("enter rupees :" );
            double r=sc.nextDouble();
            System.out.println(r/85.33);
            break;
         case 6:
            System.out.println("enter dollars");
            double d=sc.nextDouble();
            System.out.println(d*85.33);
            break;
            default:
    System.out.println("Invalid selection.");

        }

      }
      public static void main(String[] args){
        calculator c= new calculator();
        boolean b=true;
        while(b){
            System.out.println("1.basic operations");
        System.out.println("2.scientific caluculations");
        System.out.println("3.unit conversions");
        System.out.println("4.exit");
        System.out.println("select operation  ");
        int n=sc.nextInt();
        switch(n){
            case 1:
              c.basicoperation();
              break;
            case 2:
              c.scientificoperations();
              break;
            case 3:
              c.unitconversions();
              break;
              case 4:
              b=false;
              break;
              default:
    System.out.println("Invalid selection.");

    
      }
    }
}
    } 

    
//2)Simple Contact Management System:
 
 import java.util.*;
 class Contact{
    String name;
    String email;
    String number;
   Contact(String n,String nu,String e){
     name=n;
     number=nu;
     email=e;
    }
}
public class ContactManagement{
  static Scanner sc=new Scanner(System.in);
     ArrayList<Contact> al=new ArrayList<>();

     void addContact(){
         System.out.println("enter name :");
         String n=sc.nextLine();
         System.out.println("enter number :");
         String nu=sc.nextLine();
         System.out.println("enter email :");
         String e=sc.nextLine();
         al.add(new Contact(n,nu,e));
     }
     void display(){
      if(al.isEmpty()){
        System.out.println("there are no contacts");
        return ;
      }
      for(Contact c: al){
        System.out.println("name :"+c.name);
        System.out.println("num :"+c.number);
        System.out.println("email :"+c.email);
        System.out.println("");
      }
     }
     void update(){
       System.out.println("enter contact name to update :");
       String n=sc.nextLine();
       boolean found=false;
       for(Contact c: al){
        if(c.name.equalsIgnoreCase(n)){
          found =true;
          System.out.println("enter field to be updated :");
          String nam=sc.nextLine();
          switch(nam){
            case "name":
              System.out.println("enter new name :");
              c.name=sc.nextLine();
              break;
            case "number":
              System.out.println("enter new phone number :");
              c.number=sc.nextLine();
              break;
            case "email":
               System.out.println("enter new email id");
               c.email=sc.nextLine();
               break;
              default:
                System.out.println("field not found");
                break;
          }
        }
       }
       if(!found){
      System.out.println("contact not found");}
     }

     void delete(){
        System.out.println("enter number to deleted");
        String no=sc.nextLine();
        Iterator<Contact> i=al.iterator();
        while(i.hasNext()){
          Contact c1=i.next();
          if(c1.number.equals(no)){
            i.remove();
            System.out.println("contact deleted");
            return;
          }
        }
         System.out.println("contact not found");

     }
     public static void main(String[] args) {
      ContactManagement cm=new ContactManagement();
        System.out.println("1.add contact");
        System.out.println("2.update contact");
        System.out.println("3.delete contact");
        System.out.println("4.exit");
        System.out.println("select operation :");
        int m=sc.nextInt();
        sc.nextLine();
        switch (m) {
          case 1:
            cm.addContact();
            break;
         case 2:
           cm.update();
           break;
          case 3:
            cm.delete();
            break;
          case 4:
            System.out.println("exiting");
            break;
          default:
          System.out.println("invalid choice");
            break;
        }
}
}


// Intermediate:
 //1)Bank Account Management System with Unit Testing (JUnit):


import java.util.*;
  public class AccountManagement{
        String Name;
        float balance;
        String accid;
        List<String> transactionhist;
      static ArrayList<AccountManagement> b=new ArrayList<>();
        AccountManagement(String n,float bal,String id){
           Name=n;
            balance=bal;
            accid=id;
            transactionhist=new ArrayList<>();
            transactionhist.add("acc created with balance :"+bal);
        }    
        public void addacc(AccountManagement account){
          b.add(account);
        }
             public  void deposit(String a,float am){
                 for(AccountManagement bm: b){
                  if(bm.accid.equals(a)){
                      bm. balance+=am;
                       System.out.println("amount deposited");
                       bm.transactionhist.add("amount credited :"+am);
                       return;
                  }
                 }
                 System.out.println("account not found");
         }

         public void withdraw(String a,float am){
          for(AccountManagement bm: b){
                  if(bm.accid.equals(a)){

                    if(bm.balance<am){
                      System.out.println("insufficient amount");
                      return;
                    }
                      bm.balance-=am;
                       System.out.println("amount withdrawn");
                       bm.transactionhist.add("amount debited :"+am);
                       return;
                  }
                 }
                 System.out.println("account not found");
         }
         public void balinquiry(String a){
          for(AccountManagement bm: b){
                  if(bm.accid.equals(a)){
                       System.out.println("amount available :"+bm.balance);
                       return;
                  }
                 }
                 System.out.println("account not found");
         }
         public List<String> transactionhistory(String a){
             for(AccountManagement bm:b){
                  if(bm.accid.equals(a)){
                    return bm.transactionhist;
                  }
             }
             System.out.println("account not found");
             return new ArrayList<>();
         }
  }
  import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;
import java.util.List;

public class BankManagementTest {
   AccountManagement a1,a2;

    @Before
    public void setup() {
        a1=new AccountManagement("Varshini",1000f,"A001");
        a2=new AccountManagement("Nani",0f,"A002");
        a1.addacc(a1);
        a2.addacc(a2);
    }

    @Test
    public void depositValidAmountTest() {
        a1.deposit("A001",500f);
        assertEquals(1500f,a1.balance,0.01f);
    }

    @Test
    public void withdrawInsufficientBalanceTest() {
        a2.withdraw("A002",100f);
        assertEquals(0f,a2.balance,0.01f);
    }

    @Test
    public void withdrawInvalidAccountTest() {
        a1.withdraw("UNKNOWN",100f);
        assertEquals(1000f,a1.balance,0.01f);
    }

    @Test
    public void transactionHistoryTest() {
        a1.deposit("A001",200f);
        a1.withdraw("A001",100f);
        List<String> history=a1.transactionhistory("A001");
        assertTrue(history.contains("amount credited :200.0"));
        assertTrue(history.contains("amount debited :100.0"));
    }

    @Test
    public void addAccountTest() {
        AccountManagement newAcc=new AccountManagement("TestUser",300f,"A003");
        a1.addacc(newAcc);
        boolean exists=false;
        for(AccountManagement acc:AccountManagement.b) {
            if(acc.accid.equals("A003")) {
                exists=true;
                break;
            }
        }
        assertTrue(exists);
    }

    @Test
    public void transactionHistoryEmptyTest() {
        List<String> history=a2.transactionhistory("A002");
        assertEquals(1,history.size());
        assertTrue(history.get(0).startsWith("acc created"));
    }
}


//2)Inventory Management System with Basic GUI:


 import javax.swing.*;
 import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;


 class inventory implements ActionListener{
  JButton a;
  JButton d;
  JButton u;
  Execution ex;
     inventory(){
      ex=new Execution();
      JLabel l=new JLabel();
      l.setText("select operation");
      l.setBounds(150, 100,400, 50);
      l.setFont(new Font(null,Font.PLAIN,40));
       a=new JButton();
      a.setFocusable(false);
      a.setText("add item");
      a.setBounds(200, 250, 100, 100);
      a.addActionListener(this);

       d=new JButton();
      d.setFocusable(false);
      d.setText("delete item");
      d.setBounds(350, 250, 100, 100);
      d.addActionListener(this);

       u=new JButton();
      u.setFocusable(false);
      u.setText("update item");
      u.setBounds(500, 250, 125, 100);
      u.addActionListener(this);
       
         JFrame f=new JFrame();
          String[] col={"id","name","quantity"};
         String[][] data={};
         JTable t=new JTable(data,col);
         JScrollPane s=new JScrollPane(t); 
         f.add(l);
         f.add(a);
         f.add(u);
         f.add(d);
          //f.add(s);
       f.setLayout(null);
         f.setTitle("Inventory management system");
         f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
         f.setSize(750,750);
         f.setVisible(true);
        
     }
     public void actionPerformed(ActionEvent e){
    
      if(e.getSource()==a){
          ex.additem();
      }else if(e.getSource()==d){
        ex.deleteitem();
      }else if(e.getSource()==u){
        ex.updateitem();
      }
     }
     public static void main(String[] args) {
       new inventory();
     }
 } 

 import javax.swing.*;
import javax.swing.table.DefaultTableModel;

import java.awt.*;
import java.awt.event.*;

public class Execution extends JFrame {

JFrame f=new JFrame();
JTable t;
DefaultTableModel m;
String[] col={"id","name","quantity"};
   Execution(){
    
         m=new DefaultTableModel(col,0);
         t=new JTable(m);
         JScrollPane s=new JScrollPane(t);
          f.setLayout(null);
         f.setTitle("Inventory management system");
         f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
         f.setSize(750,750);
         f.add(s);
         f.setVisible(true);
   }
   void additem(){
      JTextField i=new JTextField();
      JTextField n=new JTextField();
      JTextField q=new JTextField();

      Object[] obj={"id :",i,
            "name :",n,
              "Quantity :",q};

      int res=JOptionPane.showConfirmDialog(null, obj,"enter the item details",JOptionPane.OK_CANCEL_OPTION);
      if(res==JOptionPane.OK_OPTION){
        String id=i.getText();
         String name=n.getText();
         String quan=q.getText();

         m.addRow(new Object[]{id,name,quan});
      }
   }
   void deleteitem(){
 String id=JOptionPane.showInputDialog("enter id to delete");
    if(id!=null){
        boolean found=false;
          for(int j=0;j<m.getRowCount();j++){
            String idi=m.getValueAt(j, 0).toString();
            if(id.equals(idi)){
              m.removeRow(j);
              found=true;
              JOptionPane.showMessageDialog(null,"item deleted");
              break;
            }
            
          }
          if(!found){
            JOptionPane.showMessageDialog(null,"item not found");
          }
          return;
    }
    JOptionPane.showMessageDialog(null,"invalid id");


   }
   void updateitem(){
    String id=JOptionPane.showInputDialog("enter id to update");
    if(id!=null){
        boolean found=false;
          for(int j=0;j<m.getRowCount();j++){
            String idi=m.getValueAt(j, 0).toString();
            if(id.equals(idi)){
             String f= JOptionPane.showInputDialog(null,"enter field to update");
              if(f.equals(col[0])){
               m.setValueAt( JOptionPane.showInputDialog(null,"enter updated id:"),j,0);
}else if(f.equals(col[1])){
               m.setValueAt( JOptionPane.showInputDialog(null,"enter updated name:"),j,1);
}else if(f.equals(col[2])){
               m.setValueAt( JOptionPane.showInputDialog(null,"enter updated quantity:"),j,2);
}
              found=true;
              JOptionPane.showMessageDialog(null,"item updated");
              break;
            }
            
          }
          if(!found){
            JOptionPane.showMessageDialog(null,"item not found");
          }
          return;
    }
    JOptionPane.showMessageDialog(null,"invalid id");
    }
}
