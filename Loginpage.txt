import javax.swing.*;
import java.awt.event.*;
import java.awt.*; 
import java.io.*;
	


//********************************************   Loginpage   *************************************************

class Loginpage
{  
	Loginpage()
	{				
		
		
		JFrame f=new JFrame("HOME");
		
		JLabel l11=new JLabel(" - ONLINE PORTAL FOR PET'S REGISTRATION  -");
		l11.setBounds(235,105,500,30);
		l11.setFont(new Font ("Arial",Font.PLAIN,20));
		f.add(l11);


//*** username and passowrd ***
			
JLabel l1=new JLabel("User name");
l1.setBounds(340,200,95,30);
f.add(l1);

JTextField t1=new JTextField("");
t1.setBounds(440,200,130,30);
f.add(t1);

JLabel l2=new JLabel("Password");
l2.setBounds(340,250,95,30);
f.add(l2);

JPasswordField t2=new JPasswordField("");
t2.setBounds(440,250,130,30);
f.add(t2);


//***Checkbox***
JCheckBox c1 = new JCheckBox("Accept the terms and conditions."); 
c1.setBounds(380,310,300,20);
f.add(c1);


//***Login button*** 

JButton b=new JButton("Login");
b.setBounds(455,355,95,30);
f.add(b);
b.addActionListener(new ActionListener() {	
	public void actionPerformed(ActionEvent ae) {
		String uname=t1.getText();
		String psd=t2.getText();
		// default username & passwords	
		if (uname.equals("admin") && psd.equals("admin") && c1.isSelected() )
			{
				f.dispose();
				new User();
			}	
		else
			{
			JOptionPane.showMessageDialog(f,"       Invalid username or password!!!  \n                            (or)\n please accept the terms and conditions!!!");
			}
	}
	});
	
	
//*** Register Button***
 	
JButton b1=new JButton("Register");
b1.setBounds(480,425,85,20);
f.add(b1);
b1.addActionListener(new ActionListener() {
	
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Form();
			}
		});

JLabel l3=new JLabel("Don't have a account..?");
l3.setBounds(340,410,140,50);
f.add(l3);		
		

	
	
//***Rescued pet's button

		JButton resPets =new JButton("NGO'S Rescued Pets");
		f.add(resPets);
		resPets.setBounds(670,40,200,30);
		resPets.addActionListener(new ActionListener() {
				public void actionPerformed(ActionEvent ae) {
				f.dispose();
				Ngos n=new Ngos();
				n.ngos();
			}
		});

f.setSize(900,600);
f.setLayout(null);
f.setVisible(true);
f.setResizable(false);
f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
}

// ****   MAIN METHOD   ****
		
public static void main(String[] sri)
{
new Loginpage();
}
}










//**************************************************user login page********************************************************
class User {
	private JFrame f = new JFrame("Welcome");
	public User() {
			JLabel l=new JLabel("WELCOME");
			l.setBounds(140,70,250,30);
			l.setFont(new Font ("Arial",Font.PLAIN,20));
			f.add(l);



//*** Register Button***

JLabel l1=new JLabel("Register another pet :");
l1.setBounds(50,150,200,30);
f.add(l1);
 	
JButton b1=new JButton("Register");
b1.setBounds(200,155,85,20);
f.add(b1);
b1.addActionListener(new ActionListener() {
	
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Form();
			}
		});
		

//****missing button***
JLabel l2=new JLabel("Missing pet :");
l2.setBounds(50,200,200,30);
f.add(l2);		
		JButton miss=new JButton("Missing");
			miss.setBounds(200,205,85,20);
			f.add(miss);
			miss.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Missing();
			}
		});


//***Rescued pet's button

		JButton resPets =new JButton("Rescued Pets");
		f.add(resPets);
		resPets.setBounds(250,20,120,20);
		resPets.addActionListener(new ActionListener() {
				public void actionPerformed(ActionEvent ae) {
				f.dispose();
				Ngos n=new Ngos();
				n.ngos();
			}
		});

//***loginpage button***	
	JButton back=new JButton("Signout");
			back.setBounds(250,320,80,20);
			f.add(back);
			back.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Loginpage();
			}
		});
		
	JLabel l8=new JLabel("Click here to signout...");
	l8.setBounds(110,315,200,30);
	f.add(l8);

f.setSize(400,400);
f.setLayout(null);
f.setVisible(true);
f.setResizable(false);
f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	}
}









//  **************************************    Registration FORM   ****************************************

