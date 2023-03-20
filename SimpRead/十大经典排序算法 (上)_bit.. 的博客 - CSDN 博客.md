> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_68773927/article/details/129531213?spm=1000.2115.3001.6382&utm_medium=distribute.pc_feed_v2.none-task-blog-hot_rank_bottoming-5-129531213-null-null.pc_personrec&depth_1-utm_source=distribute.pc_feed_v2.none-task-blog-hot_rank_bottoming-5-129531213-null-null.pc_personrec#t0)

**目录**

[1.1 冒泡排序](#1.1%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F)

[1. 算法步骤](#t0)

 [3. 什么时候最快](#t1)

[4. 什么时候最慢](#t2)

[5. 代码实现](#t3)

[1.2 选择排序](#t4)

[1. 算法步骤](#t5)

 [2. 动图演示](#t6)

[3. 代码实现](#t7)

 [1.3 插入排序](#t8)

[1. 算法步骤](#t9)

[2. 动图演示](#t10)

[3. 算法实现](#t11)

[1.4 希尔排序](#t12)

[1. 算法步骤](#t13)

[2. 动图演示](#t14)

 [3. 代码实现](#t15)

[1.5 归并排序](#t16)

[1. 算法步骤](#t17)

 [2. 动图演示](#t18)

 [3. 代码实现](#t19)

1.1 [冒泡排序](https://so.csdn.net/so/search?q=%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F&spm=1001.2101.3001.7020)
========================================================================================================

  冒泡排序（Bubble Sort）也是一种简单直观的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。

### 1. 算法步骤

1.  比较相邻的元素。如果第一个比第二个大，就交换他们两个。
2.  对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
3.  针对所有的元素重复以上的步骤，除了最后一个。
4.  持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

 ![](https://img-blog.csdnimg.cn/d2adefcbe1e147538f9279af5685bdde.gif)

###  3. 什么时候最快

当输入的数据已经是正序时。

### 4. 什么时候最慢

当输入的数据是反序时

### 5. 代码实现

```
public class BubbleSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        for (int i = 1; i < arr.length; i++) {
            // 设定一个标记，若为true，则表示此次循环没有进行交换，也就是待排序列已经有序，排序已经完成。
            boolean flag = true;
 
            for (int j = 0; j < arr.length - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    int tmp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = tmp;
 
                    flag = false;
                }
            }
 
            if (flag) {
                break;
            }
        }
        return arr;
    }
}
```

1.2 [选择排序](https://so.csdn.net/so/search?q=%E9%80%89%E6%8B%A9%E6%8E%92%E5%BA%8F&spm=1001.2101.3001.7020)
========================================================================================================

选择排序是一种简单直观的排序算法，无论什么数据进去都是 O(n²) 的时间复杂度。

1. 算法步骤
-------

1.  首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置。
2.  再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。
3.  重复第二步，直到所有元素均排序完毕。

 2. 动图演示
--------

![](https://img-blog.csdnimg.cn/62db89431f1a422e9636972c7286c965.gif)

3. 代码实现
-------

```
public class SelectionSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        // 总共要经过 N-1 轮比较
        for (int i = 0; i < arr.length - 1; i++) {
            int min = i;
 
            // 每轮需要比较的次数 N-i
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[j] < arr[min]) {
                    // 记录目前能找到的最小值元素的下标
                    min = j;
                }
            }
 
            // 将找到的最小值和i位置所在的值进行交换
            if (i != min) {
                int tmp = arr[i];
                arr[i] = arr[min];
                arr[min] = tmp;
            }
 
        }
        return arr;
    }
}
```

 1.3 [插入排序](https://so.csdn.net/so/search?q=%E6%8F%92%E5%85%A5%E6%8E%92%E5%BA%8F&spm=1001.2101.3001.7020)
=========================================================================================================

插入排序是一种最简单直观的排序算法，它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。

插入排序和冒泡排序一样，也有一种优化算法，叫做拆半插入。

1. 算法步骤
-------

1.  将第一待排序序列第一个元素看做一个有序序列，把第二个元素到最后一个元素当成是未排序序列。
2.  从头到尾依次扫描未排序序列，将扫描到的每个元素插入有序序列的适当位置。（如果待插入的元素与有序序列中的某个元素相等，则将待插入元素插入到相等元素的后面。）

2. 动图演示
-------

![](https://img-blog.csdnimg.cn/bbb3ee381d814b92babb3575be80a10d.gif)

3. 算法实现
-------

```
public class InsertSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        // 从下标为1的元素开始选择合适的位置插入，因为下标为0的只有一个元素，默认是有序的
        for (int i = 1; i < arr.length; i++) {
 
            // 记录要插入的数据
            int tmp = arr[i];
 
            // 从已经排序的序列最右边的开始比较，找到比其小的数
            int j = i;
            while (j > 0 && tmp < arr[j - 1]) {
                arr[j] = arr[j - 1];
                j--;
            }
 
            // 存在比其小的数，插入
            if (j != i) {
                arr[j] = tmp;
            }
 
        }
        return arr;
    }
}
```

1.4 希尔排序
========

希尔排序，也称递减增量排序算法，是插入排序的一种更高效的改进版本。但希尔排序是非稳定排序算法。

希尔排序是基于插入排序的以下两点性质而提出改进方法的：

*   插入排序在对几乎已经排好序的数据操作时，效率高，即可以达到线性排序的效率；
*   但插入排序一般来说是低效的，因为插入排序每次只能将数据移动一位；

希尔排序的基本思想是：先将整个待排序的记录序列分割成为若干子序列分别进行直接插入排序，待整个序列中的记录 "基本有序" 时，再对全体记录进行依次直接插入排序。

1. 算法步骤
-------

1.  选择一个增量序列 t1，t2，……，tk，其中 ti > tj, tk = 1；
2.  按增量序列个数 k，对序列进行 k 趟排序；
3.  每趟排序，根据对应的增量 ti，将待排序列分割成若干长度为 m 的子序列，分别对各子表进行直接插入排序。仅增量因子为 1 时，整个序列作为一个表来处理，表长度即为整个序列的长度。

2. 动图演示
-------

 ![](https://img-blog.csdnimg.cn/9fb773b638ca4390a250dbf68e2a7bbc.gif)

 3. 代码实现
--------

```
public static void shellSort(int[] arr) {
    int length = arr.length;
    int temp;
    for (int step = length / 2; step >= 1; step /= 2) {
        for (int i = step; i < length; i++) {
            temp = arr[i];
            int j = i - step;
            while (j >= 0 && arr[j] > temp) {
                arr[j + step] = arr[j];
                j -= step;
            }
            arr[j + step] = temp;
        }
    }
}
```

1.5 归并排序
========

归并排序（Merge sort）是建立在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用。

作为一种典型的分而治之思想的算法应用，归并排序的实现由两种方法：

*   自上而下的递归（所有递归的方法都可以用迭代重写，所以就有了第 2 种方法）；
*   自下而上的迭代；

1. 算法步骤
-------

1.  申请空间，使其大小为两个已经排序序列之和，该空间用来存放合并后的序列；
2.  设定两个指针，最初位置分别为两个已经排序序列的起始位置；
3.  比较两个指针所指向的元素，选择相对小的元素放入到合并空间，并移动指针到下一位置；
4.  重复步骤 3 直到某一指针达到序列尾；
5.  将另一序列剩下的所有元素直接复制到合并序列尾。

 2. 动图演示
--------

![](https://img-blog.csdnimg.cn/53cb38372389445d9a57c2fd4238e328.gif)

 3. 代码实现
--------

```
public class MergeSort implements IArraySort {
 
    @Override
    public int[] sort(int[] sourceArray) throws Exception {
        // 对 arr 进行拷贝，不改变参数内容
        int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
 
        if (arr.length < 2) {
            return arr;
        }
        int middle = (int) Math.floor(arr.length / 2);
 
        int[] left = Arrays.copyOfRange(arr, 0, middle);
        int[] right = Arrays.copyOfRange(arr, middle, arr.length);
 
        return merge(sort(left), sort(right));
    }
 
    protected int[] merge(int[] left, int[] right) {
        int[] result = new int[left.length + right.length];
        int i = 0;
        while (left.length > 0 && right.length > 0) {
            if (left[0] <= right[0]) {
                result[i++] = left[0];
                left = Arrays.copyOfRange(left, 1, left.length);
            } else {
                result[i++] = right[0];
                right = Arrays.copyOfRange(right, 1, right.length);
            }
        }
 
        while (left.length > 0) {
            result[i++] = left[0];
            left = Arrays.copyOfRange(left, 1, left.length);
        }
 
        while (right.length > 0) {
            result[i++] = right[0];
            right = Arrays.copyOfRange(right, 1, right.length);
        }
 
        return result;
    }
 
}
```