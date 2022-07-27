sm3生日攻击代码说明及运行结果
=======
1、原理
-------

SM3密码杂凑算法是中国国家密码管理局2010年公布的中国商用密码杂凑算法标准，适用于商用密码应用中的数字签名和验证，消息分组长度为512位，摘要值长度为256位。<br>
生日攻击原理：假如随机选择n个人，那么这个n个人中有两个人的生日相同的概率是多少。如果要想概率是100%，那么只需要选择366个人就够了。因为只有365个生日日期。
如果想要概率达到99.9% ，那么只需要70个人就够了。50%的概率只需要23个人。<br>
sm3的输出范围是256位，那么我们的攻击就是找到两个不同的x，y，让f(x)=f(y)。即x和y发生了碰撞。根据概率论的公式，我们想要达到50%的几率，那么需要尝试的次数是:128位。但电脑能力达不到穷举128位，所以本实验破解前面一些位。<br>
2、代码说明
----------
def naivebirth(n)为生日函数，其中n为输入规模，单位为1个字（4位），根据实际情况，将穷举数量定为输入的位数减1，此时可达到较高的成功率<br>
3、运行截图
------
![Alt text]
4、结果总结
------
根据不同位数时间比较上，可看出电脑在20位以内运算较快，且位数越多攻击越慢，且成指数级增长，符合猜想。
