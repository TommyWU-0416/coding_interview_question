# 這邊專門收集應用的 pattern，包含基礎以及進階題目說明

## [Fast And Slow](src/fastandslowpointer)

## [Next Greater Element](src/nextgreaterelement)

## [Prefix Sum](src/prefixsum)

- 從左往右加總
- 從右往左加總

## [Sliding Window](src/slidewindow)

## [Two Pointer](src/twopointer)

## [Dynamic Programming](src/dynamicprogramming)

### 第二章. 動態規劃的基本實現([例子 - Fibonacci.java](src/dynamicprogramming/onedim/Fibonacci.java))

    1. ###### 備忘錄（Memoization）- function: fib_memo(int n)

> 動態規劃問題通常可以使用遞歸來解決，但遞歸容易產生重複計算，遞歸與備忘錄示例：斐波那契數列

   ```java
   /**
 * 每一個 f(n) = f(n-1) + f(n-2)，若要計算 f(4) 就會重複計算 f(2)兩次，當然算越高的就會重複越多次
 * f(0) = 0
 * f(1) = 1
 * f(2) = f(1) + f(0) = 1
 * f(3) = f(2) + f(1) = 2
 * f(4) = f(3)        + f(2) = 3
 * ____ = f(2) + f(1) + f(2) = 3
 */
   ```

    - 備忘錄是一種技術，用來儲存已經計算過的結果，避免重複計算，從而提高效率。
    - 使用備忘錄後可以把每一次的子問題記錄下來，提供日後查詢，就以計算 fib(10)，使用 memo 前為 177次呼叫fib(), 使用 memo 後僅為 19次

    2. ###### 自底向上（Bottom-Up）方法 - function: fib_memo(int n)

> 就是把最小的子問題依序向上解開來，並且使用 for 或 while 取代 遞迴的呼叫，效率會更好，時間複雜度和空間複雜度都是 O(n)。

#### 練習題

1. 斐波那契數列 LeetCode 509 - Fibonacci Number
    1. 使用遞歸、備忘錄和自底向上方法來實現。
2. 爬樓梯 LeetCode 70 - Climbing Stairs
    1. 每次你可以爬1階或2階，問有多少種不同的方法爬到樓頂。
3. 令牌求和 LeetCode 198 - House Robber
    1. 你不能偷連續的房子，問在一定的排列中可以偷到的最大金額。
4. 最大子序和 LeetCode 53 - Maximum Subarray
    1. 找出具有最大和的連續子數組（至少包含一個數字）。

- 建議的練習順序
    - LeetCode 509 - Fibonacci Number
    - LeetCode 70 - Climbing Stairs
    - LeetCode 198 - House Robber
    - LeetCode 53 - Maximum Subarray

### 第三章. 經典問題解析

#### 3.1 背包問題（0/1 Knapsack Problem）

> 問題描述：給定一組物品，每個物品都有重量和價值，還有一個最大承重的背包，問如何選擇物品使得裝入背包中的總價值最大。

- 輸入：
    - weights：物品的重量列表。
    - values：物品的價值列表。
    - W：背包的最大承重。
- 輸出：
    - 能夠裝入背包的最大價值。
- 練習 [Knapsack.java](src/dynamicprogramming/twodim/Knapsack.java)

#### 3.2 最長公共子序列（Longest Common Subsequence, LCS）

> 問題描述：給定兩個字符串，找出它們的最長公共子序列的長度。

- 輸入：
    - text1：第一個字符串。
    - text2：第二個字符串。
- 輸出：
    - 最長公共子序列的長度。
- 練習 [Longest_Common_Subsequence_1143.java](../leetcode/blind75/dp/multidim/Longest_Common_Subsequence_1143.java)

#### 3.3 編輯距離（Edit Distance）

> 問題描述：給定兩個字符串，計算將一個字符串轉換為另一個字符串所需的最少編輯操作次數，操作包括插入、刪除和替換字符。

- 輸入：
    - word1：第一個字符串。
    - word2：第二個字符串。
- 輸出：
    - 最少編輯操作次數，即將 `word1` 轉換為 `word2` 的最短編輯距離。
- 練習 [EditDistance_72.java](../leetcode/blind75/dp/multidim/EditDistance_72.java)

#### 3.4 不同路徑（Unique Paths）

> 問題描述：一個機器人位於 m * n 網格左上角(0, 0)，每次只能動一步，向下或向右，最終要達到終點(m - 1, n - 1)也就是右下角的位置，問總共有多少條不同路徑

- 輸入：
    - m:row 數量。
    - n:col 數量。
- 輸出：
    - 不同路徑的總數
