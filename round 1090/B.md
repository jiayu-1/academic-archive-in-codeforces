题干：
<img width="805" height="120" alt="image" src="https://github.com/user-attachments/assets/c75a2bb5-63a7-4b9a-9c66-675e1d18cb89" />
<img width="787" height="74" alt="image" src="https://github.com/user-attachments/assets/ce0a53e1-07ae-4729-9755-3b3fa8c5318a" />
<img width="688" height="86" alt="image" src="https://github.com/user-attachments/assets/09eb3924-196a-4376-b1d2-4a785e2030cf" />
<img width="762" height="162" alt="image" src="https://github.com/user-attachments/assets/6d4b155d-3af8-4112-a77f-dd32b9a4df22" />



Core ：将已知进行变换，只不过“变换”，指最基础的多项式加括号方法，so，level高的题目很可能涉及含数学公式的变换
<img width="775" height="181" alt="image" src="https://github.com/user-attachments/assets/295c5ed6-5256-4989-85ee-b759c42fb658" />

思路：模拟，即用代码实现以上公式的计算
--> 公式变换一下，是否可简化代码的实现过程？

-(sum_sub-mx)=-(sum-mx-mx)=2*mx-sum   因为我们知道sum还是很好算的，整体维护一个sum，同时找一个mx，很方便；如果选择原始公式，sub_sum还需要另外寻找每次的min值放入

所以目前发现，本质两点：
优化题中的数学公式 / 变换题中给的思路  +   优化代码（通过使用一些常见的算法模板）
