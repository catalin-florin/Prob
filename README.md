# Problema biti

int main ()
{
	int a=64,i=0,b,c,z=0,n=0;
	n=sizeof(a)*8;

	for(i=0;i<n-1;i++)
	{

		if( ( (a>>i)&1) == 1 )
				{
					b=1;
				}
				else
				{
					b=0;
				}

		if( ( (a>>(i+2))&1 ) == 1 )
					{
						c=1;
					}
					else
					{
						c=0;
					}
		if(b>c)
		{
			a|=1<<(i+2);
			a&=~(1<<i);
			z++;
		}
		else if(c>b)
		{
			a|=(1<<i);
			a&=~(1<<(i+2));
			z++;
		}
		else if(c==b)
		{
			z++;
		}

if(z%2==0)
{
	i=i+2;
}

}

cout<<endl<<a;

return 0;


}





[‎3/‎5/‎2018
10:49 AM]  Tobescu, Cornel Marius:  

#include <stdio.h>

#include <stdlib.h>

 

#define number(x)(    
((((x&0xF)>>2) | ((x&0xF)<<2))&0xF) | \

       
((((((x>>4)&0xF)>>2) |
(((x>>4)&0xF)<<2))&0xF)<<4) | \

       
((((((x>>8)&0xF)>>2) |
(((x>>8)&0xF)<<2))&0xF)<<8) | \

       
((((((x>>12)&0xF)>>2)|
(((x>>12)&0xF)<<2))&0xF)<<12)  | \

       
((((((x>>16)&0xF)>>2) |
(((x>>16)&0xF)<<2))&0xF)<<16) | \

       
((((((x>>20)&0xF)>>2) |
(((x>>20)&0xF)<<2))&0xF)<<20) | \

       
((((((x>>24)&0xF)>>2) |
(((x>>24)&0xF)<<2))&0xF)<<24) | \

       
((((((x>>28)&0xF)>>2) |
(((x>>28)&0xF)<<2))&0xF)<<28)   \

                  )

int main()

{

 

    printf("Number:
%d",number(0x66));

    //
printf("Number: %d",a);

    return 0;

} 