- 練習 [Unique_Paths_62.java](../leetcode/blind75/dp/multidim/Unique_Paths_62.java)

#### 3.5 帶手續費的股票交易最佳時機（Best Time to Buy and Sell Stock with Transaction Fee）

> 問題描述：給定一個數組 prices，它的第 i 個元素表示一支給定股票第 i 天的價格。 一個整型 fee 代表了交易中的手續費。在每一天，你可以進行以下三種操作之一：買入股票、賣出股票或休息。你可以在買入股票之前賣出股票，但你必須支付每筆交易的手續費。求你能獲得的最大利潤。

- 輸入：
    - prices：股票價格數組。
    - fee：交易手續費。
- 輸出：
    - 最大利潤。
- 練習

## Bit Manipulation

> 對位元的運算進行練習，優化算法

### 第一章: 基本概念

#### 1. 二進制表示

##### (1) 二進制數的表示方法

##### (2) 負數的二進制表示（補碼）

#### 2. 基本操作

- AND (&)
- OR (|)
- XOR (^)
- NOT (~)
- 左移 (<<)
- 右移 (>>, >>>)

(1) 奇數偶數判斷
> 如果都是奇數，再跟 0001 去做 & 的時候，因為奇數尾數一定有1 所以 & 後 == 1 表示奇數

- 練習 [判斷奇數偶數 FindOddOrEven.java](src/bitmanipulation/FindOddOrEven.java)

(2) 尋找數字內涵蓋的 1 的數量(AND 右移)

- 練習 [CountBits.java](src/bitmanipulation/CountBits.java)

(3) 在一個陣列中，數字會出現至多兩次，找出僅出現一次的數字。(XOR)
> 相同的值在經過 XOR 會變成 0

- 練習 [Single_Number_136.java](../leetcode/blind75/bitmanipulation/Single_Number_136.java)

(4) 檢查 a 的第 i 位是否為 1 的方法

- 練習 [test2 寫法內 - Minimum_Flips_To_Make_A_OR_B_Equal_To_C_1318.java](../leetcode/blind75/bitmanipulation/Minimum_Flips_To_Make_A_OR_B_Equal_To_C_1318.java)

### 第二章: 進階操作

#### 1. 設置位元

- 設置第 k 位為 1 - [SetKthBit.java](src/bitmanipulation/setbit/SetKthBit.java)
- 清除第 k 位（設置為 0）- [ClearKthBit.java](src/bitmanipulation/setbit/ClearKthBit.java)
- 切換第 k 位（0 變 1，1 變 0 - [ToggleKthBit.java](src/bitmanipulation/setbit/ToggleKthBit.java)

#### 2. 檢查位元

- 檢查第 k 位是否為 1 - [CheckKthBit.java](src/bitmanipulation/checkbit/CheckKthBit.java)
- 計算 1 的數量（Hamming Weight） - [HammingWeight.java](src/bitmanipulation/checkbit/HammingWeight.java)

#### 3. 移位操作

- 將所有位元左移或右移 n 位。使用 >> 或 << 就可以達到故先不用練習
- 循環移位 - [LeftRotate.java](src/bitmanipulation/rotatebit/LeftRotate.java)

#### 4. 掩碼操作

> 掩碼: 用於選擇或修改某些特定位元的工具

- 創建並應用掩碼 - [ApplyMask.java](src/bitmanipulation/ApplyMask.java)

#### 5. 壓縮與排序
 - 將左區間(int)與右區間(int)壓縮到long的後32位元與前32位元，並進行排序。[Minimum_Number_Of_Arrows_To_Burst_Balloons_452.java](../leetcode/blind75/intervals/Minimum_Number_Of_Arrows_To_Burst_Balloons_452.java)

## Trie

### 第一章: Trie 基礎

#### 1. 概念介紹

- Trie 是什麼？
- 使用情景
- 優勢與劣勢

#### 2. 基礎操作

- 插入 (Insert)
- 搜尋 (Search)
- 刪除 (Delete)

### 第二章: Java 中的 Trie 實作

#### 1. 節點 (Node) 結構

- 定義 TrieNode 類別

#### 2. Trie 結構

- 定義 Trie 類別 - [Trie.java](src/trie/Trie.java)
    - 實作插入操作
    - 實作搜尋操作
    - 實作刪除操作

### 第三章: LeetCode 問題實作

#### 1. 基礎問題
- LeetCode 208: [Implement_Trie_208.java](../leetcode/blind75/src/trie/Implement_Trie_208.java)
- LeetCode 211: [Design_Add_And_Search_Words_Data_Structure_211.java](../leetcode/src/trie/Design_Add_And_Search_Words_Data_Structure_211.java)

