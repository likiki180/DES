# S_AES小组作业
## 作业报告
###   小组:RNG       
成员：李泽坤、吴科明
#### 第一关：基本测试



用户界面总览：
![image](https://github.com/likiki180/DES/assets/143941355/0b2dc226-e52e-4cd4-ad81-5fedf33ea65a)







我们首先展示用户界面和输入输出不合法的情况。
当输入的信息和密钥内容或者位数不合法时，会重新输入：

![image](https://github.com/likiki180/DES/assets/143941355/8195bee8-20fc-4e86-b4f1-13740b80b866)




![image](https://github.com/likiki180/DES/assets/143941355/0109f098-661a-4c10-8508-ed7270c9df3d)






接下来，我们展示二进制的加解密操作：

输入明文：1010001110110000

输入密钥：0000011010101011



我们得到了下面的加密结果，密文为0011010100111110：

![image](https://github.com/likiki180/DES/assets/143941355/a079a78e-c488-49b1-859d-ecbec9046b0d)





接下来，我们用刚才得到的密文和密钥进行解密：

密文：0011010100111110

密钥：0000011010101011

![image](https://github.com/likiki180/DES/assets/143941355/b7aaf521-bb5f-4632-bb0a-d2fd693ccf37)





解密结果为:1010001110110000

这和我们最开始使用的明文是一致的，至此我们通过了第一关的测试



#### 第二关 交叉测试

本次测试使用内容如下：

输入明文：1010001110110000

输入密钥：0000011010101011





我们程序的二进制明文加密测试：
![image](https://github.com/likiki180/DES/assets/143941355/b41fea8c-e110-49f1-9a9c-175fd0a74b64)




我们程序的ASCII码明文加密测试：

![image](https://github.com/likiki180/DES/assets/143941355/dd5ce16f-fd5a-4bfc-9ec2-7a07c95ad82f)




交叉测试组的两个加密结果：

输入明文：1010001110110000

输入密钥：0000011010101011


该小组的结果如下:

![image](https://github.com/likiki180/DES/assets/143941355/a1f93518-5366-4ada-b4d8-2773fdb71dd9)




可以看出，我们和其他小组的交叉测试结果是一样的， 交叉测试通过！



#### 第三关 拓展功能

我们的作品进行了拓展，加密算法的数据输入可以是ASII编码字符串

对应地输出也可以是ACII字符串(很可能是乱码)。而且我们使用的是web开发，在网页显示中，还纯在部分乱码是不可见的，不可以复制的状态


下图是加密演示：

明文2：RNG

密钥2：0000011010101011

加密结果为: ['0110001011100111', '1110111000011110', '0011111000011001']




![image](https://github.com/likiki180/DES/assets/143941355/33d2c200-f90a-4280-9d77-fa2d732bf000)




面是对应的解密演示：

![image](https://github.com/likiki180/DES/assets/143941355/f670d0ba-e555-4d55-b784-92e3d36a77b3)



解密成功，得到对应的明文，演示结束，第三关通过。

#### 第四关 多重加密

#####4.1 双重加密将S-AES算法通过双重加密进行扩展，分组长度仍然是16 bits，但密钥长度为32 bits

选择对应的双重加密选项：
![image](https://github.com/likiki180/DES/assets/143941355/680e7061-892a-4764-abc2-bb3633e7c725)

按照位数提示要求，输入明文
明文：1001100101100101
密钥：10100011101100000000011010101011
![image](https://github.com/likiki180/DES/assets/143941355/42e6a545-34a9-4c51-b966-1efcd4a8b832)

加密结果，密文1011010000001010：

![image](https://github.com/likiki180/DES/assets/143941355/ce493e9a-4fce-4cb0-b54b-96ac461d48fe)

现在进行解密：
![image](https://github.com/likiki180/DES/assets/143941355/8cb76469-06f2-476c-80e8-0f6faf41d56d)
成功得到刚才的明文

4.1测试通过







#####4.2 中间相遇攻击假设你找到了使用相同密钥的明、密文对(一个或多个)，请尝试使用中间相遇攻击的方法找到正确的密钥Key(K1+K2)
选择对应的中间相遇攻击选项：
![image](https://github.com/likiki180/DES/assets/143941355/935a84cb-c62c-431f-bed7-d3b2eefac80e)

按要求输入我们已知的明文和密文对：

![image](https://github.com/likiki180/DES/assets/143941355/137e0597-a5bb-4c8f-9aa5-f4a3bb20b266)

破解结果:
我们找到了两个密钥
密钥1：01101100101111000110000111101110
密钥2：01100001111011100110110010111100


![image](https://github.com/likiki180/DES/assets/143941355/d23f7c88-452a-44cf-93fa-18e4bfc74bab)






#####4.3 三重加密将S-AES算法通过三重加密进行扩展，我们按照按照32 bits密钥Key(K1+K2)的模式进行三重加密解密


在第4关中，我们尝试使用暴力破解的方法来找到正确的密钥。

对于一份已知的明文密文文对，我们得到了多份密钥的解，并使用单线程与多线程的方式对比破解效率。

在软件界面上选择对应的破解功能：

首先，我们展示单密文对破解功能：

![img_15](https://github.com/likiki180/DES/assets/143941355/aef541c4-48ee-4763-b9c1-336f39f268f4)


进入破解界面：
![img_25](https://github.com/likiki180/DES/assets/143941355/8685192d-ea23-4d0f-8b3a-d5dffbcf1fb8)

输入明文、密文对。

![img_24](https://github.com/likiki180/DES/assets/143941355/da9b1442-15a9-40e8-ac6c-688316418521)


轻松得到破解结果。

![img_23](https://github.com/likiki180/DES/assets/143941355/2b9cb970-ce28-410f-8b64-c372dedf2d8c)


然后，我们展示多密文对破解功能：

![img_28](https://github.com/likiki180/DES/assets/143941355/fe54b5a0-ff6f-44ea-a63c-7b27c359c99b)


输入多组明密文对，注意以英文分号隔开。

![img_27](https://github.com/likiki180/DES/assets/143941355/83da8fad-a917-4ba9-9c4b-2145a75cb39e)


轻松得到破解结果
![img_26](https://github.com/likiki180/DES/assets/143941355/768f9e8b-755e-4da1-a605-16809bf446e4)


第四关测试通过。

#### 第五关：工作模式

基于S-AES算法，使用密码分组链(CBC)模式对较长的明文消息进行加密。
注意初始向量(16 bits) 的生成，并需要加解密双方共享。
在CBC模式下进行加密，并尝试对密文分组进行替换或修改，
然后进行解密，请对比篡改密文前后的解密结果。


### S-DES 加解密系统开发手册

## 1. 概述
本系统采用c/s架构来实现S-AES加解密算法。它支持普通的加解密，ASCII码的加解密，以及多重加密，工作模式等功能。

## 原理介绍

### S-AES算法原理

Simplified Advanced Encryption Standard (S-AES) 是一种简化的 AES（Advanced Encryption Standard）加密算法。它以相对较小的块大小和密钥大小作为特点，用于教育和学习加密算法的基本概念。下面是 S-AES 算法的详细原理：

1. **S-Box 和逆 S-Box**：

   S-AES 使用一个 16 个字节的 S-Box（Substitution Box），以及一个对应的逆 S-Box。S-Box 是一个用于替换字节的固定置换表，它将一个 4 位二进制数替换为另一个 4 位二进制数。逆 S-Box 则是 S-Box 的逆操作。

2. **初始密钥扩展**：

   S-AES 使用一个 16 位的初始密钥，它将在加密和解密中使用。初始密钥通过密钥扩展算法扩展为多个轮次所需的子密钥。扩展密钥的过程包括以下几个步骤：

   - 将 16 位初始密钥分为 8 位的左半部分和右半部分。
   - 使用 S-Box 替换右半部分的每个字节。
   - 将左半部分和右半部分进行循环左移一位。
   - 对左半部分应用按位异或运算（XOR）。

   以上步骤会重复多次，以生成多个子密钥，供加密和解密轮次使用。

3. **加密过程**：

   S-AES 加密过程包括多轮的替代和置换操作。每一轮包括以下步骤：

   - **初始轮密钥添加**：将当前轮次的子密钥与明文进行按位异或（XOR）操作。
   - **S-Box 替代**：将明文经过 S-Box 替代，将每个字节替换为 S-Box 中的对应字节。
   - **行移位**：通过固定的移位规则，对每一行进行字节移位操作。
   - **列混淆**：将每一列进行特定的混淆操作，涉及到有限域上的乘法。
   - **轮密钥添加**：将当前轮次的子密钥再次与处理后的明文进行按位异或（XOR）操作。

   这些步骤将重复多轮，每一轮都使用不同的子密钥，最后一轮不包括列混淆操作。

4. **解密过程**：

   S-AES 解密过程与加密过程相反，它包括多轮的逆操作，包括逆 S-Box 替代、逆行移位、逆列混淆和逆轮密钥添加。这些逆操作使用与加密过程相同的子密钥，但按相反的顺序应用，最终得到明文。

S-AES 的主要目的是教育和理解加密算法的基本原理，它在实际安全性上并不强大，因此不建议在真实的安全应用中使用。它提供了一种学习 AES 的简化方式，帮助理解 AES 加密的内部工作原理。



### 多重加密

双重加密和三重加密是一种数据加密技术，它们通过多次应用相同或不同的加密算法来增强数据的保密性。在S-AES算法的上下文中，双重加密和三重加密扩展了原始的S-AES加密算法，使其适用于更长的密钥，并提供更高级别的数据保护。

#### 双重加密

在双重加密中，S-AES算法使用32位密钥（K1+K2）。这意味着明文首先使用K1进行加密，然后再使用K2进行加密，从而生成密文。在解密时，需要以相反的顺序解密，首先使用K2解密，然后再使用K1解密，以还原原始的明文。

原理如下：

1. 加密过程：
   - 明文 -> K1加密 -> 中间密文 -> K2加密 -> 最终密文

2. 解密过程：
   - 最终密文 -> K2解密 -> 中间密文 -> K1解密 -> 明文

这种双重加密提供了更高的安全性，因为需要两个不同的密钥来解密数据，而且两个加密算法可能是不同的。

#### 三重加密

在三重加密中，S-AES算法可以采用两种模式之一：

1. **按照32位密钥Key(K1+K2)的模式进行三重加密解密：**

   这种模式使用32位密钥，首先使用K1加密，然后使用K2解密，最后再使用K1进行加密，从而生成密文。在解密时，需要以相反的顺序操作，即使用K1解密，然后使用K2加密，最后再使用K1解密以还原原始的明文。

   原理如下：

   1. 加密过程：
      - 明文 -> K1加密 -> 中间密文1 -> K2解密 -> 中间密文2 -> K1加密 -> 最终密文

   2. 解密过程：
      - 最终密文 -> K1解密 -> 中间密文2 -> K2加密 -> 中间密文1 -> K1解密 -> 明文

2. **使用48位密钥(K1+K2+K3)的模式进行三重加解密：**

   这种模式使用48位密钥，其中K1、K2和K3分别用于三个不同的加密/解密轮次。原理类似于32位密钥模式，但增加了一个额外的密钥。

   原理如下：

   1. 加密过程：
      - 明文 -> K1加密 -> 中间密文1 -> K2解密 -> 中间密文2 -> K3加密 -> 最终密文

   2. 解密过程：
      - 最终密文 -> K3解密 -> 中间密文2 -> K2加密 -> 中间密文1 -> K1解密 -> 明文

这些双重和三重加密的原理可以提高数据的安全性，但也增加了计算复杂性。密钥的选择和管理也变得更加复杂，因为需要维护多个密钥。



### 中间相遇攻击

中间相遇攻击（Meet-in-the-Middle Attack）是一种密码分析攻击，通常用于攻击加密算法，尤其是用于双向加密的算法，例如双密钥加密或多轮加密。攻击的目标是找到加密算法的密钥，通常是通过分析已知的明文和密文对来实现的。中间相遇攻击的原理如下：

1. 收集明文-密文对：攻击者需要收集一组已知的明文-密文对，这些对由加密算法生成。这些明文-密文对是攻击的输入。
2. 构建中间结果表：攻击者执行加密操作两次，一次从明文到密文（正向加密），一次从密文到明文（反向解密）。在正向加密和反向解密的过程中，攻击者记录每个步骤的中间结果，这包括某一轮的密钥和状态（state）。这些中间结果形成一个表格或数据结构。
3. 比对中间结果：攻击者通过比对两个中间结果表，寻找相同的中间结果。如果在正向加密和反向解密中找到相同的中间结果，那么这些中间结果将在中间相遇攻击中起到关键作用。
4. 寻找密钥：一旦攻击者找到具有相同中间结果的正向加密和反向解密步骤，他们可以确定密钥的部分值。因为这些中间结果是通过相同的密钥生成的，所以密钥的部分值将是相同的。攻击者继续将这些部分密钥组合，以还原完整的密钥。
5. 解密数据：一旦攻击者还原了密钥，他们可以使用它来解密其他密文，或者加密其他明文，从而绕过加密保护。

需要注意的是，中间相遇攻击的成功取决于几个因素，包括已知的明文-密文对数量，中间结果的存储和比对效率，以及加密算法的复杂性。攻击者需要足够的已知明文-密文对来成功执行这种攻击，而且攻击不适用于所有类型的加密算法。因此，在设计和使用加密算法时，要采取措施来防止中间相遇攻击。



#### 使用步骤：

1. 导入必要的库和类：

   ```
   pythonCopy codefrom saes import SimplifiedAES  # 导入SimplifiedAES类
   import random
   ```

2. 创建 `DoubleSimplifiedAES` 类：

   ```
   pythonCopy codeclass DoubleSimplifiedAES(object):
       # 类的初始化方法和其他方法
   ```

3. 定义生成随机明文的函数 `generate_random_plaintext`：

   ```
   pythonCopy codedef generate_random_plaintext():
       return random.randint(0, 0xFFFFFFFF)
   ```

4. 收集明文-密文对：

   ```
   pythonCopy codeplaintexts = [generate_random_plaintext() for _ in range(1000)]  # 生成1000个随机明文
   double_aes = DoubleSimplifiedAES(0x12345678)  # 创建DoubleSimplifiedAES实例，使用相同密钥
   ciphertexts1 = [double_aes.encrypt(plaintext) for plaintext in plaintexts]  # 第一次加密
   ciphertexts2 = [double_aes.encrypt(plaintext) for plaintext in plaintexts]  # 第二次加密
   ```

5. 编写 `find_key_from_intermediates` 函数来找到中间相遇的位置：

   ```
   pythonCopy codedef find_key_from_intermediates(intermediates1, intermediates2):
       for i in range(len(intermediates1)):
           for j in range(len(intermediates2)):
               if intermediates1[i] == intermediates2[j]:
                   return i, j
       return None
   ```

6. 执行中间相遇攻击，查找相遇的位置：

   ```
   pythonCopy code
   result = find_key_from_intermediates(ciphertexts1, ciphertexts2)  # 查找中间相遇
   ```

7. 如果找到中间相遇，进一步查找密钥：

   ```
   pythonCopy codeif result:
       i, j = result
       key1 = double_aes.aes1.find_key(plaintexts[i], ciphertexts1[i])  # 查找第一个子密钥
       key2 = double_aes.aes2.find_key(plaintexts[j], ciphertexts2[j])  # 查找第二个子密钥
       full_key = (key1 << 16) | key2  # 组合得到完整密钥
       print("找到密钥:", hex(full_key))
   ```

8. 如果未找到中间相遇，输出未找到的信息：

   ```
   pythonCopy codeelse:
       print("未找到中间相遇。")
   ```

这个代码示例使用随机生成的明文-密文对并尝试执行中间相遇攻击来还原密钥。如果成功找到中间相遇，将输出找到的密钥。如果未找到中间相遇，将输出未找到的信息。注意，成功执行中间相遇攻击需要足够的明文-密文对，并且密钥空间不宜过大，否则攻击的复杂性会增加。



### CBC模式

密码分组链（Cipher Block Chaining，CBC）是一种对称加密模式，用于将较长的明文消息分成块并加密。在CBC模式中，每个明文块在加密之前都要与前一个密文块（或初始向量）进行异或运算，以增加数据的随机性和安全性。下面是使用S-AES算法和CBC模式进行加密和解密的原理：

**CBC模式的加密原理：**

1. **明文分组**：首先，将明文消息分成块，每个块的大小与S-AES的块大小相匹配（16 bits）。

2. **初始向量**：生成一个16位的初始向量（IV），初始向量需要由加密和解密双方共享。初始向量通常是随机生成的。

3. **加密过程**：对于每个明文块（除了第一个块），执行以下步骤：
   - 将前一个密文块（或初始向量）与当前明文块进行异或运算。
   - 对异或结果进行S-AES加密。
   - 将加密后的结果作为当前密文块。

4. **最终输出**：所有加密后的密文块将组成最终的密文。

**CBC模式的解密原理：**

1. **初始向量**：接收方需要知道初始向量（IV），以便进行解密。

2. **解密过程**：对于每个密文块，执行以下步骤：
   - 使用S-AES解密当前密文块。
   - 将解密后的结果与前一个密文块进行异或运算。
   - 异或结果即为明文块。

3. **最终输出**：所有解密后的明文块将组成最终的明文。

**篡改密文后的解密结果对比：**

在CBC模式中，如果密文块被篡改或修改，那么解密后的结果也会受到影响。如果攻击者篡改了一个密文块，那么解密时会导致明文块中对应的位置出现错误。这是因为解密是通过前一个密文块来计算当前明文块，任何一个密文块的修改都会传播到后续的明文块中，使其解密结果变得不可预测。

CBC模式的安全性部分依赖于初始向量的随机性，因此初始向量的生成和管理是非常重要的。此外，应该采用完整性验证机制，以检测篡改或修改，并在必要时重新加密或拒绝数据。

## 2. 前端页面设计

### 2.1 主要结构
- **Logo容器**: 显示系统相关的logo。
- **标题**: 显示系统的主标题。
- **选项列表**: 用户可以选择二进制、ASCII或暴力破解。
- **输入部分**: 允许用户输入信息和密钥。
- **信息容器**: 显示开发单位和开发者信息。

### 2.2 样式和交互
- **背景**: 页面背景采用图片，能够自动调整大小以适应不同的屏幕。
- **提示**: 提供清晰的界面和按钮提示用户进行输入。
- **交互**: 选项列表允许用户选择操作类型。选择暴力破解后，系统将跳转到另一页面。
- **界面1的设计**: 下面是本系统的初始界面的html文件。选择暴力破解后，系统将跳转到另一页面。
```html
<!DOCTYPE html>
<html>
<head>
    <style>
                body {
            background-image: url("/static/lan_F.jpg");
            background-size: cover;
            color: white;
            height: 50vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            margin: 0;
            font-size: 3em;
            font-family: Arial, sans-serif;

        }

        .logo-container {
            position: absolute;
            top: 10px;
            left: 10px;
            display: flex;
            align-items: center;
        }
        .logo-container img {
            height: 50px;
            margin-right: 10px;
        }
        .title {

            font-size: 1em;
            margin-bottom:50px;
            margin-top:200px;
        }
.select-container {
    margin: 20px 0; /* 上下边距为20px, 左右边距为0 */
    font-size: 40px; /* 字体大小为16px */
    display: flex; /* 使用flex布局以使label和select在同一行 */
    align-items: center; /* 垂直居中对齐内容 */
}

.select-container label {
    margin-right: 10px; /* 在label和select之间增加10px的间距 */
}

.select-container select {
    padding: 5px 10px; /* 选择框内部的填充：上下5px，左右10px */
    border: 1px solid #cccccc; /* 给选择框一个灰色的边框 */
    border-radius: 4px; /* 边框圆角为4px */
}




        .profile-container img {
            width: 100%;
            height: auto;
        }
        /* New CSS for login form */
                /* 应该是灰框*/
        .login-container {
            display: flex;
            flex-direction: column;
            background: rgba(0, 0, 0, 0.5); /* semi-transparent background */
            padding: 10px;  /* reduce padding */
            border-radius: 5px;
            font-size: 0.5em;

              padding: 20px;  /* 增加内边距 */

              width: 600px;  /* 增加宽度 */
    height: auto;  /* 根据内容自适应高度 */


        }
         /* 这个是输入字体控制 */
        .login-container input {
            margin-bottom: 5px; /* reduce margin */
            padding: 5px; /* reduce padding */
            font-size: 0.8em; /* reduce font-size */
            background: transparent; /* make input box transparent */
            color: white; /* change text color to white */
            border: none; /* remove input box border */
        }
         /* 这个是按钮控制 */
        .login-container button {
            padding: 5px;
            background-color: lightblue;
            color: black;
            border: none;
            cursor: pointer;
            font-size: 0.5em; /* reduce font-size */
             margin-bottom:30px;

        }
        /* New CSS for website information */
                 /* 这个是底部字体 */
        .info-container {
            position: absolute;
            bottom: 0;
            width: 100%;
            text-align: center;
            padding: 10px 0;
            background-color: rgba(0, 0, 0, 0.5); /* semi-transparent background */
            font-size: 0.2em; /* adjust font size */
        }
    </style>
    <script>
        window.onload = function() {
    document.getElementById('login-button').onclick = function() {
        var username = document.getElementById('username-input').value;
        var password = document.getElementById('password-input').value;
        var option = document.getElementById('option-list').value; // 获取当前选择的选项

        fetch('/login', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({username: username, password: password, operation: "encryption", option: option})
        }).then(response => response.json())
          .then(data => alert(data.message));
    }
   // 添加事件监听器检测选择的变化
            document.getElementById('option-list').addEventListener('change', function() {
                if (this.value === "brute_force") {
                    window.location.href = "/brute_force_page"; // 假设新的HTML页面的路由为"/brute_force_page"
                }
            });
    document.getElementById('login-button2').onclick = function() {
        var username = document.getElementById('username-input').value;
        var password = document.getElementById('password-input').value;
        var option = document.getElementById('option-list').value; // 获取当前选择的选项

        fetch('/login', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({username: username, password: password, operation: "decryption", option: option})
        }).then(response => response.json())
          .then(data => alert(data.message));
    }
}



    </script>
</head>
<body>
    <div class="logo-container">
        <img src="/static/logo1.png" alt="Logo 1">

        <img src="/static/logo3.png" alt="Logo 3">
    </div>
    <div class="title">
        S-DES加解密系统
    </div>

       <!-- 选项列表部分 -->
    <div class="select-container">
        <label for="option-list">选项：</label>
        <select id="option-list">
            <option value="binary">二进制</option>
            <option value="asciil">ASCLL</option>
             <option value="brute_force">暴力破解</option>
        </select>
    </div>


          <!-- 文本部分 -->
    <div class="login-container">
        <input id="username-input" type="text" placeholder="信息" required/>
<!--        <input id="password-input" type="password" placeholder="密钥" required/>-->
        <input id="password-input" type="text" placeholder="密钥(10bits)" required/>
        <button id="login-button">加密</button>
        <button id="login-button2">解密</button>


    </div>
    <!-- New website information -->
    <div class="info-container">
        <p>所属单位：重庆大学大数据与软件学院  |   分工小组：RNG</p>
        <p>开发人员：吴科明 李泽坤   |  联系方式：1281673219@qq.com</p>
    </div>
</body>
</html>


```


- **界面2的设计**: 选择暴力破解后，系统将跳转到另一页面。下面是该页面的html文件。

```html
<!DOCTYPE html>
<html>
<head>
    <style>
                body {
            background-image: url("/static/lan_F.jpg");
            background-size: cover;
            color: white;
            height: 50vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            margin: 0;
            font-size: 3em;
            font-family: Arial, sans-serif;

        }

        .logo-container {
            position: absolute;
            top: 10px;
            left: 10px;
            display: flex;
            align-items: center;
        }
        .logo-container img {
            height: 50px;
            margin-right: 10px;
        }
        .title {

            font-size: 1em;
            margin-bottom:50px;
            margin-top:200px;
        }
.select-container {
    margin: 20px 0; /* 上下边距为20px, 左右边距为0 */
    font-size: 40px; /* 字体大小为16px */
    display: flex; /* 使用flex布局以使label和select在同一行 */
    align-items: center; /* 垂直居中对齐内容 */
}

.select-container label {
    margin-right: 10px; /* 在label和select之间增加10px的间距 */
}

.select-container select {
    padding: 5px 10px; /* 选择框内部的填充：上下5px，左右10px */
    border: 1px solid #cccccc; /* 给选择框一个灰色的边框 */
    border-radius: 4px; /* 边框圆角为4px */
}




        .profile-container img {
            width: 100%;
            height: auto;
        }
        /* New CSS for login form */
                /* 应该是灰框*/
        .login-container {
            display: flex;
            flex-direction: column;
            background: rgba(0, 0, 0, 0.5); /* semi-transparent background */
            padding: 10px;  /* reduce padding */
            border-radius: 5px;
            font-size: 0.5em;

              padding: 20px;  /* 增加内边距 */

              width: 600px;  /* 增加宽度 */
    height: auto;  /* 根据内容自适应高度 */


        }
         /* 这个是输入字体控制 */
        .login-container input {
            margin-bottom: 5px; /* reduce margin */
            padding: 5px; /* reduce padding */
            font-size: 0.8em; /* reduce font-size */
            background: transparent; /* make input box transparent */
            color: white; /* change text color to white */
            border: none; /* remove input box border */
        }
         /* 这个是按钮控制 */
        .login-container button {
            padding: 5px;
            background-color: lightblue;
            color: black;
            border: none;
            cursor: pointer;
            font-size: 0.5em; /* reduce font-size */
             margin-bottom:30px;

        }
        /* New CSS for website information */
                 /* 这个是底部字体 */
        .info-container {
            position: absolute;
            bottom: 0;
            width: 100%;
            text-align: center;
            padding: 10px 0;
            background-color: rgba(0, 0, 0, 0.5); /* semi-transparent background */
            font-size: 0.2em; /* adjust font size */
        }
    </style>
    <script>

        window.onload = function() {


    document.getElementById('login-button').onclick = function() {
        var username = document.getElementById('username-input').value;
        var password = document.getElementById('password-input').value;

        fetch('/brute_force', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({username: username, password: password})
        }).then(response => response.json())
          .then(data => alert(data.message));
    }
}


    </script>
</head>
<body>
    <div class="logo-container">
        <img src="/static/logo1.png" alt="Logo 1">

        <img src="/static/logo3.png" alt="Logo 3">
    </div>
    <div class="title">
        S-DES加解密暴力破解系统
    </div>




          <!-- 文本部分 -->
    <div class="login-container">
        <input id="username-input" type="text" placeholder="明文" required/>
<!--        <input id="password-input" type="password" placeholder="密钥" required/>-->
        <input id="password-input" type="text" placeholder="密文" required/>
        <button id="login-button">开始破解</button>



    </div>
    <!-- New website information -->
    <div class="info-container">
        <p>所属单位：重庆大学大数据与软件学院  |   分工小组：RNG</p>
        <p>开发人员：吴科明 李泽坤   |  联系方式：1281673219@qq.com</p>
    </div>
</body>
</html>


```
## 3. 加解密算法

### 3.1 辅助函数

- **`permute(input_str, permutation_table)`**: 

- 根据给定的置换表来进行置换。
```python
def permute(input_str, permutation_table):
    output_str = ''
    for bit_position in permutation_table:
        output_str += input_str[bit_position - 1]
    return output_str


```
- **`left_shift(key, n)`**: 将输入字符串的左半部分和右半部分分别左移`n`位。
```python
def left_shift(key, n):
    left_half = key[:5]
    right_half = key[5:]
    shifted_left = left_half[n:] + left_half[:n]
    shifted_right = right_half[n:] + right_half[:n]
    return shifted_left + shifted_right

```
- **`generate_subkeys(key, p10_table, p8_table)`**: 根据给定的P10和P8表生成子密钥。
```python

def generate_subkeys(key, p10_table, p8_table):
    p10_key = permute(key, p10_table)
    key1 = permute(left_shift(p10_key, 1), p8_table)
    key2 = permute(left_shift(left_shift(p10_key, 1), 1), p8_table)
    return key1, key2

```
- **`f_function(right_half, subkey, sbox0, sbox1, p4_table)`**: 进行S-DES的F函数操作。
```python

def f_function(right_half, subkey, sbox0, sbox1, p4_table):
    # Expansion and XOR
    expanded = permute(right_half, EXPANSION_PERMUTATION)
    xored = int(expanded, 2) ^ int(subkey, 2)
    xored_str = format(xored, '08b')

    # S-box substitutions
    s0_input = xored_str[:4]
    s1_input = xored_str[4:]
    s0_row = int(s0_input[0] + s0_input[3], 2)
    s0_col = int(s0_input[1:3], 2)
    s1_row = int(s1_input[0] + s1_input[3], 2)
    s1_col = int(s1_input[1:3], 2)
    s0_output = format(sbox0[s0_row][s0_col], '02b')
    s1_output = format(sbox1[s1_row][s1_col], '02b')
    s_output = s0_output + s1_output

    # Permutation
    return permute(s_output, p4_table)

```
- **`ascii_to_binary(ascii_string)`**: 将ASCII字符串转换为二进制。
```python

def ascii_to_binary(ascii_string):
    binary_string = ""
    for character in ascii_string:
        binary_string += bin(ord(character))[2:].zfill(8)
    return binary_string

```
- **`binary_to_ascii(binary_string)`**: 将二进制转换为ASCII字符串。

```python
def binary_to_ascii(binary_string):
    ascii_string = ""
    for i in range(0, len(binary_string), 8):
        ascii_string += chr(int(binary_string[i:i + 8], 2))
    return ascii_string

```

### 3.2 加密
**`encrypt(plaintext, key)`**: 使用给定的密钥对明文进行S-DES加密。

```python
def encrypt(plaintext, key):
    key1, key2 = generate_subkeys(key, PERMUTATION_P10, PERMUTATION_P8)
    plaintext = permute(plaintext, INITIAL_PERMUTATION)
    left_half = plaintext[:4]
    right_half = plaintext[4:]
    left_previous = right_half
    f_result = f_function(right_half, key1, SBOX0, SBOX1, PERMUTATION_P4)
    right_half1_int = int(left_half, 2) ^ int(f_result, 2)
    right_half1 = format(right_half1_int, '04b')
    f_result = f_function(right_half1, key2, SBOX0, SBOX1, PERMUTATION_P4)
    right_half2_int = int(left_previous, 2) ^ int(f_result, 2)
    right_half2 = format(right_half2_int, '04b')
    return permute(right_half2 + right_half1, INVERSE_INITIAL_PERMUTATION)


```

### 3.3 解密
**`decrypt(ciphertext, key)`**: 使用给定的密钥对密文进行S-DES解密。

```python
def decrypt(ciphertext, key):
    key1, key2 = generate_subkeys(key, PERMUTATION_P10, PERMUTATION_P8)
    ciphertext = permute(ciphertext, INITIAL_PERMUTATION)
    right_previous = ciphertext[:4]
    left_previous = ciphertext[4:]
    f_result = f_function(left_previous, key2, SBOX0, SBOX1, PERMUTATION_P4)
    left_half1_int = int(right_previous, 2) ^ int(f_result, 2)
    left_half1 = format(left_half1_int, '04b')
    f_result = f_function(left_half1, key1, SBOX0, SBOX1, PERMUTATION_P4)
    right_half1_int = int(left_previous, 2) ^ int(f_result, 2)
    right_half1 = format(right_half1_int, '04b')
    return permute(right_half1 + left_half1, INVERSE_INITIAL_PERMUTATION)

```

### 3.4 字符串加解密
**`encrypt_string(ascii_string, key)`**: 对ASCII字符串进行加密。

```python
def encrypt_string(ascii_string, key):
    binary_string = ascii_to_binary(ascii_string)
    encrypted_string = ""
    for i in range(0, len(binary_string), 8):
        plaintext = binary_string[i:i + 8]
        ciphertext = encrypt(plaintext, key)
        encrypted_string += ciphertext
    return encrypted_string


```
**`decrypt_string(encrypted_string, key)`**: 对已加密的字符串进行解密。

```python
def decrypt_string(encrypted_string, key):
    decrypted_string = ""
    for i in range(0, len(encrypted_string), 8):
        ciphertext = encrypted_string[i:i + 8]
        plaintext = decrypt(ciphertext, key)
        decrypted_string += plaintext
    return decrypted_string

```


## 4. 暴力破解
**`BruteForceDecrypt`类**: 提供了单线程和多线程的暴力破解方法。

- **`_brute_force(self, plaintext, ciphertext, start, end)`**: 单线程暴力破解方法，从start到end范围内尝试所有的密钥。

```python

class BruteForceDecrypt:

    def __init__(self):
        self.correct_keys = []
        self.lock = threading.Lock()

    def _brute_force(self, plaintext, ciphertext, start, end):
        for key in range(start, end):
            key_str = '{0:010b}'.format(key)
            decrypted = decrypt(ciphertext, key_str)
            if decrypted == plaintext and len(key_str) == 10:
                with self.lock:
                    self.correct_keys.append(key_str)

    def single_thread_brute_force(self, plaintext, ciphertext):
        self._brute_force(plaintext, ciphertext, 0, 2 ** 10)
        return self.correct_keys

    def multi_thread_brute_force(self, plaintext, ciphertext):
        threads = []
        for i in range(8):
            start = i * (2 ** 9)
            end = (i + 1) * (2 ** 9)
            thread = threading.Thread(target=self._brute_force, args=(plaintext, ciphertext, start, end))
            thread.start()
            threads.append(thread)
        for thread in threads:
            thread.join()
        return self.correct_keys

    def decrypt(self, plaintext, ciphertext):
        start_time = time.time()
        single_result = self.single_thread_brute_force(plaintext, ciphertext)
        single_time = time.time() - start_time
        self.correct_keys.clear()
        start_time = time.time()
        multi_result = self.multi_thread_brute_force(plaintext, ciphertext)
        multi_time = time.time() - start_time
        return {
            "single_thread": {
                "keys": single_result,
                "time": single_time
            },
            "multi_thread": {
                "keys": multi_result,
                "time": multi_time
            }
        }


```



- **`multi_thread_brute_force(self, plaintext, ciphertext)`**: 多线程暴力破解接口，使用8个线程进行破解。

```python
def multi_thread_brute_force(plaintext, ciphertext):
    threads = []
    for i in range(8):
        start = i * (2 ** 9)
        end = (i + 1) * (2 ** 9)
        thread = threading.Thread(target=brute_force, args=(plaintext, ciphertext, start, end))
        thread.start()
        threads.append(thread)
    # 等待所有线程完成
    for thread in threads:
        thread.join()
```





## 5. 使用指南

### 5.1 S-DES算法介绍

S-DES（Simplified Data Encryption Standard）是一个供教学而非安全使用的加密算法。它与DES的特性和结构类似，但参数小，明文分组为8位，主密钥分组为10位，采用两轮迭代。

S-DES加密过程包含两个重要部分：子密码生成过程和f函数结构。

子密码生成过程：
- 对初始密钥进行P10置换，将置换后的结果分为左右两部分，各5位。
- 对左右两部分进行循环左移操作和P8置换，得到K1。
- 再次对上一步结果进行循环左移操作和P8置换，得到K2。

f函数结构：
- 对右半部分进行E/P扩展置换，将其扩展为8位。
- 对扩展后的结果与轮密钥进行异或运算，再将异或的结果拆分成2个4位的块。
- 将这2个块分别通过S盒代替（S0和S1），然后再进行P4置换，最后将P4置换后的结果与左半部分进行异或，得到F函数输出的结果。

### 5.2 使用步骤

1. 打开S-DES加解密系统主页。
2. 选择所需的操作类型：二进制、ASCII或暴力破解。
3. 输入信息和10位的密钥。如果输入不合法会报错。
4. 点击“加密”或“解密”按钮以进行相应操作。
5. 若选择了暴力破解，则系统会尝试所有可能的密钥，直到找到正确的密钥为止。这个过程可能需要一些时间，具体取决于你的计算机性能和你选择的明文和密文对的数量，并在完成后查看找到的正确密钥。
6. 如果你选择了ASCII模式，那么你输入的信息应该是一个ASCII编码的字符串，而输出也将是一个ASCII编码的字符串。请注意，由于S-DES算法会对数据进行各种复杂的变换，所以加密后得到的字符串可能包含一些无法打印或无法显示的字符（即所谓的"乱码"）。但这并不影响解密过程。只要知道正确的密钥，就可以使用S-DES算法将这个"乱码"字符串解密回原始字符串。

## 6. 联系信息
若有任何疑问或建议，请联系开发团队：1281673219@qq.com

## 7. 其他
我们的系统支持浏览器**在线使用**，如果你有需求，请你联系开发团队开启服务器。









