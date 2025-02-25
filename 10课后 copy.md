根据提供的上下文，以下是各个问题的标准答案：

### 循环控制关键字
1. **使用哪个关键字可以直接跳到下一个循环？**
   - **A. continue**

2. **使用哪个关键字可以跳出当前循环？**
   - **B. break**

### 合约构造函数
1. **一个合约可以定义多个构造函数（constructor）：**
   - **B. 错误**  
     一个合约只能定义一个构造函数。

2. **构造函数的运行，只能通过手动调用：**
   - **B. 错误**  
     构造函数在合约部署时自动调用。

3. **构造函数是否可以用来初始化合约参数？**
   - **A. 是**

4. **合约的构造函数，可以定义多个：**
   - **B. 错误**  
     一个合约只能定义一个构造函数。

5. **阅读图中代码，非owner地址是否可以调用函数F？**
   - **B. 否**  
     函数 `F` 使用了 `onlyOwner` 修饰符，只有合约的所有者才能调用该函数。

### 事件
1. **下列关于事件的说法中，错误的是**
   - **C. 链上存储数据比存储事件的成本低。**  
     实际上，存储事件的成本通常低于存储数据。

2. **可以使用emit关键字来释放一个事件**
   - **A. 正确**

3. **每个事件可以有无限个带indexed的变量**
   - **B. 错误**  
     一个事件最多可以有3个带 `indexed` 的变量。

4. **indexed关键字可以修饰任意类型的变量**
   - **B. 错误**  
     `indexed` 关键字只能修饰 `uint`, `int`, `address`, `bytes32` 类型的变量。

5. **下列可以查询事件的是**
   - **A. Etherscan**  
   - **B. Remix**  
   - **D. Nansen**

### 继承
1. **对virtual关键字描述正确的是：**
   - **A. 父合约中的函数，如果希望子合约重写，需要加上该关键字。**

2. **对override关键字描述正确的是：**
   - **B. 子合约中重写了父合约中的函数，需要加上该关键字。**

3. **下面哪个选项表示A合约继承了B合约：**
   - **B. contract A is B**

4. **function a() public override{} 意思是**
   - **B. 函数a()重写了父合约中的同名函数**

5. **如果合约B继承了合约A，合约C要继承A和B，要怎么写？**
   - **A. contract C is A, B**

6. **合约B继承了合约A，下面选项中，正确调用父合约构造函数的是：**
   - **C. constructor(uint _num) A(_num){}**

7. **合约B继承了合约A，两个合约都有pop()函数，下面选项中，正确调用父合约函数的是：**
   - **C. 都正确**

### 抽象合约和接口
1. **已知foo是一个未实现的函数，那么下面代码中书写正确的是？**
   - **A. abstract contract A{ function foo(uint a) internal pure virtual returns(uint); }**

2. **被标记为abstract的合约能否被部署？**
   - **B. 不能**

3. **下列关于接口的规则中，错误的是**
   - **E. 继承接口的合约可以不实现接口定义的全部功能**

4. **下列关于接口的描述，错误的是**
   - **E. 如果已知一个合约实现了IERC20接口，那么还需要知道它具体代码实现，才可以与之交互**

5. **已知Azuki的合约地址为0xED5AF388653567Af2F388E6224dC7C4b3241C544，那么利用该地址创建接口合约变量的语句是**
   - **A. IERC721 Azuki = IERC721(0xED5AF388653567Af2F388E6224dC7C4b3241C544)**

6. **已知Azuki合约中存在ownerOf(uint256 tokenId)函数可用来查询某一NFT的拥有者，现在vitalik想利用上文中创建的接口合约变量调用这一函数，并写出了如下代码：**
   - **A. return Azuki.ownerOf(id);**

7. **已知Azuki合约中存在approve(address to, uint256 tokenId)函数可以让NFT的拥有者将自己某一NFT的许可权授予另一地址，且该函数没有返回值，现在某个Azuki拥有者想利用上文中创建的接口合约变量调用这一函数 ，那么他写出的代码可能是？**
   - **A. function approveAzuki(address to, uint256 id) external{ Azuki.approve(to, id);}**

### 排序算法
1. **用Solidity手写插入排序代码**
   ```solidity
   function insertionSort(uint[] memory arr) public pure returns (uint[] memory) {
       for (uint i = 1; i < arr.length; i++) {
           uint key = arr[i];
           int j = int(i) - 1;
           while (j >= 0 && arr[uint(j)] > key) {
               arr[uint(j + 1)] = arr[uint(j)];
               j--;
           }
           arr[uint(j + 1)] = key;
       }
       return arr;
   }
   ```

2. **用Solidity手写冒泡排序代码**
   ```solidity
   function bubbleSort(uint[] memory arr) public pure returns (uint[] memory) {
       bool swapped;
       for (uint i = 0; i < arr.length - 1; i++) {
           swapped = false;
           for (uint j = 0; j < arr.length - i - 1; j++) {
               if (arr[j] > arr[j + 1]) {
                   uint temp = arr[j];
                   arr[j] = arr[j + 1];
                   arr[j + 1] = temp;
                   swapped = true;
               }
           }
           if (!swapped) break;
       }
       return arr;
   }
   ```