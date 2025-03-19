```
#include <bits/stdc++.h>
using namespace std;


vector<int> BFSTraversal (vector<int> adj[], int v) {
    queue<int> q;
    vector<int> ans;
    vector<int> visited(v, 0);  

    q.push(0);
    visited[0] = 1;

    while (!q.empty()) {
        int node = q.front();  
        q.pop();
        ans.push_back(node);

        for (auto it : adj[node]) {
            if (!visited[it]) {
                q.push(it);
                visited[it] = 1;
            }
        }
    }

    return ans;
}

int main() {
    int v, e;
    cin >> v >> e;

    vector<int> adj[v];  // Array of vectors

    for (int i = 0; i < e; i++) {
        int x, y;
        cin >> x >> y;
        adj[x].push_back(y);
        adj[y].push_back(x);
    }

    vector<int> ans = BFSTraversal(adj, v);

    for (auto it : ans) {
        cout << it << " ";
    }
    return 0;
}
```
