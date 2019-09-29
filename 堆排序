public class HeapSort {
    public static void heapSort(int[] array) {
        // 1. 建大堆
        createBigHeap(array);

        // 2. 选出 array.length - 1 个数
        for (int i = 0; i < array.length - 1; i++) {
            // 无序: [0. array.length - i)
            // [0] [array.length - i - 1]
            swap(array, 0, array.length - i - 1);
            // 无序的长度 - 1
            // 长度 array.length - i - 1
            shiftDown(array, array.length - i - 1, 0);
        }
    }

    private static void createBigHeap(int[] array) {
        for (int i = (array.length - 2) / 2; i >= 0; i--) {
            shiftDown(array, array.length, i);
        }
    }

    private static void shiftDown(int[] array, int size, int i) {
        while (2 * i + 1 < size) {
            int max = 2 * i + 1;
            if (max + 1 < size) {
                if (array[max + 1] > array[max]) {
                    max = max + 1;
                }
            }

            if (array[i] >= array[max]) {
                return;
            }

            swap(array, i, max);
            i = max;
        }
    }

    private static void swap(int[] array, int i, int j) {
        int t = array[i];
        array[i] = array[j];
        array[j] = t;
    }
}
