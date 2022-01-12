# HalfAdder
```
CHIP HalfAdder 
{
    IN a, b;
    OUT sum, carry;

    PARTS:
    Xor(a=a, b=b, out=sum);
    And(a=a, b=b, out=carry);
}
```
![image](https://user-images.githubusercontent.com/80435655/149147935-7ec5a96f-ceec-4f69-99cc-59a29bf10836.png)
# FullAdder
```
CHIP HalfAdder 
{
    IN a, b;
    OUT sum, carry;

    PARTS:
    Xor(a=a, b=b, out=sum);
    And(a=a, b=b, out=carry);
}
```
![image](https://user-images.githubusercontent.com/80435655/149149231-6b6d3255-aa35-4e01-b4f3-e34f077d4cdc.png)

# Add16
```
CHIP Add16
 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
    FullAdder(a=a[0],  b=b[0],  c=false,   carry=carry0, sum=out[0]);
    /* HalfAdder(a=a[0], b=b[0], carry=carry0, sum=out[0]); */
    FullAdder(a=a[1],  b=b[1],  c=carry0,  carry=carry1, sum=out[1]);
    FullAdder(a=a[2],  b=b[2],  c=carry1,  carry=carry2, sum=out[2]);
    FullAdder(a=a[3],  b=b[3],  c=carry2,  carry=carry3, sum=out[3]);
    FullAdder(a=a[4],  b=b[4],  c=carry3,  carry=carry4, sum=out[4]);
    FullAdder(a=a[5],  b=b[5],  c=carry4,  carry=carry5, sum=out[5]);
    FullAdder(a=a[6],  b=b[6],  c=carry5,  carry=carry6, sum=out[6]);
    FullAdder(a=a[7],  b=b[7],  c=carry6,  carry=carry7, sum=out[7]);
    FullAdder(a=a[8],  b=b[8],  c=carry7,  carry=carry8, sum=out[8]);
    FullAdder(a=a[9],  b=b[9],  c=carry8,  carry=carry9, sum=out[9]);
    FullAdder(a=a[10], b=b[10], c=carry9,  carry=carry10, sum=out[10]);
    FullAdder(a=a[11], b=b[11], c=carry10, carry=carry11, sum=out[11]);
    FullAdder(a=a[12], b=b[12], c=carry11, carry=carry12, sum=out[12]);
    FullAdder(a=a[13], b=b[13], c=carry12, carry=carry13, sum=out[13]);
    FullAdder(a=a[14], b=b[14], c=carry13, carry=carry14, sum=out[14]);
    FullAdder(a=a[15], b=b[15], c=carry14, carry=carry15, sum=out[15]);
}
```
![image](https://user-images.githubusercontent.com/80435655/149149255-25ef3a98-9b35-48e5-b9c5-9c30ae88a624.png)

# Inc16
```
CHIP Inc16 {
    IN in[16];
    OUT out[16];

    PARTS:
   // Put you code here:
   //Add16(a=in, b[0]=true, out=out);
   HalfAdder(a=in[0], b=true, carry=t1, sum=out[0]);
   HalfAdder(a=in[1], b=t1, carry=t2, sum=out[1]);
   HalfAdder(a=in[2], b=t2, carry=t3, sum=out[2]);
   HalfAdder(a=in[3], b=t3, carry=t4, sum=out[3]);
   HalfAdder(a=in[4], b=t4, carry=t5, sum=out[4]);
   HalfAdder(a=in[5], b=t5, carry=t6, sum=out[5]);
   HalfAdder(a=in[6], b=t6, carry=t7, sum=out[6]);
   HalfAdder(a=in[7], b=t7, carry=t8, sum=out[7]);
   HalfAdder(a=in[8], b=t8, carry=t9, sum=out[8]]);
   HalfAdder(a=in[9], b=t9, carry=t10, sum=out[9]);
   HalfAdder(a=in[10], b=t10, carry=t11, sum=out[10]);
   HalfAdder(a=in[11], b=t11, carry=t12, sum=out[11]);
   HalfAdder(a=in[12], b=t12, carry=t13, sum=out[12]);
   HalfAdder(a=in[13], b=t13, carry=t14, sum=out[13]);
   HalfAdder(a=in[14], b=t14, carry=t15, sum=out[14]);
   HalfAdder(a=in[15], b=t15, carry=t16, sum=out[15]);
}
```
![image](https://user-images.githubusercontent.com/80435655/149149279-8ab77775-e3b9-4106-b6ab-b1a0bf2297fb.png)
