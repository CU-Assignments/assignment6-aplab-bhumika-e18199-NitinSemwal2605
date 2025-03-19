```
class MinStack {
    stack<pair<int, int>> st;

public:
    void push(int val) {
        int minval;
        if (st.empty()) {
            minval = val;
        } else {
            minval = min(st.top().second, val);
        }
        st.push({val, minval});
    }

    void pop() { st.pop(); }

    int top() { return st.top().first; }

    int getMin() { return st.top().second; }
};


```


![image](https://github.com/user-attachments/assets/1bbf9781-5f27-47d2-97f8-dd83ad663afb)
