# STACK
#include<iostream>
using namespace std;
#define MAX 10
class stack{
int a[MAX];
int top;

public:
    void init(){
    top=-1;}

    void push(int data){
    if(top==MAX-1){
        cout<<"stack overflow"<<endl;
        return;
    }
    top++;
    a[top]=data;
    }

    int pop(){
    int n;
    if(top==-1){
        cout<<"stack underflow"<<endl;
        return n=9999;
    }
    int popitem=a[top];
    top--;
    return popitem;
    }

    void display(){
    for(int i=0;i<=top;i++)
        cout<<a[i];
    }

    int isempty(){
    if(top==-1)
        return 1;//true condition
    else
        return 0;//false condition
    }

    int isfull(){
    if(top==MAX-1)
        return 1;
    else
        return 0;
    }

    int peek(){
    cout<<a[top];
    }


…
[10:57 PM, 8/21/2022] Nayanika Csbs: #include<iostream>
using namespace std;

class node{
int data;
node *next;
public:
    node *top=NULL;

    void push (int d)
    {
        node *current = new node();
        current->data=d;
        current->next=NULL;
        if(top==NULL)
        {
            top=current;
        }
        else {
        current->next=top;
        top=current;}

    }

    int pop(){
    if(top==NULL)
        {
            cout<<"underflow";
            return 9999;
        }


    node *temp =top;
    int x = top->data;
    top=top->next;
    delete(temp);
    return x;
    }

    void display(){
    if(top==NULL)
        cout<<"empty stack";
        else{
            node *temp=top;
            while(temp!=NULL)
            {
                cout<<temp->data<<endl;;
                temp=temp->next;
            }
        }

    }
};

int main(){
    node n;
    n.push(10);
    n.push(20);
    n.display();

}

#STACK IMPLEMENTATION USING LINKED LIST
#include<iostream>
using namespace std;

class node{
int data;
node *next;
public:
    node *top=NULL;

    void push (int d)
    {
        node *current = new node();
        current->data=d;
        current->next=NULL;
        if(top==NULL)
        {
            top=current;
        }
        else {
        current->next=top;
        top=current;}

    }

    int pop(){
    if(top==NULL)
        {
            cout<<"underflow";
            return 9999;
        }


    node *temp =top;
    int x = top->data;
    top=top->next;
    delete(temp);
    return x;
    }

    void display(){
    if(top==NULL)
        cout<<"empty stack";
        else{
            node *temp=top;
            while(temp!=NULL)
            {
                cout<<temp->data<<endl;;
                temp=temp->next;
            }
        }

    }
};

int main(){
    node n;
    n.push(10);
    n.push(20);
    n.display();

}

#QUEUE
#include<iostream>
using namespace std;
#define MAX 10

class que{
int a[MAX];
int r,f;
public:
void init(){
r=-1;
f=-1;
}

void enqueue(int data){
if(r==MAX-1)
    {
        cout<<"queue is full";
        return;
    }
else{
    r++;
    a[r]=data;
}
}

int dequeue(){
if(r==f)
{
    cout<<"empty q"<<endl;
    return 9999;
}
f++;
return a[f];
}

void display(){
for(int i=f+1;i<=r;i++)
    cout<<a[i]<<endl;
}

 };

int main(){
que q;
q.init();
q.enqueue(10);
q.display();

}

#QUEUE IMPLEMENTATION USING LINKEDLIST
#include<iostream>
using namespace std;

class node{
int data;
node *next;
public:
    node *r,*f;
    void init(){
    r=NULL;
    f=NULL;}


void enqueue(int d){
node *current = new node();
current->data=d;
current->next=NULL;
}

int dequeue(){
if(r=NULL){
    cout<<"empty q"<<endl;
    return 9999;
}
else{
    int x=f->data;
    node *temp=f;
    f=f->next;
    delete(temp);
    return x;
}
}

void display(){
node *temp=f;
while(temp!=NULL)
    {
        cout<<temp->data;
        temp=temp->next;
    }
}

};

int main(){
node n;
n.init();
n.enqueue(10);
n.enqueue(20);
cout<<n.dequeue();
}

#LINKEDLIST
#include<iostream>
using namespace std;

class node{
int data;
node *next;
public:
    node *first;

