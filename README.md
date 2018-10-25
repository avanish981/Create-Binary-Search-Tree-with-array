## Create-Binary-Search-Tree-with-array
#include<iostream>
#include<bits/stdc++.h>
#include<algorithm>
using namespace std;
#define ll long long 
#define size 1000
ll create_bst(ll b[],ll data,ll ind,ll c,ll d)
{
    if(b[ind]==-1)
    {
        b[ind]=data;
    }
    else{
        if(data<b[ind])
        {
            c++;
            create_bst(b,data,2*ind,c,d);
        }
        else
        {
            d++;
            create_bst(b,data,(2*ind)+1,c,d);
        }
    }
    return max(c,d);
}
ll height(ll b[],ll count,ll ind){
    if(b[ind]==-1)
    return count;
    count++;
    ll h1=height(b,count,2*ind);
    ll h2=height(b,count,(2*ind+1)+1);
    return (h1>h2)?h1:h2;
}
int main()
{
   ll n,c=0,d=0,y;
   cin>>n;
   ll a[n];
   ll b[size];
   for(ll i=1;i<=size;i++)
       b[i]=-1;
   for(ll i=1;i<=n;i++)
      cin>>a[i];
   ll i=1;
   while(i<=n)
   {
    create_bst(b,a[i],1,c,d);
    i++;
    
    }
   // y=height(b,0,1);
    //cout<<y<<endl;
    
 
}
