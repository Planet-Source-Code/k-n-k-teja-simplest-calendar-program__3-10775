<div align="center">

## Simplest Calendar Program


</div>

### Description

This is a 28 line calendar program. It prints any month entered after Jan, 1980. Simple program to show the power of calculations.
 
### More Info
 
The inputs of the program are the month and year numbers you want to print the calendar for.

Nothing special

Program does not return anything but displays the calendar for the requested month

No special side effects for the program.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[K\. N\. K\. TEJA](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/k-n-k-teja.md)
**Level**          |Beginner
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |C\+\+ \(general\), Borland C\+\+
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/k-n-k-teja-simplest-calendar-program__3-10775/archive/master.zip)

### API Declarations

```
iostream.h for cout,cin and,
conio.h for clrscr(), getch().
```


### Source Code

```
#include<iostream.h>
#include<conio.h>
void main(){
 int i,cm,cy,d=2; //cm = current month, cy = current year. d=2 because 1st jan,1980 is tuesday.
 int m[12]={31,28,31,30,31,30,31,31,30,31,30,31}; //Array to hold no. of days in all months.
 clrscr();
 cout<<"Enter month and year:";
 cin>>cm>>cy;
 if(cm<1||cm>12||cy<1980){
  cout<<"ERROR! Cannot display below 1980.";
  return; //returns from main
 }
 m[1]=!(cy%4)+28; // !(cy%4) is true if cy is a leapyear
 for(i=1980;i<cy;i++){
  d+=!(i%4)+365;
  d%=7; //calculates the effective day.
 }
 for(i=2;i<=cm;i++)
  d+=m[i-2];
 d%=7;
 cout<<"\nSu\tMo\tTu\tWe\tTh\tFr\tSa\n";
 for(i=0;i<d;i++)cout<<" \t";
 for(i=1;i<=m[cm-1];i++,d++){
  cout<<i<<'\t';
  if(!((d+1)%7))cout<<endl;
 }
 getch();
}
```

