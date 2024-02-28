#include <iostream>
#include <iomanip>
#include <ctime>
#include <cstdlib>

using namespace std;

struct slistEl
{
	slistEl * next;
	int data;
};

class queue
{
	private:
    	slistEl * head;
    	slistEl * tail;

	public:
    	queue( );      
    	~queue( );     
    	bool empty ( );
    	int front ();
    	void enqueue ( int v );
    	void dequeue ( );
    	void print ( );
};

queue::queue( )
{
	head = tail = NULL;
}

queue::~queue( )
{
  	while( head ) dequeue( );
}

bool queue::empty ( void )
{
  	return !head;
}

int queue::front()
{
	//1
	if (head){
return head->data;
}
else{
	return 0;
}
}

void queue::enqueue ( int v )
{
  	slistEl * p;
  	p = new slistEl;
  	p->next = NULL;
  	p->data = v;

  	if( !head ) head = tail = p;
  	else  {
  		//2
		 tail->next=p;
		 tail=p;
  	}
}

void queue::dequeue ( )
{
	slistEl * p;
	p = head;
  	if( head )
  	{
  		//3
		head=head->next;
		if(!head)
		tail = NULL;
  	}
  	delete p;
}

void queue::print()
{
	slistEl * p;
	
	if (head) {
		p = head;
		//4
		while(p){
		cout << p->data << " ";
		p=p->next;
		
	}
	cout << endl;
}
}

int main( )
{
  	queue Q;
  	int i, v;

  	srand ( time ( NULL ) );
  
  	for( i = 1; i <= 10; i++ )
  	{
       	v = rand( ) %  100;
     	Q.enqueue ( v );
  	}
  	
  	Q.print();
  	cout << "Front: " << Q.front() << endl;
  	
  	for( i = 1; i <= 10; i++ ) {
  		Q.dequeue();
  		Q.dequeue();
  		Q.print();  
  		cout << "Front: " << Q.front() << endl;
  		v = rand( ) %  100;
     	Q.enqueue ( v );
  		Q.print();     	
  		cout << "Front: " << Q.front() << endl;
	}
	
	Q.dequeue();
  	Q.print();
	cout << "Front: " << Q.front() << endl;	

} 
