#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>

/*
Input sample
 2
 4
 1 2 3 4
 5
 -1 2 -3 4 -5

 Output Sample
 10 10
 4  6

*/

int* getArray(char *txt, int num)
{
    int *arr = malloc(sizeof(int) * num);
    if (arr == NULL)
    {
        printf("Memory allocation failed\n");
        return NULL;
    }

    int i = 0;
    char *temp = strtok(txt, " ");
    while (temp != NULL && i < num)
    {
        arr[i++] = atoi(temp);
        temp = strtok(NULL, " ");
    }
    return arr;
}

int MaxSequenceArr(int *arr, int num)
{
    int maxSum = arr[0];
    int currentSum = arr[0];

    for (int i = 1; i < num; i++)
    {
        currentSum = currentSum > 0 ? currentSum + arr[i] : arr[i];
        if (currentSum > maxSum)
            maxSum = currentSum;
    }

    return maxSum;
}

int main()
{
    int cases;
    scanf("%d", &cases);

    while (cases--)
    {
        int n;
        scanf("%d", &n);

        char str[1000];
        getchar();
        fgets(str, sizeof(str), stdin);

        size_t len = strlen(str);
        if (len > 0 && str[len - 1] == '\n') {
            str[len - 1] = '\0';
        }

        int *arr = getArray(str, n);
        if (arr == NULL)
        {
            return 1; 
        }

        int max = MaxSequenceArr(arr, n);
        printf("%d\n", max);

        free(arr);
    }

    return 0;
}
