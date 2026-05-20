题干：

<img width="796" height="157" alt="image" src="https://github.com/user-attachments/assets/65a52b45-d0d2-401d-8ac5-5b1636ed5d06" />
<img width="796" height="187" alt="image" src="https://github.com/user-attachments/assets/25cd3cf4-9849-4036-a7d2-450adaeb4f7b" />

<img width="837" height="763" alt="image" src="https://github.com/user-attachments/assets/37344393-b8c2-445e-b9a1-a87746f1d261" />

🧥：
找出n个数，a1,a2,……,an，使得相邻两项的gcd不重复出现！

gcd，最大公约数，直接BF算gcd必然不可，所以反向 --> 找他们分解之后的数字

假设:
a1 =x *y
a2 =a * b
……
an =c * d
而且素数/质数，是天然的因子，天然地可以充当上述的 x y a b c d
而要求gcd相邻项的结果不同，所以最好的方式是，gcd(a1,a2)的结果，是一个素数，
然后往后取相邻项算gcd，得到的是更大的素数，这样就避免了重复
所以想到：
a1 =x *y
a2 =y * b
所以 gcd(a1,a2)=y
且 x y b都是素数

构造素数的模板如下：
埃拉托斯特尼筛法 模板，常用于快速预处理不超过 limit 的所有素数
在数据范围 ≤ 1e7 时可以

'''
vector<int> primes;//全局
// 生成所有不超过 limit 的素数，存到 primes 中

void init_primes(int limit) {
    vector<bool> is_prime(limit + 1, true);
    is_prime[0] = is_prime[1] = false;
// 0 和 1 不是素数，设为 false
    for (int i = 2; i <= limit; ++i) {
        if (is_prime[i]) {
            primes.push_back(i);
            if (i * 1LL * i <= limit) {
                for (int j = i * i; j <= limit; j += i)
                    is_prime[j] = false;
            }
        }
    }
}
'''

