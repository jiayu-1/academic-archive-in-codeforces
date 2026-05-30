题干欣赏：
（……有机会补上截图）


这道题本质：建图
图，节点之间有连边，​连边它可以代表一种操作或者其他意向。
现在通过这道题，发现操作其实能当做图中的边的，​所以它被操作的对象就构成节点，整体建为图
​这是它这个方法的本质就这么简单

而：
“操作能成为图的边，被操作的对象就是节点”
是图论建模的核心思想。



1. 单向 vs 双向
你说得完全正确：
如果操作是互换（swap），就是无向边，两个节点互相可达。
如果操作是单向移动（比如只能把值从 i 移到 2i），就是有向边，可达性就得按有向图的规则来。

本题是交换，所以是无向边。


2. “别的具体的意象”
其实你已经掌握最核心的那个了。补充几个常见的边可以代表什么（都是操作/关系的变体）：

可达性：能从 A 走到 B（比如迷宫、棋盘跳转）

依赖关系：A 必须在 B 之前完成（拓扑排序，有向边）

冲突关系：A 和 B 不能共存（二分图染色）

相似/连接：A 和 B 直接相连（网络、社交图）

但所有这些本质上都是某种“关系”。你抓住“操作=边”已经够用了。


3. 一个重要的隐藏前提（你已经隐含用到了）
操作作用于位置，不是作用于值。

这一点很关键。因为位置是固定的，所以图的结构是静态的，我们可以提前建好。如果操作直接作用于值，那图就变成动态的了，建模会更复杂。

本题里，我们建图建的是位置图，值只是在这个图上被搬来搬去的“乘客”。


4. 可以扩充的一点：连通分量内的任意排列
你说“双向边连通意味着可以任意移动”，这已经很接近了。严格来说，还需要一条性质：

只要图是连通的，且边对应交换操作，就可以通过一系列交换在该分量内实现任意排列。

这在置换群中对应“相邻交换生成整个对称群”。你不需要记住这个定理，但可以保留这个直觉：连通的交换网络里，东西可以随便排序。




'''
#include <bits/stdc++.h>
using namespace std;

// 常用类型别名
using ll = long long;
using pii = pair<int, int>;
using pll = pair<ll, ll>;
using vi = vector<int>;
using vll = vector<ll>;

// 常用宏定义（根据个人习惯选用）
#define all(x) (x).begin(), (x).end()
#define rall(x) (x).rbegin(), (x).rend()
#define sz(x) (int)(x).size()
#define pb push_back
#define eb emplace_back
#define fi first
#define se second
#define rep(i, a, b) for (int i = (a); i < (b); ++i)
#define per(i, a, b) for (int i = (a); i > (b); --i)
#define endl '\n'

// 快速输入输出（解除同步，提高速度）
void fast_io() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    cout.tie(nullptr);
}

// x数值，pos[x]当前位置
// 先判断x在1 or 3的分支里
//之后判断pos[x]所在是否和x所在一致，
//遍历所有的pos[x]，一旦有一个不一致，，break，cout NO
//把思路写出来！想的话容易有bug！
//具体列出如下，
// 家族 1：{1, 2, 4, 8, 16, …}
// 家族 3：{3, 6, 12, 24, …}
// 家族 5：{5, 10, 20, …}
// 家族 7：{7, 14, 28, …}
//（写出来，发现只以1 3为基准，不可能列举出所有的可能，因为题目规则是2i）
//而且都是 2a 形式，而 n*a ,……,2a,a,区别在于 %2 --> 用于判断是否为2的倍数

int base(int i){
   while(i%2==0)i/=2;
   return i;
}

void solve(){
    int n;cin>>n;
//数组边界：开始值，末尾（无论几个数组，每个数组都要查一遍！
    vector<int>pos(n+1);
    for(int i=1;i<=n;i++){
        int x;cin>>x;
        pos[x]=i;
    }
    for(int i=1;i<=n;i++){
        if(base(pos[i])!=base(i)){
            cout<<"NP\n";
            return;
        }
    }
    cout<<"YES\n";

    return;
    
}

int main() {
    fast_io();
    int t;cin>>t;
    while(t--){
        solve();
    }

    return 0;
}

'''
