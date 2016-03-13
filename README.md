/*Реализовать функцию int getmax2(const int *arr, int count),
 *  которая принимает в
 * качестве параметров целочисленный массив элементов arr и
 * количество элементов в массиве count. Гарантируется, что
 * значение count ≥ 2. Функция должна вернуть значение элемента
 * массива, который является вторым максимальным элементом в массиве,
 *  то есть в массиве, отсортированном по убыванию, данное
 *  значение находится на позиции 1. Не используйте сортировку.*/
#include <stdio.h>

int getmax2(const int *arr, int count);

int main()
{
    int count, i;
    count =-1;
        while (count < 2)
    {
        printf("\nWrite count of array: ");
        scanf("%d",&count);
        if (count<2)
            {
                printf("Error, count of array must be >=2!\n");
            }
        else
            {
                printf("Okay, count = %3d \n",count);
            }
    }
    int array[count];
    for ( i = 0; i < count; ++i)
    {
        printf("\nInput element of array, arr[%d]: ",i);
        scanf("%d",&array[i]);
    }

    getmax2(array,count);
    return 0;
}


int getmax2(const int *arr, int count)
{

    int gmax = arr[0];
    int gmax2 = arr[1];
    if(gmax<gmax2){gmax=arr[1];gmax2=arr[0];}
    int i;
    if(gmax==gmax2)
    {
        for(i=2;i<count;++i)
            {
            if(arr[i]>gmax)
                {
                gmax2 = gmax;
                gmax = arr[i];
                }
            else
            if(gmax==gmax2 && arr[i]<gmax2)
                {
                gmax2=arr[i];
                }
            }
    }
    else
    {
        for(i=2;i<count;++i)
            {
            if(arr[i]>gmax)
                {
                gmax2 = gmax;
                gmax = arr[i];
                }
            else
            if(arr[i]>gmax2)
                {
                gmax2=arr[i];
                }
            }
    }
     printf("Okay, getmax2 = %3d \n",gmax2);
    return gmax2;
}
