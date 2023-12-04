#stack class..........................
import javax.swing.JOptionPane;

public class stack<T> {
	T element[];
	int top;
	
	stack(T element[])
	{
		this.element = element;
		this.top = -1;
	}
	
	void push(T var)
	{
		try {
			element[++top] = var;
		} catch(ArrayIndexOutOfBoundsException e) {
			JOptionPane.showMessageDialog(null, "Overflow");
			
		}
	}
	
	T pop()
	{
		if(!empty())
			return element[top--];
		else
			return null;
	}
	
	boolean empty()
	{
		if(top == -1)
			return true;
		else
			return false;
	}
	
	T stackTop()
	{
		if(top == -1)
			return null;
		else
			return element[top];
	}
	String display()
	{
		String str = "";
		for(int i=0; i<=top; i++)
		{
			str = str + (element[i]) + ' ';
		}
		return str;
	}
}
///////main class///////

import javax.swing.JOptionPane;
public class startup{
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Integer array[] = new Integer[5];
		stack<Integer> s = new stack<Integer>(array);
		int choice = 0;
		
		do {
			choice = Integer.parseInt(JOptionPane.showInputDialog
					( "Enter \n0: Stop \n1: Push \n2: pop "
							+ "\n3: Stack Top \n4: Display \n5: Empty"));
			switch(choice) 
			{
				case 1: Integer el = Integer.parseInt(JOptionPane.
						showInputDialog( "Enter Element"));
						s.push(el);
				break;
				case 2: s.pop();
				break;
				case 3: JOptionPane.showMessageDialog(null,"Top element is " 
				+ s.stackTop());
				break;
				case 4: JOptionPane.showMessageDialog(null, s.display());
				break;
				case 5: JOptionPane.showMessageDialog(null, s.empty());
			}
			
		} while(choice != 0);
	}

}
.........................................................book(array of object xlass....................................


import java.util.*;
public class Book {

	public String bookname;
	public String subject;
	Publisher P;

	Author[]a= new Author [2];
	public Book(String bookname,String subject)
	{
		this.bookname=bookname;
		this.subject=subject;
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter publisher name");
		String n=sc.next();
		System.out.println("Telephone");
		String t=sc.next();
		P=new Publisher(n,t);
		
		
		for(int i=0; i<2; i++)
		{
			System.out.println("Enter Author name:");
			String aname = sc.next();
			System.out.println("Enter Author telephone:");
			String telephone1 = sc.next();
			System.out.println("Enter Author address:");
			String address=sc.next();
			
			a[i]= new Author (aname,telephone1,address);
		}
		
	}

			
	
	public void display()
	{
		System.out.println("Book name: "+this.bookname 
				);
		P.display();
		for(int i=0;i<2; i++)
		{
		a[i].display();
		}
	}
	
}
............................................................................................theatre(for rating and capacity......................



public class theatre {
private String tname;
private String tlocation;
private int capacity;
private double rating;
public theatre()
{
	this.tname="Abc";
	this.tlocation="xyz";
	this.capacity=200;
	this.rating= 5.5;
}
public theatre(String tname, String tlocation,int capacity,double rating)
{
	this.tname=tname;
	this.tlocation=tlocation;
	this.capacity=capacity;
	this.rating=rating;
}
public String getTname() {
	return tname;
}
public String getTlocation() {
	return tlocation;
}
public int getCapacity() {
	return capacity;
}
public double getRating() {
	return rating;
}
void display()
{
	System.out.println("Theatre name: "+this.tname +"\nTheatre location:" +this.tlocation
			+"\ncapacity:" +this.capacity + "\nrating:" +this.rating);
}

}

.......................................



import java.util.*;
public class startup {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int i;
		theatre []t = new theatre[3];
		Scanner sc= new Scanner(System.in);
		for(i=0; i<3; i++)
		{
			System.out.println("Enter theatre name:");
			String tname = sc.next();
			System.out.println("Enter theatre location:");
			String tlocation = sc.next();
			System.out.println("Enter theatre capacity:");
			int capacity = sc.nextInt();
			System.out.println("Enter theatre rating:");
			double rating = sc.nextDouble();
			t[i]= new  theatre (tname,tlocation,capacity,rating);
			}
		for(i=0; i<3; i++)
		{
			if(t[i].getCapacity()>200 && t[i].getRating()>3)
			{
				t[i].display();
			}
		}
		
	}	

}

......................done..............................
