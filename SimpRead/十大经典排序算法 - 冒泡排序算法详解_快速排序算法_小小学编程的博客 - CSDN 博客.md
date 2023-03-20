> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/qq_35344198/article/details/106437639)

##### 十大经典[排序算法](https://so.csdn.net/so/search?q=%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95&spm=1001.2101.3001.7020)

*   [十大经典排序算法 - 冒泡排序算法详解](https://blog.csdn.net/qq_35344198/article/details/106437639)
*   [十大经典排序算法 - 选择排序算法详解](https://blog.csdn.net/qq_35344198/article/details/106471672)
*   [十大经典排序算法 - 插入排序算法详解](https://blog.csdn.net/qq_35344198/article/details/106546399)
*   [十大经典排序算法 - 希尔排序算法详解](https://blog.csdn.net/qq_35344198/article/details/106665126)
*   [十大经典排序算法 - 快速排序算法详解](https://blog.csdn.net/qq_35344198/article/details/106785849)
*   [十大经典排序算法 - 归并排序算法详解](https://blog.csdn.net/qq_35344198/article/details/106857042)
*   [十大经典排序算法 - 堆排序算法详解](https://blog.csdn.net/qq_35344198/article/details/107067432)
*   [十大经典排序算法 - 计数排序算法详解](https://blog.csdn.net/qq_35344198/article/details/107206269)
*   [十大经典排序算法 - 桶排序算法详解](https://blog.csdn.net/qq_35344198/article/details/107378626)
*   [十大经典排序算法 - 基数排序算法详解](https://blog.csdn.net/qq_35344198/article/details/107615053)

### 一、什么是[冒泡排序](https://so.csdn.net/so/search?q=%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F&spm=1001.2101.3001.7020)

#### 1. 概念

冒泡排序（Bubble Sort）是排序算法里面比较简单的一个排序。它重复地走访要排序的数列，一次比较两个数据元素，如果顺序不对则进行交换，并一直重复这样的走访操作，直到没有要交换的数据元素为止。

#### 2. 算法原理

这是一个无序数列：1、5、4、2、6、3，我们要将它按从小到大排序。按照冒泡排序的思想，我们要把相邻的元素两两比较，根据大小来交换元素的位置  
![](https://img-blog.csdnimg.cn/20200530100933632.png)  
首先开始第一轮比较

第一步：比较 1 和 5，1 比 5 小，顺序正确，元素位置不变

第二步：比较 5 和 4，5 比 4 大，顺序错误，交换元素位置  
![](https://img-blog.csdnimg.cn/20200530101008755.png)  
![](https://img-blog.csdnimg.cn/20200530101027250.png)  
第三步：比较 5 和 2，5 比 2 大，顺序错误，交换元素位置  
![](https://img-blog.csdnimg.cn/20200530101052123.png)  
![](https://img-blog.csdnimg.cn/20200530101110179.png)  
经过一轮比较后，6 作为最大的元素到了序列的最右侧  
![](https://img-blog.csdnimg.cn/20200530101131105.png)  
接下来进行第二轮比较，从 1 和 4 开始比较，到最右边的 3 结束，6 已经是有序的，不需要再参与比较

第二轮结束后，如下所示  
![](https://img-blog.csdnimg.cn/20200530101200757.png)  
第三轮结束后，如下所示  
![](https://img-blog.csdnimg.cn/20200530101224134.png)  
第四轮结束后，如下所示  
![](https://img-blog.csdnimg.cn/20200530101242479.png)  
第五轮结束后，如下所示  
![](https://img-blog.csdnimg.cn/20200530101259816.png)  
至此所有的元素都是有序的

#### 3. 算法实现

```
function sort(arr) {
    let length = arr.length;
    for (let i = 0; i < length - 1; i++) {
        for (let j = 0; j < length - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
            }
        }
    }
}

let arr = [1, 5, 4, 2, 6, 3];
sort(arr);
console.log(arr);
```

### 二、算法优化

#### 优化一

从图中可以看到，在第三轮时，序列已经是有序了，但程序还是进行了第四、第五轮排序。可以在排序时做个标记，如果序列已经有序了，就不再进行后续的排序  
![](https://img-blog.csdnimg.cn/20200530101327550.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1MzQ0MTk4,size_16,color_FFFFFF,t_70)  
优化后代码如下：

```
function sort(arr) {
    let length = arr.length;
    for (let i = 0; i < length - 1; i++) {
        // 优化，isSorted判断是否有序，已经有序，不需要再继续交换
        let isSorted = true;
        for (let j = 0; j < length - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
                isSorted = false;
            }
        }
        if (isSorted) {
            break;
        }
    }
}

let arr = [1, 5, 4, 2, 6, 3];
sort(arr);
console.log(arr);
```

#### 优化二

看如下序列  
![](https://img-blog.csdnimg.cn/20200807102943262.png)  
第一步，2 和 3 比较，2 比 3 小，顺序正确，元素位置不变

第二步，3 和 1 比较，3 比 1 大，顺序错误，交换元素位置  
![](https://img-blog.csdnimg.cn/20200530101414627.png)  
![](https://img-blog.csdnimg.cn/20200530101440163.png)  
第三步，3 和 4 比较，3 比 4 小，顺序正确，元素位置不变

第四步，4 和 5 比较，4 比 5 小，顺序正确，元素位置不变

第五步，5 和 6 比较，5 比 6 小，顺序正确，元素位置不变  
![](https://img-blog.csdnimg.cn/20200530101501124.png)  
可以看到后 4 位元素已经是有序了，但还是进行了比较，并且在第二轮，第三轮还会对后面有序的元素进行比较。可以通过记录每轮交换后，最后一次交换的位置，进行优化

优化后代码如下所示：

```
function sort(arr) {
    let length = arr.length;
    // 优化2，记录无序数列的边界，每次比较只需要比到这里为止
    let lastExchangeIndex = 0;
    let sortBorder = length - 1;
    for (let i = 0; i < length - 1; i++) {
        // 优化1，isSorted判断是否有序，已经有序，不需要再继续交换
        let isSorted = true;
        for (let j = 0; j < sortBorder; j++) {
            if (arr[j] > arr[j + 1]) {
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
                isSorted = false;
                lastExchangeIndex = j;
            }
        }
        sortBorder = lastExchangeIndex;
        if (isSorted) {
            break;
        }
    }
}

let arr = [2, 3, 1, 4, 5, 6];
sort(arr);
console.log(arr);
```

其实这还不是最优的，有一种排序算法叫鸡尾酒排序算法，能对冒泡排序算法做进一步优化达到最优的目的，详情可参考[鸡尾酒排序算法](https://blog.csdn.net/qq_35344198/article/details/107856432)。

### 三、冒泡排序算法特点

#### 1. 时间复杂度

冒泡排序算法的每一轮要遍历所有元素，轮转的次数和元素数量相当，所以时间复杂度是 O(N^2)

经过优化后，最优的情况，序列已经是顺序的，那么只要进行一次循环，所以最优时间复杂度是 O(N)

#### 2. 空间复杂度

冒泡排序算法排序过程中需要一个临时变量进行两两交换，所需要的额外空间为 1，因此空间复杂度为 O(1)

#### 3. 稳定性

冒泡排序算法在排序过程中，元素两两交换时，相同元素的前后顺序并没有改变，所以冒泡排序是一种稳定排序算法

另外推荐一个开发者小工具网站，个人觉得里面的 Json 格式化功能很强大，报错很详细

[https://tinyutil.com/](https://tinyutil.com)

还可以输入表达式进行内容选取，对于复杂 json 非常多层级的内容展现非常用用处

![](https://img-blog.csdnimg.cn/20200716221534647.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1MzQ0MTk4,size_16,color_FFFFFF,t_70)