    void init(){
        first=NULL;
        }

    void finsert(int d){
        node *current=new node();
        current->data=d;
        current->next=NULL;
        if(first==NULL){
            first=current;
        }
        else{
            current->next=first;
            first=current;
        }
    }

    int fdelete(){
    int x= first->data;
    node *temp=first;
    first=first->next;
    delete(temp);
    cout<<"deleted item is"<<x<<endl;
    return x;
    }

    void display(){
    node *temp=first;
    while(temp!=NULL){
        cout<<temp->data<<endl;
        temp=temp->next;
    }
    }

    void binsert(int d){
    node *current = new node();
    current->data=d;
    current->next=NULL;
    node *temp=first;
    while(temp->next!=NULL){
        temp->next=current;
    }
    temp->next=current;
    }

    int bdelete(){
    node *temp=first;
    node *prev=NULL;
    while(temp->next!=NULL){
        prev=temp;
        temp=temp->next;
    }
    prev->next=NULL;
    int x= temp->data;
    delete(temp);
    return x;
    }

    void midinsert(int d){
    int n;
    cout<<"after how many nodes you want to insert?"<<endl;
    cin>>n;
    node *current=new node();
    current->data=d;
    current->next=NULL;
    int i=1;
    node *temp=first;
    while(i<n){
        temp=temp->next;
        i++;
    }
        current->next=temp->next;
        temp->next=current;
    }

    int middelete(){
    int x;
    cout<<"what do you want to delete?"<<endl;
    cin>>x;
    node *temp=first;
    node *prev=NULL;
    while(temp->data!=x && temp->next!=NULL){
        prev=temp;
        temp=temp->next;
    }
    prev->next=temp->next;
    delete(temp);
    return x;

    }
};

int main(){
    node n;
    n.init();
    n.finsert(10);
    n.finsert(20);
    //n.display();
    n.midinsert(30);
    n.bdelete();
    n.fdelete();
    n.display();
}

#DOUBLY LINKEDLIST
#include<iostream>
using namespace std;
class node
{
	node *prev;
	int data;
	node *succ;
	public:
	node *head=NULL;
	void insertbeg(int val)
	{
	node *nn=new node();
	nn->data=val;
	nn->succ=NULL; 	
	nn->prev=NULL;
	if(head==NULL)
	{
	  	  head=nn;
	  	 
	  	  return;
    }
    else
    {nn->succ=head;
     head->prev=nn;
     head=nn;
	}
   }
  void insertend(int val)
   {
   	node *nn=new node();
	nn->data=val;
	nn->succ=NULL;
	nn->prev=NULL;
	if(head==NULL)
	{
	  	  head=nn;
	  	  return;
    }
    node *temp=head;
    while(temp->succ!=NULL)
    { temp=temp->succ;
	}
	
	temp->succ=nn;
	nn->prev=temp;
	
   }
   void deletebeg()
   {
   	  node *temp;
   	if(head==NULL)
   	{cout<<" the list is empty. u can't delete";
   	 return;
	 }
   	temp=head;
   	head=head->succ;
   	head->prev=NULL;
   	cout<<"the deleted item is "<<temp->data;
   	delete(temp);
   }
   void deleteend()
   {
   	node  *temp=head;
   	while(temp->succ!=NULL)
   	   	  temp=temp->succ;
   (temp->prev)->succ=NULL;
   cout<<"the deleted item is "<<temp->data;
   delete(temp);
   }
   
