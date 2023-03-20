> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_68773927/article/details/129611251)

> 🍓个人主页：[bit..](https://blog.csdn.net/weixin_68773927?spm=1010.2135.3001.5343 "bit..") 
> 
> 🍒系列专栏：[Linux(Ubuntu) 入门必看](https://blog.csdn.net/weixin_68773927/category_11985388.html?spm=1001.2014.3001.5482 "Linux(Ubuntu)入门必看")   [C 语言刷题](https://blog.csdn.net/weixin_68773927/category_11983356.html "C语言刷题      ") [数据结构与算法](https://blog.csdn.net/weixin_68773927/category_12036218.html?spm=1001.2014.3001.5482 "数据结构与算法")  [HTML 和 CSS3](https://blog.csdn.net/weixin_68773927/category_12086374.html "HTML和CSS3")

**目录**

[1.6 快速排序](#t0)

[1. 算法步骤](#t1)

[2. 动图演示](#t2)

[3. 代码实现](#t3)

 [1.7 堆排序](#t4)

[1. 算法步骤](#t5)

[2. 动图演示](#t6)

[3. 代码实现](#t7)

[1.8 计数排序](#t8)

[1. 计数排序的特征](#t9)

[2. 动图演示](#t10)

[3. 代码实现](#t11)

 [1.9 桶排序](#t12)

[1. 什么时候最快](#t13)

[2. 什么时候最慢](#t14)

[3. 示意图](#t15)

[3. 代码实现](#t16)

 [1.10 基数排序](#t17)

[1. 基数排序 vs 计数排序 vs 桶排序](#t18)

[2. LSD 基数排序动图演示](#t19)

[3. 代码实现](#t20)

1.6 [快速排序](https://so.csdn.net/so/search?q=%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F&spm=1001.2101.3001.7020)
--------------------------------------------------------------------------------------------------------

快速排序，一种排序很快的方法，使用分治思想，就是说快速排序是通过把数据分成几部分来处理的一种算法。快排本身和其使用的分治思想都很重要，也是面试可能出现的一大难点。

### 1. 算法步骤

1.  从数列中挑出一个元素，称为 "基准"（pivot）;
    
2.  重新排序数列，所有元素比基准值小的摆放在基准前面，所有元素比基准值大的摆在基准的后面（相同的数可以到任一边）。在这个分区退出之后，该基准就处于数列的中间位置。这个称为分区（partition）操作；
    
3.  递归地（recursive）把小于基准值元素的子数列和大于基准值元素的子数列排序；
    

### 2. 动图演示

![](https://img-blog.csdnimg.cn/img_convert/76a212ed104408af6187786862f671cd.gif)

### 3. 代码实现

```
public class QuickSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        return quickSort(arr, 0, arr.length - 1);
    }
 
    private int[] quickSort(int[] arr, int left, int right) {
        if (left < right) {
            int partitionIndex = partition(arr, left, right);
            quickSort(arr, left, partitionIndex - 1);
            quickSort(arr, partitionIndex + 1, right);
        }
        return arr;
    }
 
    private int partition(int[] arr, int left, int right) {
        // 设定基准值（pivot）
        int pivot = left;
        int index = pivot + 1;
        for (int i = index; i <= right; i++) {
            if (arr[i] < arr[pivot]) {
                swap(arr, i, index);
                index++;
            }
        }
        swap(arr, pivot, index - 1);
        return index - 1;
    }
 
    private void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
 
}
```

 1.7 堆排序
--------

堆排序（Heapsort）是指利用堆这种数据结构所设计的一种排序算法。堆积是一个近似完全二叉树的结构，并同时满足堆积的性质：即子结点的键值或索引总是小于（或者大于）它的父节点。堆排序可以说是一种利用堆的概念来排序的选择排序。分为两种方法：

1.  大顶堆：每个节点的值都大于或等于其子节点的值，在堆排序算法中用于升序排列；
2.  小顶堆：每个节点的值都小于或等于其子节点的值，在堆排序算法中用于降序排列；

### 1. 算法步骤

1.  创建一个堆 H[0……n-1]；
    
2.  把堆首（最大值）和堆尾互换；
    
3.  把堆的尺寸缩小 1，并调用 shift_down(0)，目的是把新的数组顶端数据调整到相应位置；
    
4.  重复步骤 2，直到堆的尺寸为 1。
    

### 2. 动图演示

![](https://img-blog.csdnimg.cn/img_convert/3e539d66afa5dd9e2ac88a57761b58ac.gif)

![](https://img-blog.csdnimg.cn/img_convert/8327a54aecfeca0c5ee1e9ad019ff59a.gif)

### 3. 代码实现

```
public class HeapSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        int len = arr.length;
 
        buildMaxHeap(arr, len);
 
        for (int i = len - 1; i > 0; i--) {
            swap(arr, 0, i);
            len--;
            heapify(arr, 0, len);
        }
        return arr;
    }
 
    private void buildMaxHeap(int[] arr, int len) {
        for (int i = (int) Math.floor(len / 2); i >= 0; i--) {
            heapify(arr, i, len);
        }
    }
 
    private void heapify(int[] arr, int i, int len) {
        int left = 2 * i + 1;
        int right = 2 * i + 2;
        int largest = i;
 
        if (left < len && arr[left] > arr[largest]) {
            largest = left;
        }
 
        if (right < len && arr[right] > arr[largest]) {
            largest = right;
        }
 
        if (largest != i) {
            swap(arr, i, largest);
            heapify(arr, largest, len);
        }
    }
 
    private void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
 
}
```

1.8 计数排序
--------

计数排序的核心在于将输入的数据值转化为键存储在额外开辟的数组空间中。作为一种线性时间复杂度的排序，计数排序要求输入的数据必须是有确定范围的整数。

### 1. 计数排序的特征

当输入的元素是 n 个 0 到 k 之间的整数时，它的运行时间是 Θ(n + k)。计数排序不是比较排序，排序的速度快于任何比较排序算法。

由于用来计数的数组 C 的长度取决于待排序数组中数据的范围（等于待排序数组的最大值与最小值的差加上 1），这使得计数排序对于数据范围很大的数组，需要大量时间和内存。例如：计数排序是用来排序 0 到 100 之间的数字的最好的算法，但是它不适合按字母顺序排序人名。但是，计数排序可以用在基数排序中的算法来排序数据范围很大的数组。

通俗地理解，例如有 10 个年龄不同的人，统计出有 8 个人的年龄比 A 小，那 A 的年龄就排在第 9 位, 用这个方法可以得到其他每个人的位置, 也就排好了序。当然，年龄有重复时需要特殊处理（保证稳定性），这就是为什么最后要反向填充目标数组，以及将每个数字的统计减去 1 的原因。

 算法的步骤如下：

*   （1）找出待排序的数组中最大和最小的元素
*   （2）统计数组中每个值为 i 的元素出现的次数，存入数组 C 的第 i 项
*   （3）对所有的计数累加（从 C 中的第一个元素开始，每一项和前一项相加）
*   （4）反向填充目标数组：将每个元素 i 放在新数组的第 C(i) 项，每放一个元素就将 C(i) 减去 1 

### 2. 动图演示

![](https://img-blog.csdnimg.cn/img_convert/0501dc071622735b23bdda4244a71d3a.gif)

### 3. 代码实现

```
public class CountingSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        int maxValue = getMaxValue(arr);
 
        return countingSort(arr, maxValue);
    }
 
    private int[] countingSort(int[] arr, int maxValue) {
        int bucketLen = maxValue + 1;
        int[] bucket = new int[bucketLen];
 
        for (int value : arr) {
            bucket[value]++;
        }
 
        int sortedIndex = 0;
        for (int j = 0; j < bucketLen; j++) {
            while (bucket[j] > 0) {
                arr[sortedIndex++] = j;
                bucket[j]--;
            }
        }
        return arr;
    }
 
    private int getMaxValue(int[] arr) {
        int maxValue = arr[0];
        for (int value : arr) {
            if (maxValue < value) {
                maxValue = value;
            }
        }
        return maxValue;
    }
 
}
```

 1.9 桶排序
--------

桶排序是计数排序的升级版。它利用了函数的映射关系，高效与否的关键就在于这个映射函数的确定。为了使桶排序更加高效，我们需要做到这两点：

1.  在额外空间充足的情况下，尽量增大桶的数量
2.  使用的映射函数能够将输入的 N 个数据均匀的分配到 K 个桶中

同时，对于桶中元素的排序，选择何种比较排序算法对于性能的影响至关重要。

### 1. 什么时候最快

当输入的数据可以均匀的分配到每一个桶中。

### 2. 什么时候最慢

当输入的数据被分配到了同一个桶中。

### 3. 示意图

元素分布在桶中：

![](https://img-blog.csdnimg.cn/img_convert/3cc40c72c2243ff9de5d6722e43cd9c9.png)

然后，元素在每个桶中排序：

![](https://img-blog.csdnimg.cn/img_convert/b7bd94f0e3aa35da47856c0c78959a6d.png)

### 3. 代码实现

```
public class BucketSort implements IArraySort {
 
    private static final InsertSort insertSort = new InsertSort();
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        return bucketSort(arr, 5);
    }
 
    private int[] bucketSort(int[] arr, int bucketSize) throws Exception {
        if (arr.length == 0) {
            return arr;
        }
 
        int minValue = arr[0];
        int maxValue = arr[0];
        for (int value : arr) {
            if (value < minValue) {
                minValue = value;
            } else if (value > maxValue) {
                maxValue = value;
            }
        }
 
        int bucketCount = (int) Math.floor((maxValue - minValue) / bucketSize) + 1;
        int[][] buckets = new int[bucketCount][0];
 
        // 利用映射函数将数据分配到各个桶中
        for (int i = 0; i < arr.length; i++) {
            int index = (int) Math.floor((arr[i] - minValue) / bucketSize);
            buckets[index] = arrAppend(buckets[index], arr[i]);
        }
 
        int arrIndex = 0;
        for (int[] bucket : buckets) {
            if (bucket.length <= 0) {
                continue;
            }
            // 对每个桶进行排序，这里使用了插入排序
            bucket = insertSort.sort(bucket);
            for (int value : bucket) {
                arr[arrIndex++] = value;
            }
        }
 
        return arr;
    }
 
    /**
     * 自动扩容，并保存数据
     *
     * @param arr
     * @param value
     */
    private int[] arrAppend(int[] arr, int value) {
        arr = Arrays.copyOf(arr, arr.length + 1);
        arr[arr.length - 1] = value;
        return arr;
    }
 
}
```

 1.10 基数排序
----------

基数排序是一种非比较型整数排序算法，其原理是将整数按位数切割成不同的数字，然后按每个位数分别比较。由于整数也可以表达字符串（比如名字或日期）和特定格式的浮点数，所以基数排序也不是只能使用于整数。

### 1. 基数排序 vs 计数排序 vs 桶排序

基数排序有两种方法：

这三种排序算法都利用了桶的概念，但对桶的使用方法上有明显差异：

*   基数排序：根据键值的每位数字来分配桶；
*   计数排序：每个桶只存储单一键值；
*   桶排序：每个桶存储一定范围的数值；

### 2. LSD 基数排序动图演示

![](https://img-blog.csdnimg.cn/img_convert/0fa6a159f8e0a4344b43ff2451c11f8a.gif)

### 3. 代码实现

```
/**
 * 基数排序
 * 考虑负数的情况还可以参考： https://code.i-harness.com/zh-CN/q/e98fa9
 */
public class RadixSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        int maxDigit = getMaxDigit(arr);
        return radixSort(arr, maxDigit);
    }
 
    /**
     * 获取最高位数
     */
    private int getMaxDigit(int[] arr) {
        int maxValue = getMaxValue(arr);
        return getNumLenght(maxValue);
    }
 
    private int getMaxValue(int[] arr) {
        int maxValue = arr[0];
        for (int value : arr) {
            if (maxValue < value) {
                maxValue = value;
            }
        }
        return maxValue;
    }
 
    protected int getNumLenght(long num) {
        if (num == 0) {
            return 1;
        }
        int lenght = 0;
        for (long temp = num; temp != 0; temp /= 10) {
            lenght++;
        }
        return lenght;
    }
 
    private int[] radixSort(int[] arr, int maxDigit) {
        int mod = 10;
        int dev = 1;
 
        for (int i = 0; i < maxDigit; i++, dev *= 10, mod *= 10) {
            // 考虑负数的情况，这里扩展一倍队列数，其中 [0-9]对应负数，[10-19]对应正数 (bucket + 10)
            int[][] counter = new int[mod * 2][0];
 
            for (int j = 0; j < arr.length; j++) {
                int bucket = ((arr[j] % mod) / dev) + mod;
                counter[bucket] = arrayAppend(counter[bucket], arr[j]);
            }
 
            int pos = 0;
            for (int[] bucket : counter) {
                for (int value : bucket) {
                    arr[pos++] = value;
                }
            }
        }
 
        return arr;
    }
 
    /**
     * 自动扩容，并保存数据
     *
     * @param arr
     * @param value
     */
    private int[] arrayAppend(int[] arr, int value) {
        arr = Arrays.copyOf(arr, arr.length + 1);
        arr[arr.length - 1] = value;
        return arr;
    }
}
```