题干：
<img width="965" height="507" alt="image" src="https://github.com/user-attachments/assets/1abcfea0-b94a-4cfe-a70a-92909cabebe1" />

<img width="949" height="738" alt="image" src="https://github.com/user-attachments/assets/5b3cb3ac-2697-4425-a9ff-4002cfaf9348" />



🌙：


'''
    int n;cin>>n;
    // if(n==1){
    //     cout<<n<<endl;
    //     return;
    // }  
//不用特殊判断了！以上不接受input的特判会导致shujuinput流被打乱！
//解决方一：发现主分析能处理n=1的情况，所以撤掉特判
//方二：特判里加对于input的读取，保证数据流顺序正确


//数据规模不大，都读下来再处理！别边读边处理！
    
    vector<int>a(n);
    // for(auto &i: a)cin>>i;
//for(元素类型 变量名: 容器)循环体，&i，表示a[i],
    for(int i=0;i<n;i++)cin>>a[i];

    if(is_sorted(a.begin(),a.end()))cout<<n<<endl;
//is_sorted(a.begin(),a.end())
// a.begin() 返回指向第一个元素的迭代器。
// a.end() 返回指向最后一个元素之后位置的迭代器（不指向有效元素）。
// 函数检查区间 [begin, end) 内的元素是否满足 a[i] <= a[i+1]，是则返回 true，否则返回 false。
    else cout<<1<<endl;
'''