   void display()
   {
   	node *temp=head;
   	while(temp!=NULL)
   	{
   		cout<<temp->data<<" ";
   		temp=temp->succ;
	   }
   }
   void insertmiddle(int val)
   {int n;
   	node *nn=new node();
	nn->data=val;
	nn->succ=NULL;
	nn->prev=NULL;
	if(head==NULL)
	{
	  	  head=nn;
	  	  return;
    }
    cout<<"enter the number of nodes after which you want to insert this";
    cin >>n;
    node *temp=head;
    int count=1;
    while(count<n && temp->succ!=NULL)
    {
      temp=temp->succ;
      count++;
	}
	nn->succ=temp->succ;
	(temp->succ)->prev=nn;
	temp->succ=nn;
	nn->prev=temp;
   }
   void deletemiddle()
   {int delval;
   	 node *temp=head;
   	 cout<<"enter the node value that u want to delete";
   	 cin>>delval;
   	 while(temp->data!=delval&&temp->succ!=NULL)
   	 	temp=temp->succ;
	 if(temp->data!=delval)
	{cout<<"there is no such node in the list";
	  return;
	}
	 (temp->prev)->succ=temp->succ;
	 (temp->succ)->prev=temp->prev;
	 cout<<"deleted item is "<<temp->data;
	 delete(temp);
   }
};
int main()
{
	int choice,val;
	node obj;
	do
	{
	
	cout<<"enter ur choice 1-insert in the beg 2-insert at the end .......";
	cin>>choice;
	switch(choice)
	{
		case 1: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.insertbeg(val);
		        break;
	    case 2: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.insertend(val);
		        break;
		case 3: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.insertmiddle(val);
		        break;
	    	    
	    case 4:obj.deletebeg();
	           break;
	    case 5:obj.deleteend();
	           break;
	    case 6: obj.deletemiddle();
	            break;
	    case 7: obj.display();
	            break;
	    
	}
  }while(choice!=8);
}

#infix to postfix
#include<iostream>
#include<string.h>
using namespace std;
#define MAX 30

  char a[MAX];  //As the expression contains operators & operands, use a char array
   int top;

void init()
{
     top=-1;
}
void push(char data)
{
     top++;
     a[top]=data;
     
}
char pop()
{   if(top!=-1)
    { int x=a[top];
    
       top--;
       return x;
	}
    else
      return('\0');
}
int priority(char data)
{
    if(data=='*'||data=='/'||data=='%')
       return 3;
   else if(data=='-'||data=='+')
       return 2;
   else if(data=='>' || data == '<')  
      return 1;  
    else
      return 0;
}



int main()
{
  int len,j,k=0;
  char opr;
  string s,post;
  cout<<"enter the infix expression to be converted\n";
  getline(cin,s);   // a  *b+c     7-3
            //  01234
  len=s.length();  
  init();
  
  for(j=0;j<len;j++)  // this loop is to process the characters of the entire expression one by one 
  {
     if((s[j]==' ')||(s[j]=='\t'))  // to ignore unwanted spaces left in between the characters of the expression
      continue;
     else if((isdigit(s[j]))||(isalpha(s[j])))  // this condition will evaluate to true for an operand
     {                                                       // an operand can be a digit or alphabet and so simply add it to 
      post.append(1,s[j]);                                      // post string
    }
    else if(s[j]=='(')                                 // if character is '(' push it onto the stack
      push(s[j]);
    else if(s[j]==')')                             // if character is ')'
    {
       do
       {
	 opr=pop();                       // pop the next character from the top of stack
	 if(opr=='(')    // if popped character is '(' simply ignore
	   break;
	 else
	  post.append(1,opr);                      // else append the popped character to post string
	 }while (opr!='(');       // the above steps are repeated till an '(' is encountered.
    }
    else                                    // this 'else' part will handle operators
    {
	if(top== -1)         // if stack is empty, simply push the current character (which is an operator)
	  push(s[j]);            // on to the stack
	else
	{
	opr=pop(); 
	if(opr=='(')
	{
	  push(opr);
	  push(s[j]);
	}  
	else
	{        // otherwise pop the topmost operator (opr) and compare priority of 'opr' with 
    while(priority(opr)>=priority(s[j]))  // priority of current operator. If priority of opr is higher, append it 
	{                                           // to post string and repeat the 'pop' & 'compare' operations till
	    post.append(1,opr);                   // the popped character 'opr' has a lesser priority than that of curren                               // operator (c[j]) or till the stack becomes empty
	    opr=pop();
	    if(opr=='\0')
	      break;
	}
	push(opr);                //else if priority of popped character 'opr' is lesser than that of current 
	push(s[j]);               // operator,we should push the current operator onto stack. But before that 
      } 
	  }                                    // we should also push the operator that we popped for comparison
    }                                       // Hence two 'push' statements
  }    // at the end of this 'for' loop entire expression would have been processed. 
  char x;
  do // at last pop the remaining contents from the stack and append them to post string
  { x=pop();
    if (x!='\0')
	  post.append(1,x);
   }while (x!='\0');
  post.append(1,'\0');    // also add a NULL character at the end of 'post' string
  cout<<post;
  return 0;
}

#POSTFIX EVALUATION
#include<iostream>
#include<string.h>
#define MAX 30
using namespace std;

