## Heap、heapify、build_heap、heap_sort

### Heap

### heapify

### build_heap

### heap_sort

```Java
public class Main {
    static void swap(int[] arr,int i,int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    static void heapify(int[] tree,int n,int i) {
        if(i >= n) {
            return ;
        }
        int c1 = 2*i+1;
        int c2 = 2*i+2;
        int max = i;
        if(c1 < n && tree[c1] > tree[max]) {
            max = c1;
        }
        if(c2 < n && tree[c2] > tree[max]) {
            max = c2;
        }
        if(i != max) {
            swap(tree,max,i);
            heapify(tree,n,max);
        }
    }

    static void build_heap(int[] tree,int n) {
        int last_node = n-1;
        int parent = (last_node-1)/2;
        for(int i=parent; i>=0; i--) {
            heapify(tree,n,i);
        }
    }

    static void heap_sort(int[] tree,int n) {
        build_heap(tree,n);
        for(int i=n-1; i>=0; i--) {
            swap(tree,i,0);
            heapify(tree,i,0);
        }
    }

    public static void main(String[] args){
        int[] tree = new int[]{4, 10, 3, 5, 1, 2};
        int n = tree.length;
        //heapify(tree,n,0);
        //build_heap(tree,n);
        heap_sort(tree,n);

        for(int i=0; i<n; i++) {
            System.out.println(tree[i]);
        }
    }
}

```