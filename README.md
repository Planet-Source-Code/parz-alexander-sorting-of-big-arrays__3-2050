<div align="center">

## Sorting of big arrays


</div>

### Description

You can test 7 different sorting algorithms, with random numbers even large numbers not only integers.
 
### More Info
 
1.)Which sorting algorithm.

2.)Starting number of the random number

3.)Ending number of the random number

4.)Amount of the random numbers

My aim had been to produce random numbers larger

than 32767 in a range which you can choose.

1.)You can choose if you want to see the unsorted

and sorted array.

2.)The sec. how long the choosen sorting algorithm

needs.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Parz Alexander](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/parz-alexander.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C, C\+\+ \(general\)
**Category**       |[Algorithms](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithms__3-29.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/parz-alexander-sorting-of-big-arrays__3-2050/archive/master.zip)





### Source Code

```
/*Alexander
You can choose any starting and ending point also you can choose
the amount of numbers to be sorted. I tried to play with Prototypes
so I wrote this prg. It should be easy to understand and you can
take out very easy any sorting algorithm for your own purpose.
If you find some bugs please tell me. I just started to learn C++
2 months ago so it is possible that there are some bugs.*/
#include<iomanip.h>
#include<iostream.h>
#include<stdlib.h>
#include<math.h>
#include<time.h>
#include<conio.h>
#include<stdio.h>
long Zufallszahlen(long,long);
void UAusgabe(long *, long);
void SAusgabe(long *, long);
void Bubblesort (long *, long);
void DoubleBubble (long *, long);
void Selectionsort (long *, long);
void Insertionsort (long *,long);
void Shellsort (long *, long);
void Heapsort(long *, long);
void BuildHeap(long, long *, long);
void Quicksort(long *, long);
void QuickLR(long *, long, long);
double tBubble(0);
double tDouble(0);
double tInsertion(0);
double tSelection(0);
double tShell(0);
double tQuick(0);
double tHeap(0);
void main()
{
	long a(0);
	long b(0);
	long c(0);
	long d(0);
	int e(0);
	int e1[8]={0,0,0,0,0,0,0,0};
	int e2(-1);
	int f(0);
	long i(0);
	time_t m;
	time(&m);
	srand(m);
	do
	{
	cout << "Choose the Sorting Algorithm???"
		 << endl << endl
		 << "1.) Bubblesort" << endl
		 << "2.) Doublesort" << endl
		 << "3.) Selectionsort" << endl
		 << "4.) Insertionsort" << endl
		 << "5.) Shellsort" << endl
		 << "6.) Heapsort" << endl
		 << "7.) Quicksort " << endl
		 << "8.) All" << endl
		 << "9.) Choosen" << endl << endl
		 << "Type in the number" << endl;
	cin >> e;
	e2++;
	e1[e2]=e;
	}
	while((e!=9) && (e!=8));
		cout << "Type in the start number" << endl;
		cin >> a;
		cout << endl;
		cout << "Type in the end number" << endl;
		cin >> b;
		cout << endl;
		cout << "How many random numbers???" << endl;
		cin >> c;
		cout << endl;
		cout << "Want to print out the numbers" << endl
			 << "Press 1 for YES 0 for NO" << endl;
		cin >> f;
		cout << endl;
	long *x = new long[c];
	long *y = new long[c];
	for(d=0;d<c;d++)
	{
		y[d] = x[d] = Zufallszahlen(a,b);
	}
	if((e1[0]==1) || (e1[1]==1) || (e1[2]==1) || (e1[3]==1) || (e1[4]==1) || (e1[5]==1) || (e1[6]==1) || (e1[7]==1))
	{
		cout << endl;
		Bubblesort(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tBubble << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Bubblesort" << endl;
	}
	if((e1[0]==2) || (e1[1]==2) || (e1[2]==2) || (e1[3]==2) || (e1[4]==2) || (e1[5]==2) || (e1[6]==2) || (e1[7]==2))
	{
		cout << endl;
		DoubleBubble(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tDouble << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Doublesort" << endl;
	}
	if((e1[0]==3) || (e1[1]==3) || (e1[2]==3) || (e1[3]==3) || (e1[4]==3) || (e1[5]==3) || (e1[6]==3) || (e1[7]==3))
	{
		cout << endl;
		Selectionsort(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tSelection << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Selectionsort" << endl;
	}
	if((e1[0]==4) || (e1[1]==4) || (e1[2]==4) || (e1[3]==4) || (e1[4]==4) || (e1[5]==4) || (e1[6]==4) || (e1[7]==4))
	{
		cout << endl;
		Insertionsort(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tInsertion << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Insertionsort" << endl;
	}
	if((e1[0]==5) || (e1[1]==5) || (e1[2]==5) || (e1[3]==5) || (e1[4]==5) || (e1[5]==5) || (e1[6]==5) || (e1[7]==5))
	{
		cout << endl;
		Shellsort(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tShell << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Shellsort" << endl;
	}
	if((e1[0]==6) || (e1[1]==6) || (e1[2]==6) || (e1[3]==6) || (e1[4]==6) || (e1[5]==6) || (e1[6]==6) || (e1[7]==6))
	{
		cout << endl;
		Heapsort(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tHeap << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Heapsort" << endl;
	}
	if((e1[0]==7) || (e1[1]==7) || (e1[2]==7) || (e1[3]==7) || (e1[4]==7) || (e1[5]==7) || (e1[6]==7) || (e1[7]==7))
	{
		cout << endl;
		Quicksort(x,c);
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tQuick << " sec "
		<< "for " << c <<" Random numbers "
		<< "with Quicksort" << endl;
	}
	if((e1[0]==8) || (e1[1]==8) || (e1[2]==8) || (e1[3]==8) || (e1[4]==8) || (e1[5]==8) || (e1[6]==8) || (e1[7]==8))
	{
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
			cout << endl;
			Bubblesort(x,c);
			cout << "Bubblesort finished" << endl;
		if(f==1)
		{
		UAusgabe(y,c);
		SAusgabe(x,c);
		}
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
			cout << endl;
			DoubleBubble(x,c);
			cout << "DoubleBubble finished" << endl;
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
			cout << endl;
			Selectionsort(x,c);
			cout << "Selectionsort finished" << endl;
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
		cout << endl;
			Insertionsort(x,c);
			cout << "Insertionsort finished" << endl;
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
		cout << endl;
			Shellsort(x,c);
			cout << "Shellsort finished" << endl;
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
			cout << endl;
			Heapsort(x,c);
			cout << "Heapsort finished" << endl;
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		for(d=0;d<c;d++)
		{
			y[d] = x[d] = Zufallszahlen(a,b);
		}
			cout << endl;
			Quicksort(x,c);
			cout << "Quicksort finished" << endl <<endl;
		if(f==1)
		{
			UAusgabe(y,c);
			SAusgabe(x,c);
		}
		cout << tBubble << " sec "
		<< "for " << c << " Random numbers "
		<< "with Bubblesort" << endl;
		cout << tDouble << " sec "
		<< "for " << c << " Random numbers "
		<< "with Doublesort" << endl;
		cout << tSelection << " sec "
		<< "for " << c << " Random numbers "
		<< "with Selectionsort" << endl;
		cout << tInsertion << " sec "
		<< "for " << c << " Random numbers "
		<< "with Insertionsort" << endl;
		cout << tShell << " sec "
		<< "for " << c << " Random numbers "
		<< "with Shellsort" << endl;
		cout << tHeap << " sec "
		<< "for " << c << " Random numbers "
		<< "with Heapsort" << endl;
		cout << tQuick << " sec "
		<< "for " << c << " Random numbers "
		<< "with Quicksort" << endl;
	}
}
void Bubblesort(long *x,long c)
{
	long a(0);
	long b(0);
	long d(0);
	double t1(0);
	double t2(0);
	t1=clock();
	for(a=1;a<c;a++)
	{
		for(b=0;b<c-a;b++)
		{
			if(x[b]>x[b+1])
			{
				x[b]^=x[b+1];
				x[b+1]^=x[b];
				x[b]^=x[b+1];
			}
		}
	}
	t2=clock();
	tBubble = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void DoubleBubble(long *x,long c)
{
	long a(0);
	long b(0);
	long i(0);
	long j(1);
	double t1(0);
	double t2(0);
	t1=clock();
	a=c-1;
	b=-1;
	while(b<a)
	{
		b++;
		a--;
		for(i=b;i<a;i++)
			if (x[i]>x[i+1])
			{
				x[i]^=x[i+1];
				x[i+1]^=x[i];
				x[i]^=x[i+1];
			}
			for(j=a;j>=b;--j)
			if (x[j]>x[j+1])
			{
				x[j]^=x[j+1];
				x[j+1]^=x[j];
				x[j]^=x[j+1];
			}
	}
	t2=clock();
	tDouble = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void Selectionsort(long *x,long c)
{
	long a(0);
	long b(0);
	long d(0);
	long m(0);
	double t1(0);
	double t2(0);
	t1=clock();
	for(a=0;a<c-1;a++)
	{
		d=a;
		for(b=a+1;b<c;b++)
		{
			if(x[b]<x[d])
				d=b;
		}
			if(d!=a)
			{
				x[a]^=x[d];
				x[d]^=x[a];
				x[a]^=x[d];
			}
	}
	t2=clock();
	tSelection = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void Insertionsort(long *x,long c)
{
	long a(0);
	long b(0);
	long d(0);
	double t1(0);
	double t2(0);
	t1=clock();
	for(a=1;a<c;a++)
	{
		d=x[a];
		for(b=a;b && (x[b-1] > d);b--)
		{
			x[b]=x[b-1];
		}
		x[b]=d;
	}
	t2=clock();
	tInsertion = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void Shellsort(long *x,long c)
{
	long a(0);
	long b(0);
	long d(0);
	long h(0);
	long i(0);
	double t1(0);
	double t2(0);
	cout << endl;
	cout << "Please type in an int number for the row of Shellsort" << endl;
	cin >> i;
	t1=clock();
	for(h=1;h<=c/(i*i);h=i*h+1)
	;
		for (; h>0;h/=i)
			{
			for(a=h;a<c;a++)
			{
				d=x[a];
				for(b=a;(b>=h) && (x[b-h] > d);b-=h)
				{
					x[b]=x[b-h];
				}
				x[b]=d;
			}
	}
	t2=clock();
	tShell = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void Heapsort(long *x, long c)
{
	long k(0);
	long t(0);
	double t1(0);
	double t2(0);
	t1=clock();
	for(k=c/2;k;)
	{
		BuildHeap(c,x,--k);
	}
	while( --c)
	{
		x[c]^=x[0];
		x[0]^=x[c];
		x[c]^=x[0];
		BuildHeap(c, x, 0);
	}
	t2=clock();
	tHeap = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void BuildHeap(long c, long *x, long k)
{
	long i(0);
	long j(0);
	j=x[k];
	while(k<c/2)
	{
		i=2*k+1;
		if((i<c-1) && (x[i]<x[i+1]))
			i++;
		if(j>=x[i])
			break;
		x[k]=x[i];
		k=i;
	}
	x[k]=j;
}
void Quicksort(long *x, long c)
{
	double t1(0);
	double t2(0);
	t1=clock();
	QuickLR(x,c-1,0);
	t2=clock();
	tQuick = (double)(t2-t1)/CLOCKS_PER_SEC;
}
void QuickLR( long *x,long r,long l)
{
	long med(0);
	long i(0);
	long j(0);
	if(r>l)
	{
		med=x[r];
		i=l-1;
		j=r;
		for(;;)
		{
			while(x[++i]<med)
				;
			while(x[--j]>med)
				;
			if(i>=j)
				break;
				x[i]^=x[j];
				x[j]^=x[i];
				x[i]^=x[j];
		}
		x[r]=x[i];
		x[i]=med;
		QuickLR(x,i-1,l);
		QuickLR(x,r,i+1);
	}
}
void UAusgabe(long *y ,long c)
{
	long z(0);
	for(z=0;z<c;z++)
	{
		cout << y[z] << '\t';
	}
cout << endl;
}
void SAusgabe(long *x ,long c)
{
	long z(0);
	for(z=0;z<c;z++)
	{
		cout << x[z] << '\t';
	}
cout << endl;
}
long Zufallszahlen(long a1,long b1)
{
	long x(0);
	x = long((b1-a1)*((double) rand()/RAND_MAX)+a1);
	return long (x);
}
```

