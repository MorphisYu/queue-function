#queue function

MAX_SIZE = 10  # Define the maximum size of the queue
queue = [None] * MAX_SIZE  # Initialize the queue with None values
front = -1  # Initialize front to -1 indicating an empty queue
rear = -1  # Initialize rear to -1 indicating an empty queue

def enqueue(item):
    global front
    global rear
    if rear == MAX_SIZE - 1:
        print("Queue is full. Cannot enqueue.")
        return
    if front == -1:
        front = 0
    rear += 1
    queue[rear] = item
    print(display())

def dequeue():
    global front
    global rear
    if front == -1:
        print("Queue is empty. Cannot dequeue.")
        return None
    item = queue[front]
    if front == rear:
        front = rear = -1
    else:
        front += 1
    return item

def is_empty():
    return front == -1

def size():
    if is_empty():
        return 0
    return rear - front + 1

def peek():
    if is_empty():
        print("Queue is empty. Cannot peek.")
        return None
    return queue[front]

def display():
    dis = []
    #for val in queue:
    for x in range(front, rear+1):
        if queue[x] != None :
            dis.append(queue[x])
    return dis

# Enqueue more elements to demonstrate overflow
enqueue(40)
enqueue(50)
enqueue(60)
enqueue(70)
enqueue(80)
enqueue(90)