class Form 
	{
	private JFrame f = new JFrame("Registration form");
	public Form() {
			JLabel l=new JLabel("- REGISTRATION FORM -");
			l.setBounds(100,70,250,30);
			l.setFont(new Font ("Arial",Font.PLAIN,20));
			f.add(l);
			
			
//***name***
JLabel l1=new JLabel("Name  :");
l1.setBounds(50,150,95,30);
f.add(l1);

JTextField t1=new JTextField("");
t1.setBounds(175,157,140,20);
f.add(t1);

//***Age***
JLabel l2=new JLabel("Age    :");
l2.setBounds(50,200,95,30);
f.add(l2);

JTextField  t2= new JTextField();
t2.setBounds(175,207,40,20);
f.add(t2);

//***colour***
JLabel l3=new JLabel("Colour  :");
l3.setBounds(50,250,95,30);
f.add(l3);

JRadioButton j1=new JRadioButton("Black");	
j1.setBounds(150,250,60,30);			
f.add(j1);

JRadioButton j2=new JRadioButton("White");	
j2.setBounds(220,250,60,30);			
f.add(j2);

JRadioButton j3=new JRadioButton("Brown");	
j3.setBounds(290,250,70,30);			
f.add(j3);

JRadioButton j4=new JRadioButton("White/black");	
j4.setBounds(370,250,90,30);			
f.add(j4);


//***Breed***
JLabel l4=new JLabel("Breed  :");
l4.setBounds(50,300,95,30);
f.add(l4);

String s1[] = {"SELECT", "American Bulldog","Molossus","Norwich Terrier", "American Pugabull", "Chow Chow","Indian Spitz","Keeshond", "Combai","Field Spaniel", "Clumber Spaniel", "Boxer", "Braque Francais", "Cesky Terrier", "Carolina Dog", "Chinook","Leonberger","Lowchen", "Others" }; 
JComboBox t4=new JComboBox(s1);
t4.setBounds(175,307,150,20);
f.add(t4);

//***Weight***
JLabel l5=new JLabel("weight  :");
l5.setBounds(50,350,95,30);
f.add(l5);

JTextField t5=new JTextField("");
t5.setBounds(175,357,40,20);
f.add(t5);

//***unique features***
JLabel l6=new JLabel("unique features  :");
l6.setBounds(50,400,100,30);
f.add(l6);

JTextField t6=new JTextField("");
t6.setBounds(175,407,140,20);
f.add(t6);

//***Owners name***
JLabel l7=new JLabel("Owner's name  :");
l7.setBounds(50,450,140,30);
f.add(l7);


JTextField t7=new JTextField("");
t7.setBounds(175,457,140,20);
f.add(t7);

//***Ownes contact number***
JLabel l17=new JLabel("Contact number  :");
l17.setBounds(50,500,120,30);
f.add(l17);

JTextField t17=new JTextField("");
t17.setBounds(175,507,100,20);
f.add(t17);


//***Checkbox***
JCheckBox c1 = new JCheckBox("Accept the terms and conditions."); 
c1.setBounds(120,540,300,20);
f.add(c1);

//***Submit button***
JButton b=new JButton("Submit");
			b.setBounds(200,570,95,20);
			f.add(b);
			
			
			b.addActionListener (new ActionListener(){
			public void actionPerformed(ActionEvent e)
{
if(c1.isSelected())			
				
				{
					JOptionPane.showMessageDialog(f,"Succesfully Registered...");
			try
          	{

				File file = new File("Register.txt");
				FileWriter fr = new FileWriter(file, true);
				fr.write("\nName                : "+t1.getText()+"\n");
				fr.write("Age                   : "+t2.getText()+"\n");
				fr.write("Weight  	         : "+t5.getText()+"\n");
				fr.write("Unique features        : "+t6.getText()+"\n");
				fr.write("Owner's name        : "+t7.getText()+"\n");
				fr.write("Contact number        : "+t17.getText()+"\n");
				fr.close();

			}   
		catch(Exception ae )
 			{
   				System.out.println("Not Created check once");
 			}
           f.dispose();
				}
else
{
JOptionPane.showMessageDialog(f,"Please accept the terms and contitions");
}
}
});
	
	


//***loginpage button***	
	JButton back=new JButton("Login page");
			back.setBounds(300,705,100,20);
			f.add(back);
			back.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Loginpage();
			}
		});
		
	JLabel l8=new JLabel("If you Aldready have account please login...");
	l8.setBounds(50,700,500,30);
	f.add(l8);


