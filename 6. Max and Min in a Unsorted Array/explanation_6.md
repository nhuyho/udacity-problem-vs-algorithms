# Problem 6: Unsorted Integer Array  


This problem does not require a sorted array. Rather first store the max and min as the first list element, then iterate over each list element to see if a larger or smaller part appears. This involves a single array traversal and thus is O(n) for time complexity. In addition, the algorithm consists in storing the entire list in memory for traversal, which is also O(n) in space complexity.