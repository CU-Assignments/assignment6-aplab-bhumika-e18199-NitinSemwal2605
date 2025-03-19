```
class MyQueue {
private:
    stack<int> inputStack;
    stack<int> outputStack;

public:
    MyQueue() {
    }
    
    // put the value directly to inputstack !!
    void push(int x) {
        inputStack.push(x); 
    }
    
    int pop() {
        // if output is empty
        if (outputStack.empty()) {
            // input ko khali kardo output mai
            while (!inputStack.empty()) {
                outputStack.push(inputStack.top());
                inputStack.pop();
            }
        }
        // output.pop
        int front = outputStack.top();
        outputStack.pop();
        return front;
    }
    
    int peek() {
        // if output is empty
        if (outputStack.empty()) {
            // input khali karo output mai and output.top return !!
            while (!inputStack.empty()) {
                outputStack.push(inputStack.top());
                inputStack.pop();
            }
        }
        return outputStack.top();
    }
    
    // empty check for both
    bool empty() {
        return inputStack.empty() && outputStack.empty();
    }
}; 
```


![image](https://github.com/user-attachments/assets/6be76c38-4cea-4788-9a0a-9cbba61d2471)
