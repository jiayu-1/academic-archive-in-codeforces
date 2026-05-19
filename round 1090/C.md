补一下操作限制 ————来自DS老师

<img width="722" height="408" alt="image" src="https://github.com/user-attachments/assets/87303443-2aff-4a68-824c-d819eb26fa0a" />

题干：
<img width="833" height="327" alt="image" src="https://github.com/user-attachments/assets/4bd59ecb-b8ff-4928-993e-3a7db93575ce" />
<img width="806" height="311" alt="image" src="https://github.com/user-attachments/assets/5c69474c-9c9d-4b75-aa12-d82b302413de" />

input & output
<img width="697" height="99" alt="image" src="https://github.com/user-attachments/assets/d49fc50c-e307-45cb-9f9b-1cc6c416c7ee" />
<img width="782" height="112" alt="image" src="https://github.com/user-attachments/assets/46937160-9d1e-40ac-8bef-e9f2eef483b3" />
<img width="831" height="791" alt="image" src="https://github.com/user-attachments/assets/ec031c29-9305-4267-9de1-38f519afed27" />

题干🧥（大衣，大意）：
3n个数，构成一个permutation，即从1-3n这些数字，不重不漏地组成一个数组。现在从里面构造出n对小元组，买一组里三个元素，升序来排，要求尽量使中间的元素大

silk：
遇到permutation，先将其按照数字原本的顺序放置，这个递增、有序的原始序列，有助于后续对于其他思路想出
中间元素尽量大，所以尽选最右侧的数字，但是右侧的3n必不能充当mid，所以选3n-1作为mid；接下来，开始选left，发现右侧大的数字尽量留着作为mid，所以left从左侧的数字里选
所以最终的选法：左侧选一个left，右端mid和mid+1，双指针即可
注意规范写发，变量的倍数规范化写为：3*n

```
int j=1,k=3*n;
for(int i=1;i<=n;i++){
  cout<<j<<' '<<k-1<<' '<<k<<" \n"[i==n];
  j++;
  k-=2;
}
```
