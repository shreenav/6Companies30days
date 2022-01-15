class Solution{
    public:
    
    void solve(int src, vector<int>& visited, vector<int>& topo, vector<int> adj[]){
	    visited[src] = 1;
	    for(auto i : adj[src]){
	        if(!visited[i]){
	            solve(i,visited,topo,adj);
	        }
	    }
	    topo.push_back(src);
	}
    
    string findOrder(string dict[], int N, int K) {
        //code here
        vector<int>adj[K];
        for(int i=1; i<N; i++){
            string s1 = dict[i-1];
            string s2 = dict[i];
            for(int j=0; j<min(s1.size(),s2.size()); j++){
                if(s1[j] != s2[j]){
                   int u = s1[j] - 'a';
                   int v = s2[j] - 'a';
                   adj[u].push_back(v);
                   break;
                }
            }
        }
        
        vector<int>visited(K,0);
	    vector<int>topo;
	    for(int i=0; i<K; i++){
	        if(!visited[i]){
	            solve(i,visited,topo,adj);
	        }
	    }
	    reverse(topo.begin(),topo.end());
	    string s = "";
	    for(int i=0; i<topo.size(); i++){
	        s+=topo[i] + 'a';
	    }
	    return s;
    }
};
