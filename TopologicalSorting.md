```
#include <bits/stdc++.h>
using namespace std;

void DFS(int node, vector<int> adj[], vector<int>& visited, stack<int>& st){
    visited[node] = 1;
    for(auto it : adj[node]){
        if(!visited[it]){
            DFS(it, adj, visited, st);
        }
    }
    st.push(node);
}

vector<int> TopologicalSort(vector<int> adj[], int n){
    vector<int> visited(n, 0);
    stack<int> st;

    for(int i = 0; i < n; i++){
        if(!visited[i]){
            DFS(i, adj, visited, st);
        }
    }

    vector<int> result;
    while(!st.empty()){
        result.push_back(st.top());
        st.pop();
    }
    return result;
}

int main (){
    int n, m;
    cin >> n >> m;
    vector<int> adj[n]; 

    for (int i = 0; i < m; i++) {
        int u, v;
        cin >> u >> v;
        adj[u].push_back(v);
    }

    vector<int> result = TopologicalSort(adj, n);  
    for (int i = 0; i < result.size(); i++) {
        cout << result[i] << " ";
    }
    cout << endl;
    return 0;
}

```
