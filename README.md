# Queue
#Basic of Queue
#FIFO queue
#queues are a type of container adaptor, specifically designed to operate in a FIFO context (first-in first-out), where elements are inserted #into one end of the container and extracted from the other.

#queues are implemented as containers adaptors, which are classes that use an encapsulated object of a specific container class as its underlying #container, providing a specific set of member functions to access its elements. Elements are pushed into the "back" of the specific container #and popped from its "front".
#Code:


#include <bits/stdc++.h> 
class Queue {
    int *arr;
    int qfront;
    int rear;
    int size;
public:
    Queue() {
        // Implement the Constructor
        size=10001;
        arr=new int[size];
        qfront=0;
        rear=0;
    }

    bool isEmpty() {
        if(qfront==rear)
        {
            return true;
        }
        else{return false;}
    }

    void enqueue(int data) {
        if(rear==size)
        {
            cout<<"Queue is full"<<endl;
        }
        else{
            arr[rear]=data;
            rear++;
        }
    }

    int dequeue() {
       if(qfront==rear)
       {
           return -1;
       }
       else{
           int ans=arr[qfront];
           arr[qfront]=-1;
           qfront++;
           //To free the space
           if(qfront==rear)
           {
               qfront=0;
               rear=0;
           }
           return ans;
       }
       
    }

    int front() {
        if(qfront==rear)
        {
            return -1;
        }
        else{
           int ans=arr[qfront];
           return ans;
        }
    }
};