//***Rescued pets button***
		JButton resPets =new JButton("Rescued Pets");
		f.add(resPets);
		resPets.setBounds(340,20,140,22);
		resPets.addActionListener(new ActionListener() {
				public void actionPerformed(ActionEvent ae) {
				f.dispose();
				Ngos n=new Ngos();
				n.ngos();
			}
		});	
	
	JLabel l9=new JLabel("If any pet is missing...");
	l9.setBounds(125,615,500,30);
	f.add(l9);
	

//***Missing pets form button***	
	JButton miss=new JButton("Missing pet's complaints");
			miss.setBounds(250,620,200,25);
			f.add(miss);
			miss.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Missing();
			}
		});

f.setSize(500,800);
f.setLayout(null);
f.setVisible(true);
f.setResizable(false);
f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	}
}










//    ******************************************    Missing Form    *************************************

class Missing {
	private JFrame f = new JFrame("Missing pet registration");
	public Missing() {
			
			JLabel l=new JLabel("- MISSING PET'S REGISTRATION FORM -");
			l.setFont(new Font ("Arial",Font.PLAIN,20));
			l.setBounds(50,70,500,30);
			f.add(l);
			
			
//***name***
JLabel l1=new JLabel("Name  :");
l1.setBounds(50,150,95,30);
f.add(l1);

JTextField t1=new JTextField("");
t1.setBounds(175,157,140,20);
f.add(t1);

//***Age***
JLabel l2=new JLabel("Age    :");
l2.setBounds(50,200,95,30);
f.add(l2);

JTextField  t2= new JTextField();
t2.setBounds(175,207,40,20);
f.add(t2);

//***colour***
JLabel l3=new JLabel("Colour  :");
l3.setBounds(50,250,95,30);
f.add(l3);

JRadioButton j1=new JRadioButton("Black");	
j1.setBounds(150,250,60,30);			
f.add(j1);

JRadioButton j2=new JRadioButton("White");	
j2.setBounds(220,250,60,30);			
f.add(j2);

JRadioButton j3=new JRadioButton("Brown");	
j3.setBounds(290,250,70,30);			
f.add(j3);

JRadioButton j4=new JRadioButton("White/black");	
j4.setBounds(370,250,90,30);			
f.add(j4);




//***Breed***
JLabel l4=new JLabel("Breed  :");
l4.setBounds(50,300,95,30);
f.add(l4);

String s1[] = {"SELECT", "American Bulldog","Molossus","Norwich Terrier", "American Pugabull", "Chow Chow","Indian Spitz","Keeshond", "Combai","Field Spaniel", "Clumber Spaniel", "Boxer", "Braque Francais", "Cesky Terrier", "Carolina Dog", "Chinook","Leonberger","Lowchen", "Others" };  
JComboBox t4=new JComboBox(s1);
t4.setBounds(175,307,150,20);
f.add(t4);

//***Weight***
JLabel l5=new JLabel("weight  :");
l5.setBounds(50,350,95,30);
f.add(l5);

JTextField t5=new JTextField("");
t5.setBounds(175,357,40,20);
f.add(t5);

//***unique features***
JLabel l6=new JLabel("unique features  :");
l6.setBounds(50,400,120,30);
f.add(l6);

JTextField t6=new JTextField("");
t6.setBounds(175,407,140,20);
f.add(t6);

//***Owners name***
JLabel l7=new JLabel("Owner's name  :");
l7.setBounds(50,450,95,30);
f.add(l7);

JTextField t7=new JTextField("");
t7.setBounds(175,457,140,20);
f.add(t7);

//***Ownes contact number***
JLabel l17=new JLabel("Contact number  :");
l17.setBounds(50,500,120,30);
f.add(l17);

JTextField t17=new JTextField("");
t17.setBounds(175,507,100,20);
f.add(t17);


//***Checkbox***
JCheckBox c1 = new JCheckBox("Accept the terms and conditions."); 
c1.setBounds(120,540,300,20);
f.add(c1);


//***Submit button***
JButton b=new JButton("Submit");
			b.setBounds(200,570,95,20);
			f.add(b);
			
			
			b.addActionListener (new ActionListener(){
			public void actionPerformed(ActionEvent e)
{
if(c1.isSelected())			
				
				{
					JOptionPane.showMessageDialog(f,"Succesfully Added missing information...");
			try
          	{

				File file = new File("Missing.txt");
				FileWriter fr = new FileWriter(file, true);
				fr.write("\nName                : "+t1.getText()+"\n");
				fr.write("Age                   : "+t2.getText()+"\n");
				fr.write("Weight  	         : "+t5.getText()+"\n");
				fr.write("Unique features        : "+t6.getText()+"\n");
				fr.write("Owner's name        : "+t7.getText()+"\n");
				fr.write("Contact number        : "+t17.getText()+"\n");
				fr.close();

			}   
		catch(Exception ae )
 			{
   				System.out.println("Not Created check once");
 			}
           f.dispose();
				}
else
{
JOptionPane.showMessageDialog(f,"Please accept the terms and contitions");
}
}
});

//***pet photo***
JTextArea t8=new JTextArea("\n \n \n     PET PHOTO");
t8.setBounds(350,130,100,100);
t8.setEditable(false);
f.add(t8);


//***Loginpage buttonm***
			JButton back=new JButton("Login page");
			back.setBounds(300,705,100,20);
			f.add(back);
			back.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Loginpage();
			}
		});
		
		JLabel l8=new JLabel("If you Aldready have account please login...");
		l8.setBounds(50,700,500,30);
		f.add(l8);
		
