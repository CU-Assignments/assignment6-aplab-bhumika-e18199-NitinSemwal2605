```
#include <bits/stdc++.h>
using namespace std;

int main (){
    int vertex, edge; 
    cin >> vertex >> edge;
    vector<vector<bool>> AdjMatrix(vertex, vector<bool>(vertex,false)); 

    int u,v; 
    for(int i=0;i<edge;i++){
        cin >> u >> v;
        AdjMatrix[u][v] = 1;
        AdjMatrix[v][u]= 1;
    }

    for(int i=0;i<vertex;i++){
        for(int j=0;j<vertex;j++){
            cout << AdjMatrix[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
