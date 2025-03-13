# Singly-Linked-List---Insert-Operation
This is to know about how insertion operation done in singly linked list.
 
class Node{
    int data;
    Node next;
    // constructor
    Node(int data){
        this.data=data;
        this.next=null;
    }
}
class SinglyLinkedList{
    Node head;
    //insert at begin
    public void InsertAtbegin(int data)
    {
        Node newnode=new Node(data);
        newnode.next=head;
        head=newnode;
    }
    //insert at position
    public void InsertAtPosition(int position,int data){
        if (position<=0)
        {
            System.out.println("Invalid position");
            return;
        }
        Node newnode=new Node(data);
        if(position==1)
        {
            newnode.next=head;
            head=newnode;
            return;
        }
        Node temp=head;
        for(int i=0;i<position-1 && temp!=null ;i++)
        {
          temp=temp.next;  
        }
        if(temp==null)
        {
            System.out.println("position is exceed");
            return;
        }
        newnode.next=temp.next;
        temp.next=newnode;
    }
    // insert at the end
    public void InsertAtend(int data)
    {
        Node newnode=new Node(data);
        //if head is null 
        if (head==null)
        {
            head=newnode;
            return;
        }
        Node temp=head;
        while(temp.next!=null)
        {
            temp=temp.next;
        }
        temp.next = newnode;
    }
//display function 
     public void display()
    {
        Node temp=head;
        if (temp==null)
        {
            System.out.println("list is empty");
        }
        while(temp!=null)
        {
            System.out.print(temp.data);
            if(temp.next!=null)
            {
            System.out.print("->");
            }
            temp=temp.next;
        }    
        System.out.println(" ");        
    }
}
public class Main
{
	public static void main(String[] args)
	{
		SinglyLinkedList list = new SinglyLinkedList();
		list.InsertAtbegin(1);
		list.InsertAtbegin(2);
		list.InsertAtbegin(3);
		list.InsertAtbegin(4);
		list.display();
		list.InsertAtPosition(3,10);
	  list.display();
		list.InsertAtend(0);
		list.InsertAtend(9);
		list.InsertAtend(8);
		list.InsertAtend(7);
		list.display();
  }
}


Output:

4->3->2->1
4->3->2->10->1
4->3->2->10->1->0->9->8->7 
