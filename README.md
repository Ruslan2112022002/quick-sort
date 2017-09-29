# quick-sort#include "txLib.h"

int const DATA_SIZE = 50;


void fill  (int data [],int size);
void print (int const data [], int size);
void sort (int data [], int size);
int dividyng (int data [], int start, int end);




int main ()

    {

    int data [DATA_SIZE] = {};
    fill (data, DATA_SIZE);
    sort (data, DATA_SIZE);
    print (data, DATA_SIZE);
    printf ("wall =%d", dividyng (data, 0, DATA_SIZE));
    print (data, DATA_SIZE);

    }

void fill (int data [],int size)

    {

    srand (GetTickCount());

    for (int i = 0; i < size; i++)

        {

        data [i] = rand ();

        }

    }

void print (int const data [], int size)

    {

    for (int i = 0; i < size; i++)

        {

        printf ("data [%d] = %d \n", i, data [i]);

        }

    }

int dividyng (int data[], int start, int end)

    {

    int pivot = end - 1;
    int wall = start;
    for (int i = start; i < end; i++)

        {

        if (data [i] < data [pivot])

            {

            int a = data[wall];
            data [wall] = data [i];
            data[i] = a;
            wall++;

            }

        return wall;

        }

    }

void sort (int data[], int size)

    {
   // while (1 > 0)

      //  {
    //
    //    int dividyng ( data, 0, size);

        //}

    }


