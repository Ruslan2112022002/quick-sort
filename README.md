#include "txLib.h"

int const DATA_SIZE = 50;


void fill  (int data [],int size);
void print (int const data [], int size);
void sort (int data [], int start, int end, int wall);
int partish (int data [], int start, int end);
void swap (int first_elem, int second_elem, int data []);




int main ()

    {

    int data [DATA_SIZE] = {};
    fill (data, DATA_SIZE);
    sort (data, 0, DATA_SIZE , partish (data, 0, DATA_SIZE));
  //  print (data, DATA_SIZE);
    //int a = partish (data, 0, DATA_SIZE);
  //  printf ("wall =%d\n", a);
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

int partish (int data[], int start, int end)

    {

    int pilot = end - 1;
    int wall = start;
    printf ("%d\n", data[pilot]);
    for (int i = start; i < pilot; i++)

        {

        if (data [i] < data [pilot])

            {

            int a = data[wall];
            data [wall] = data [i];
            data[i] = a;
            wall++;

            }

        }

    swap (wall, pilot, data);
    //int a = data[wall];
    //data [wall] = data [pilot];
    //data[pilot] = a;

    return wall;

    }

void sort (int data[], int start, int end, int wall)

    {

    if (wall - start > 1)

        {

        sort (data, start, wall,partish ( data, start, wall));

        }

    if (end - wall > 1)

        {

        sort ( data, wall+1, end, partish( data, wall+1, end));

        }

    }


void swap (int first_elem, int second_elem, int data [])

    {

    int a = data[first_elem];
    data [first_elem] = data [second_elem];
    data[second_elem] = a;

    }