  int a[MAX];
   int top;

void init()
{
     top=-1;
}
void push(int data)
{
     int i;
     top++;
     a[top]=data;
}
int pop()
{
     return(a[top--]);
}
int eval(int d1,int d2,char sym) // this function takes 2 operands and 1 operator as input parameters
{                                                 // and evaluates the 2 operands based on the operator and returns the result
    int r;
    switch(sym)
    {
      case '+':  r=d1+d2; break;
      case '-':  r=d1-d2; break;
      case '*':  r=d1*d2; break;
      case '/':  r=d1/d2; break;
      case '%':  r=d1%d2; break;
    }
    return(r);
}
int main()
{
  int i,j,val,opd1,opd2;
  
  string post;   //34+
  printf("enter the postfix expression to be evaluated\n");
  getline(cin,post); //34+
  i=post.length();  //3  
  init();              
  for(j=0;j<i;j++)     //"34+"   //ab+  post[0] ='a' post[1]='b'  post[2]='+'
  {

     if((post[j]==' ')||(post[j]=='\t'))  
      continue; 
     else if(isdigit(post[j]))    
     {      //'3'-'0'  post[j]-'0'
       val=post[j]-48;    // if the operands in the expression are digits, directly we can use the value of the           
       push(val);      // current operand and push it
     }               //'a'
     else if(isalpha(post[j]))  // if the operand is an alphabet, get the input for the operand and use it for 
     {                                                         // further processing and push it
      cout<< "enter the value of "<<post[j];
      cin>>val;
      push(val);
     }
    
    else
    {
	opd2=pop();   // if the current character is an operator, pop the 2 topmost elements from 
	opd1=pop();    // stack and call eval function to evaluate them. Push the value returned by that 
	int x=eval(opd1,opd2,post[j]);
	push(x); // function onto the stack
      }
  }
  cout<<"the result of the give postfix expression is \n"<<pop(); // pop the result and display
  return 0;
}

#DYNAMIC QUEUE
#include<iostream>
#define max 60
using namespace std;
class node
{
	int data;
	node *next;
	public:
	node *rear=NULL,*front=NULL;
	void enqueue(int val)
	{
	  	node *newnode=new node();
	  	newnode->data=val;
	  	newnode->next=NULL;
	  	if(rear==NULL)
	  	{
		  front=newnode;
		  rear=newnode;
	    }
	  	else
	  	{
	  	  rear->next=newnode;
	  	  rear=newnode;
		  }
 
}
int dequeue()
{
	if(isempty())
	
		cout<<"queue is empty. Can't dequeue....";
	else
	{
	node *temp=front;      
	int x=temp->data;
	front=front->next;
	if(front==NULL)
	  rear=NULL;
	delete(temp);
	return(x);
	
    }
}
void display()
{node *temp=front;
while(temp!=NULL)
{
  cout<<temp->data<<" ";
  temp=temp->next;
}
	
}
int isempty()
{
	if(rear==NULL)
	  return 1;
	else
	  return 0;
}
};

int main()
{
	int choice,val,x;
	node obj;
	do
	{
	
	cout<<"enter ur choice 1-enqueue 2-dequeue 3-display .......";
	cin>>choice;
	switch(choice)
	{
		case 1: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.enqueue(val);
		        break;
	    case 2: if(!obj.isempty())
	            {
		        x=obj.dequeue();
		        cout<<"dequeued item is "<<x<<"\n";
		        }
		        else
		          cout<<"queue is empty";
				break;
		case 3: obj.display();
	            break;
	    default: exit(0);
	    
	}
  }while(choice!=4);
}

#DYNAMIC STACK
#include<iostream>
using namespace std;
class node
{
	int data;
	node *next;
	public:
	node *top=NULL;
	void push(int val)
	{
	  	node *newnode=new node();
	  	newnode->data=val;
	  	newnode->next=NULL;
	  	if(top==NULL)
	  	  top=newnode;
	  	else
	  	{
	  	  newnode->next=top;
	  	  top=newnode;
		  }
 
}
int pop()
{
	if(isempty())
	
		cout<<"stack is empty. Can't pop....";
	else
	{
	node *temp=top;      
	int x=temp->data;
	top=top->next;
	delete(temp);
	return(x);
    }
}
void display()
{node *temp=top;
while(temp!=NULL)
{
  cout<<temp->data<<" ";
  temp=temp->next;
}
	
}
bool isempty()
{
	if(top==NULL)
	  return true;
	else
	  return false;
}
};
int main()
{
	int choice,val,pop_element;
	node obj;
	do
	{
	
	cout<<"enter ur choice 1-push 2-pop 3-display .......";
	cin>>choice;
	switch(choice)
	{
		case 1: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.push(val);
		        break;
	    case 2: if(!obj.isempty())
	            {
		          pop_element=obj.pop();
	           // if(pop_element!=99999)
	              cout<<"popped element is "<<pop_element;
	            }
	            break;
		case 3: obj.display();
	            break;
	    default: exit(0);
	    
	}
  }while(choice!=4);
}
#SINGLY LINKEDLIST
#include<iostream>
using namespace std;
class node
{
	int data;
	node *next;
	public:
	node *head=NULL;
	void insertbeg(int val)
	{
	  	node *newnode=new node();
	  	newnode->data=val;
	  	newnode->next=NULL;
	  	if(head==NULL)
	  	  head=newnode;
	  	else
	  	{
	  	  newnode->next=head;
	  	  head=newnode;
		  }	  	
   }
   void insertend(int val)
   {
   	node *newnode=new node();
	newnode->data=val;
	newnode->next=NULL;
	if(head==NULL)
	{
	  	  head=newnode;
	  	  return;
    }
    node *temp=head;
    while(temp->next!=NULL)
    { temp=temp->next;
	}
	
	temp->next=newnode;
	
   }
   void deletebeg()
   {
   	node *temp;
   	if(head==NULL)
   	{cout<<" the list is empty. u can't delete";
   	 return;
	 }
   	temp=head;
   	head=head->next;
   	cout<<"the deleted item is "<<temp->data;
   	delete(temp);
   }
   void deleteend()
   {
   	node *prev=NULL, *temp=head;
   	while(temp->next!=NULL)
   	{ prev=temp;
   	  temp=temp->next;
   }
   prev->next=NULL;
   cout<<"the deleted item is "<<temp->data;
   delete(temp);
   }
   
