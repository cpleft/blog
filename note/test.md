# Collection of Functions for Testing of C++
### rand()
```c++
int rand() 
```
Produce a integer range from 0 to 2147483647(int).
Contained in `<cstdlib>`.

e.g.
```c++
#include <iostream>
#include <cstdlib>                          // for rand()
using namespace std;
int main() {
    for (int i = 1; i <= 100; ++i)
        cout << rand() << " ";
    cout << endl;
    for (int i = 1; i <= 100; ++i)
        cout << rand() % 1000 << " ";       // produce numbers lower than 
                                            // 1000. 
    cout << endl;
}
```

### srand()
If you do not assign a `srand()` function for rand(), every time you run 
this program the results will be the same.  Because the seed of the 
`rand()` function is the same.  You can use function `srand()` to assign 
a seed for function rand().  If you do not assign `srand()` explicitly, 
the seed will be default value 1.

```c++
void srand(unsigned int seed)
```
It is practical to invoke `time(0)` in the ``srand()`` function to produce
a ramdom seed.

```c++
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main()
{
    srand((int)time(0));
    for (int i = 1; i <= 100; ++i)
        cout << rand() << " ";
    cout << endl;
}
```
Then if you run this program more than once, the random numbers each run
produced will be different.

### clock()
clock() is used to record that how many time your program occupied to run.

```c++
clock_t clock(void)
```

Contained in `<ctime>`.

`clock_t` is a data type for recording time, actually it is `long int`.

```c++
typedef long    clock_t;
```

The return value of this function is a variable of `clock_t` which denotes 
how much time the program has occupied CPU.  The standard unit to measure
time spent in CPU is _clock tick_.  One second may contain 1000000000 clock
ticks.  It depends on your CPU's dominaant frequency.

`<ctime>` defined a constant variable `CLOCKS_PRE_SEC`, which denotes how 
many clock ticks will occur in one second.  You can use this constant
variable to calculate out how many seconds your program occupied CPU.

```c++
#include<iostream>
#include<ctime>
using namespace std;
int main()
{
    clock_t startTime, endTime;
    startTime = clock();            // start recording
    for (int i = 0; i < 2147483640; i++)
        i++;
    endTime = clock();              // end of recording
    cout << "The run time is: " << (double)(endTime - startTime) /
        CLOCKS_PER_SEC << "s" << endl;
    system("pause");
    return 0;
}
```
