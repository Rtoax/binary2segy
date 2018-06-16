# binary2segy
Convert binary to seismic files in SeismicUnix format
* some swap function
```c
void swap_short_2(short *tni2);
void swap_u_short_2(unsigned short *tni2);
void swap_int_4(int *tni4);
void swap_u_int_4(unsigned int *tni4);
void swap_long_4(long *tni4);
void swap_u_long_4(unsigned long *tni4);
void swap_float_4(float *tnf4);
void swap_double_8(double *tndd8);
void swaphval(segy *tr, int index);
```

* the important function that  swap ```float```

```cpp
void swap_float_4(float *tnf4)
/**************************************************************************
swap_float_4		swap a float
***************************************************************************/
{
 int *tni4=(int *)tnf4;
 *tni4=(((*tni4>>24)&0xff) | ((*tni4&0xff)<<24) |
	    ((*tni4>>8)&0xff00) | ((*tni4&0xff00)<<8));
}
```