   void display()
   {
   	node *temp=head;
   	while(temp!=NULL)
   	{
   		cout<<temp->data<<" ";
   		temp=temp->next;
	   }
   }
   void insertmiddle(int val)
   {int n;
   	node *newnode=new node();
	newnode->data=val;
	newnode->next=NULL;
	if(head==NULL)
	{
	  	  head=newnode;
	  	  return;
    }
    cout<<"enter the number of nodes after which you want to insert this";
    cin >>n;
    node *temp=head;
    int count=1;
    while(count<n && temp->next!=NULL)
    {
      temp=temp->next;
      count++;
	}
	newnode->next=temp->next;
	temp->next=newnode;
   }
   void deletemiddle()
   {int delval;
   	 node *prev=NULL,*temp=head;
   	 cout<<"enter the node value that u want to delete";
   	 cin>>delval;
   	 while(temp->data!=delval&&temp->next!=NULL)
   	 {
   	 	prev=temp;
   	 	temp=temp->next;
	 }
	 if(temp->data!=delval)
	{cout<<"there is no such node in the list";
	  return;
	}
	 prev->next=temp->next;
	 cout<<"deleted item is "<<temp->data;
	 delete(temp);
   }
};
int main()
{
	int choice,val;
	node obj;
	do
	{
	
	cout<<"enter ur choice 1-insert in the beg 2-insert at the end .......";
	cin>>choice;
	switch(choice)
	{
		case 1: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.insertbeg(val);
		        break;
	    case 2: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.insertend(val);
		        break;
		case 3: cout<<"enter the value u want to insert";
		        cin>>val;
		        obj.insertmiddle(val);
		        break;
	    	    
	    case 4:obj.deletebeg();
	           break;
	    case 5:obj.deleteend();
	           break;
	    case 6: obj.deletemiddle();
	            break;
	    case 7: obj.display();
	            break;
	    
	}
  }while(choice!=8);
}

#circular singly linked list with pointer to the first node (c program ) (but pointer to the last node will be more efficient)
//Circular Linked List
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
#include<malloc.h>
struct node
{
  int data;
  struct node *next;
};
struct node *head=NULL;

void f_insert()
{
struct node *newnode,*temp;
newnode=(struct node*)malloc(sizeof(struct node));
printf("enter the element to be inserted\n");
scanf("%d",&newnode->data);
newnode->next = newnode;
if(head==NULL)
{
  head=newnode;
}

else
{
  temp=head;
  newnode->next=head;
  do
  {
    temp=temp->next;
  }while(temp->next!=head);
  temp->next=newnode;
  head=newnode;
}
return;
}
void b_insert()
{

struct node *newnode,*temp;
if(head==NULL)
  f_insert();
else
{
newnode=(struct node*)malloc(sizeof(struct node));
printf("enter the element to be inserted\n");
scanf("%d",&newnode->data);
newnode->next=newnode;
temp=head;
while(temp->next!=head)
{
  temp=temp->next;
}
temp->next=newnode;
newnode->next=head;
}
return;
}
void b_delete()
{
struct node *temp,*prev;
if(head==NULL)
{
 //printf("the list is empty\n");
 return;
}
if(head->next==head)
{
  printf("the deleted node is %d\n",head->data);
  head=NULL;
  return;
}
else
{
 temp=head;
  while(temp->next!=head)
  {
    prev=temp;
    temp=temp->next;
 }
 prev->next=head;
 free(temp);
}
  return;
}

void f_delete()
{
struct node *temp,*last;
last=head;
if(head==NULL)
{
 printf("the list is empty\n");
 return;
}
else if(head->next==head)
{
  printf("the deleted node is %d\n",head->data);
  head=NULL;
  return;
}

else
{
while(last->next!=head)
  last=last->next;
temp=head;
head=head->next;
printf("the deleted node is %d\n",temp->data);
free(temp);
last->next=head;
}
}
void display()
{
  struct node *temp;
  temp=head;
  if(head==NULL)
  {
    printf("the list is empty\n");
    return;
  }
 do
  {
    printf("%d->",temp->data);
    temp=temp->next;
  }while(temp!=head);
  printf("\n");
  return;
}

int main()
{
  int choice;

  do
  {
   printf("do you want to continue\n 1-insert in the front \t");
   printf("2-insert at the back\t3-delete from front");
   printf("4-delete from back\n5-exit\n");
   scanf("%d",&choice);
   switch(choice)
   {
     case 1:
	     f_insert();
	     display();
	     break;
     
     case 2: b_insert();
	     display();
	     break;
     case 3: f_delete();
	     display();
	     break;
     
     case 4: b_delete();
	     display();
	     break;
   }
   }while(choice!=5);
   return 0;
}
