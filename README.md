# C-day-4

1. Move all zeros to the end
   #include <stdio.h>

int main() {
    int arr[] = {0, 1, 0, 3, 12};
    int n = sizeof(arr) / sizeof(arr[0]);
    int i, pos = 0;

  * Move non-zero elements to the front, keeping order */
    for (i = 0; i < n; i++) {
        if (arr[i] != 0)
            arr[pos++] = arr[i];
    }
    /* Fill the remaining positions with zeros */
    while (pos < n)
        arr[pos++] = 0;

    printf("Output: ");
    for (i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
    return 0;
}
2.Maximum sum of a continuous 

#include <stdio.h>

int main() {
    int arr[] = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
    int n = sizeof(arr) / sizeof(arr[0]);
    int i, current = arr[0], max = arr[0];

   for (i = 1; i < n; i++) {
        if (current + arr[i] > arr[i])
            current = current + arr[i];
        else
            current = arr[i];
        if (current > max)
            max = current;
   }
    printf("Maximum subarray sum = %d\n", max);
    return 0;
}
3.Intersection of two arrays
#include <stdio.h>

int main() {
    int a[] = {1, 2, 3, 4, 5};
    int b[] = {3, 4, 5, 6, 7};
    int n1 = sizeof(a) / sizeof(a[0]);
    int n2 = sizeof(b) / sizeof(b[0]);
    int i, j, k, found, repeated;

   printf("Intersection: ");
   for (i = 0; i < n1; i++) {
        /* skip if this value already appeared earlier in a[] */
        repeated = 0;
        for (k = 0; k < i; k++) {
            if (a[k] == a[i]) {
                repeated = 1;
                break;
            }
        }
        if (repeated)
            continue;

   /* check whether a[i] is present in b[] */
        found = 0;
        for (j = 0; j < n2; j++) {
            if (a[i] == b[j]) {
                found = 1;
                break;
            }
        }
        if (found)
            printf("%d ", a[i]);
    }
    printf("\n");
    return 0;
}