#### 2. 進階問題

- LeetCode 212: Word Search II
- LeetCode 648: Replace Words
- LeetCode 676: Implement Magic Dictionary
- LeetCode 677: Map Sum Pairs
- LeetCode 1268: [Search_Suggestions_System_1268.java](../leetcode/blind75/trie/Search_Suggestions_System_1268.java)

### 第四章: Trie 的進階應用

#### 1. 自動補全系統

- 實作一個簡單的自動補全系統

#### 2. 頻率統計

- 在 Trie 中儲存詞頻

## Intervals

### 第一章: 課前準備

Java 語言基礎：熟悉 Java 語言的基本語法和數據結構，如數組、列表和映射。
基礎演算法知識：了解基本排序演算法（如快速排序、合併排序）。

### 第二章: 課程內容

#### (1) 基礎概念

> 在許多問題中，我們需要處理一組區間。每個區間可以表示為一對有序的數 (start, end)，其中 start 是區間的起點，end 是區間的終點。這些區間可以表示一段連續的數字範圍。

```java
// 在 Java 中，我們可以使用 int[] 來表示一個區間：
int[] interval = {start, end};

// 或者使用一個列表來表示多個區間：
List<int[]> intervals = new ArrayList<>();
intervals.add(new int[]{start1, end1});
intervals.add(new int[]{start2, end2});
```

#### (2) 常見問題類型

- 合併間隔
    - LeetCode 56. [Merge_Intervals_56.java](src/intervals/Merge_Intervals_56.java)：給定一組間隔，合併所有重疊的間隔。
    - LeetCode 986. Interval List Intersections：找到兩個間隔列表的交集。

- 插入間隔
    - LeetCode 57. [Insert_Interval_57.java](src/intervals/Insert_Interval_57.java)：在不重疊的間隔列表中插入一個新的間隔，並合併所有可能的重疊間隔。
      覆蓋間隔
    - LeetCode 1288. Remove Covered Intervals：移除覆蓋其他間隔的間隔。
      無重疊間隔
    - LeetCode 435. [Non_overlapping_Intervals_435.java](../leetcode/blind75/intervals/Non_overlapping_Intervals_435.java)：找到使得間隔之間無重疊的最小移除數量。

- 會議室問題
    - LeetCode 252. Meeting Rooms：判斷一個人是否能參加所有會議。
    - LeetCode 253. Meeting Rooms II：計算需要多少個會議室來安排所有會議。

- 區間覆蓋問題
    - LeetCode 1288. Remove Covered Intervals：找到最少的區間以覆蓋區間。

#### (3) 進階問題

- 間隔叢集
    - LeetCode 715. Range Module：設計一個數據結構來高效地處理多個區間操作，如添加區間和查詢區間。
- 最大區間
    - LeetCode 352. Data Stream as Disjoint Intervals：給定一個數據流，動態地保持不重疊的區間列表。

## Monotonic Stack

### 第一章: 基礎介紹與概念

#### 1. Monotonic Stack 基本概念

- 什麼是 Monotonic Stack

> 定義：Monotonic Stack 是一種特殊的棧，其特性是棧內元素保持單調遞增或單調遞減順序。

> 優勢：它在許多問題中能夠幫助我們在常數時間內獲取某些特定的信息，例如下一个更大的元素、下一個更小的元素等。

> 應用場景：處理滑動窗口、區間最大值/最小值問題、雨水收集問題等。

- 為什麼要使用 Monotonic Stack
- 單調遞增棧與單調遞減棧的區別與應用
- 基本操作與實現 - [MonotonicStack.java](src/monotonicstack/MonotonicStack.java)

#### 2. Monotonic Stack 的基本操作（push, pop, peek）

- 使用 Java 實現基本的 Monotonic Stack
- 基礎問題練習
- 練習題
    - LeetCode 496: Next Greater Element I
    - LeetCode 739: Daily Temperatures
    - LeetCode 901: Online Stock Span

### 第二章: 進階應用與實現

#### 1. 進階問題解析

- 深入解析單調棧在處理區間最大值/最小值問題中的應用
- 使用單調棧進行滑動窗口問題的解決
- 進階問題練習
    - LeetCode 84: Largest Rectangle in Histogram
    - LeetCode 85: Maximal Rectangle
    - LeetCode 42: Trapping Rain Water
- 綜合應用。解析和實現一些綜合性更高的問題
    - LeetCode 907: Sum of Subarray Minimums
    - LeetCode 239: Sliding Window Maximum