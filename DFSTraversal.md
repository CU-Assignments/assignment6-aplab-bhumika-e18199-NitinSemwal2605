```
#include<bits/stdc++.h>
using namespace std;

void DFS(vector<int>adj[],int node,vector<bool>&visited,vector<int>&ans){
    visited[node] = true;
    ans.push_back(node);

    for(auto it : adj[node]){
        if(!visited[it]){
            DFS(adj,it,visited,ans);
        }
    }

    return; 
}

vector<int> DFSTraversal(vector<int>adj[],int v){
    vector<int>ans;
    vector<bool>visited(v,false);

    DFS(adj,0,visited,ans);
    return ans;
}


int main(){
    int v,e;
    cin>>v>>e;

    vector<int>adj[v];
    for(int i=0;i<e;i++){
        int x,y;
        cin>>x>>y;
        adj[x].push_back(y);
        adj[y].push_back(x);
    }

    vector<int>ans = DFSTraversal(adj,v);
    for(auto it : ans){
        cout<<it<<" ";
    }
    return 0;
}

```