//***registration form button***
					JButton Form=new JButton("Form");
			Form.setBounds(285,620,100,20);
			f.add(Form);
			Form.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent ae) {
				f.dispose();
				new Form();
			}
		});
		
		JLabel l9=new JLabel("Back to Registration form...");
		l9.setBounds(125,615,500,30);
		f.add(l9);

//***rescued pet button***		
		JButton resPets =new JButton("Rescued Pets");
		f.add(resPets);
		resPets.setBounds(340,20,140,22);
		resPets.addActionListener(new ActionListener() {
				public void actionPerformed(ActionEvent ae) {
				f.dispose();
				Ngos n=new Ngos();
				n.ngos();
			}
		});	

f.setSize(500,800);
f.setLayout(null);
f.setVisible(true);
f.setResizable(false);
f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	}
}






//     **********************************************   Ngos   ***************************************

class Ngos extends Canvas{  
      
    public void paint(Graphics g) {  
  
        Toolkit t=Toolkit.getDefaultToolkit();  
        Image i=t.getImage("pet1.jpg");
        g.drawImage(i, 100,50,this); 
        Image j=t.getImage("pet2.jpg");
        g.drawImage(j, 140,330,this);  		      
    }  
	void ngos()
	{  
        Ngos m=new Ngos();  
        JFrame f=new JFrame("pets rescued by NGO's");  
		
			JLabel l=new JLabel("- PET'S RESCUED BY NGO'S -");
			l.setFont(new Font ("Arial",Font.PLAIN,20));
			l.setBounds(135,10,500,30);
			f.add(l);
    
	// 1st pet details    
	
	JLabel l1=new JLabel("Name  :Puppy");
	l1.setBounds(340,140,95,30);
	f.add(l1);
	
	JLabel l2=new JLabel("Age  :6");
	l2.setBounds(340,160,95,30);
	f.add(l2);
	
	JLabel l3=new JLabel("Breed  :Beagle");
	l3.setBounds(340,180,95,30);
	f.add(l3);
	
	JLabel l4=new JLabel("Colour  :White");
	l4.setBounds(340,200,95,30);
	f.add(l4);
	
	JLabel l5=new JLabel("weight  :60Pounds");
	l5.setBounds(340,220,115,30);
	f.add(l5);
	
	
	// 2nd pet details
	
	JLabel l11=new JLabel("Name  :Akita");
	l11.setBounds(150,520,95,30);
	f.add(l11);
	
	JLabel l21=new JLabel("Age  :5");
	l21.setBounds(150,540,95,30);
	f.add(l21);
	
	JLabel l31=new JLabel("Breed  :pug");
	l31.setBounds(150,560,95,30);
	f.add(l31);
	
	JLabel l41=new JLabel("Colour  :brown");
	l41.setBounds(150,580,95,30);
	f.add(l41);
	
	JLabel l51=new JLabel("weight  :50Pounds");
	l51.setBounds(150,600,115,30);
	f.add(l51);
	    
//***Loginpage button***
	JButton back1=new JButton("Click here to go Login page");
	back1.setBounds(150,700,340,30);
	f.add(back1);
	back1.addActionListener(new ActionListener() {
	public void actionPerformed(ActionEvent ae) {
	f.dispose();
	new Loginpage();
			}
});	

		f.add(m);
        f.setSize(600,800); 		
        f.setVisible(true); 
		f.setResizable(false);
		f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		}	
}