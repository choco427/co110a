# NOT16

```
CHIP Not16 {
    IN in[16];
    OUT out[16];

    PARTS:
    // Put your code here:
    Not(in=in[0], out=out[0]);
    Not(in=in[1], out=out[1]);
    Not(in=in[2], out=out[2]);
    Not(in=in[3], out=out[3]);
    Not(in=in[4], out=out[4]);
    Not(in=in[5], out=out[5]);
    Not(in=in[6], out=out[6]);
    Not(in=in[7], out=out[7]);
    Not(in=in[8], out=out[8]);
    Not(in=in[9], out=out[9]);
    Not(in=in[10], out=out[10]);
    Not(in=in[11], out=out[11]);
    Not(in=in[12], out=out[12]);
    Not(in=in[13], out=out[13]);
    Not(in=in[14], out=out[14]);
    Not(in=in[15], out=out[15]);
}
```
![image](https://user-images.githubusercontent.com/80435655/149146830-736af46c-3c6d-467a-bbbe-56fa0a84b116.png)

# And16

```
CHIP And16 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
    // Put your code here:
    And(a=a[0] ,b=b[0] ,out=out[0]);
    And(a=a[1] ,b=b[1] ,out=out[1]);
    And(a=a[2] ,b=b[2] ,out=out[2]);
    And(a=a[3] ,b=b[3] ,out=out[3]);
    And(a=a[4] ,b=b[4] ,out=out[4]);
    And(a=a[5] ,b=b[5] ,out=out[5]);
    And(a=a[6] ,b=b[6] ,out=out[6]);
    And(a=a[7] ,b=b[7] ,out=out[7]);
    And(a=a[8] ,b=b[8] ,out=out[8]);
    And(a=a[9] ,b=b[9] ,out=out[9]);
    And(a=a[10] ,b=b[10] ,out=out[10]);
    And(a=a[11] ,b=b[11] ,out=out[11]);
    And(a=a[12] ,b=b[12] ,out=out[12]);
    And(a=a[13] ,b=b[13] ,out=out[13]);
    And(a=a[14] ,b=b[14] ,out=out[14]);
    And(a=a[15] ,b=b[15] ,out=out[15]);
}
```
![image](https://user-images.githubusercontent.com/80435655/149146874-a6fa7511-bd1d-476a-878e-486fa472af2c.png)

# Or16

```
CHIP Or16 {
    IN a[16], b[16];
    OUT out[16];

    PARTS:
    // Put your code here:
    Or(a=a[0] ,b=b[0] ,out=out[0]);
    Or(a=a[1] ,b=b[1] ,out=out[1]);
    Or(a=a[2] ,b=b[2] ,out=out[2]);
    Or(a=a[3] ,b=b[3] ,out=out[3]);
    Or(a=a[4] ,b=b[4] ,out=out[4]);
    Or(a=a[5] ,b=b[5] ,out=out[5]);
    Or(a=a[6] ,b=b[6] ,out=out[6]);
    Or(a=a[7] ,b=b[7] ,out=out[7]);
    Or(a=a[8] ,b=b[8] ,out=out[8]);
    Or(a=a[9] ,b=b[9] ,out=out[9]);
    Or(a=a[10] ,b=b[10] ,out=out[10]);
    Or(a=a[11] ,b=b[11] ,out=out[11]);
    Or(a=a[12] ,b=b[12] ,out=out[12]);
    Or(a=a[13] ,b=b[13] ,out=out[13]);
    Or(a=a[14] ,b=b[14] ,out=out[14]);
    Or(a=a[15]] ,b=b[15] ,out=out[15]);
}
```
![image](https://user-images.githubusercontent.com/80435655/149146907-eecaac71-dde4-4a6d-b8cd-56a4fd38b5c0.png)

# Mux16

```
CHIP Mux16 {
    IN a[16], b[16], sel;
    OUT out[16];

    PARTS:
    // Put your code here:
    Mux(a=a[0], b=b[0], sel=sel, out=out[0]);
    Mux(a=a[1], b=b[1], sel=sel, out=out[1]);
    Mux(a=a[2], b=b[2], sel=sel, out=out[2]);
    Mux(a=a[3], b=b[3], sel=sel, out=out[3]);
    Mux(a=a[4], b=b[4], sel=sel, out=out[4]);
    Mux(a=a[5], b=b[5], sel=sel, out=out[5]);
    Mux(a=a[6], b=b[6], sel=sel, out=out[6]);
    Mux(a=a[7], b=b[7], sel=sel, out=out[7]);
    Mux(a=a[8], b=b[8], sel=sel, out=out[8]);
    Mux(a=a[9], b=b[9], sel=sel, out=out[9]);
    Mux(a=a[10], b=b[10], sel=sel, out=out[10]);
    Mux(a=a[11], b=b[11], sel=sel, out=out[11]);
    Mux(a=a[12], b=b[12], sel=sel, out=out[12]);
    Mux(a=a[13], b=b[13], sel=sel, out=out[13]);
    Mux(a=a[14], b=b[14], sel=sel, out=out[14]);
    Mux(a=a[15], b=b[15], sel=sel, out=out[15]);
}
```
![image](https://user-images.githubusercontent.com/80435655/149146932-f8da8211-256f-459b-8c59-90b75c71df61.png)

# Or8Way

```
CHIP Or8Way {
    IN in[8];
    OUT out;

    PARTS:
    // Put your code here:
    Or(a=in[0], b=in[1], out=t1);
    Or(a=in[2], b=in[3], out=t2);
    Or(a=in[4], b=in[5], out=t3);
    Or(a=in[6], b=in[7], out=t4);
    Or(a=t1, b=t2, out=t5);
    Or(a=t3, b=t4, out=t6);
    Or(a=t5, b=t6, out=out);
}
```
![image](https://user-images.githubusercontent.com/80435655/149146960-56a04e02-22ed-4974-971b-cdee81a133e7.png)

# Mux4Way16

```
CHIP Mux4Way16 {
    IN a[16], b[16], c[16], d[16], sel[2];
    OUT out[16];

    PARTS:
    // Put your code here:
    Mux16(a=a, b=b, sel=sel[0], out=t1);
    Mux16(a=c, b=d, sel=sel[0], out=t2);
    Mux16(a=t1, b=t2, sel=sel[1], out=out);
}

```
![image](https://user-images.githubusercontent.com/80435655/149147138-427b4d10-f57a-451b-ae97-274d3f008f69.png)

# Mux8Way16

```
CHIP Mux8Way16 {
    IN a[16], b[16], c[16], d[16],
       e[16], f[16], g[16], h[16],
       sel[3];
    OUT out[16];

    PARTS:
    // Put your code here:
    Mux4Way16(a=a, b=b, c=c, d=d, sel[0]=sel[0], sel[1]=sel[1], out=t1);
    Mux4Way16(a=e, b=f, c=g, d=h, sel[0]=sel[0], sel[1]=sel[1], out=t2);
    Mux16(a=t1, b=t2, sel=sel[2], out=out);
}
```
![image](https://user-images.githubusercontent.com/80435655/149147161-66851d3d-9775-4f71-b41d-1da960ebd9e9.png)

# DMux4Way

```
CHIP DMux4Way {
    IN in, sel[2];
    OUT a, b, c, d;

    PARTS:
    // Put your code here:
    DMux(in=in, sel=sel[0], a=a, b=b);
    DMux(in=in, sel=sel[1], a=c, b=d);
}
```
![image](https://user-images.githubusercontent.com/80435655/149147283-a86bece6-15a9-47f8-aa4d-b6dac64414b8.png)

# DMux8Way

```
CHIP DMux8Way {
    IN in, sel[3];
    OUT a, b, c, d, e, f, g, h;

    PARTS:
    // Put your code here:
    DMux(in=in, sel=sel[2], a=t1, b=t2);
    DMux(in=t1, sel=sel[0], a=a, b=b);
    DMux(in=t2, sel=sel[0], a=e, b=f);
    DMux(in=t1, sel=sel[1], a=c, b=d);
    DMux(in=t2, sel=sel[1], a=g, b=h);
}
```
![image](https://user-images.githubusercontent.com/80435655/149147307-407a4e6b-a8f8-41f7-9f28-ec63569af143.png)

# 迪摩根定律
![image](https://user-images.githubusercontent.com/80435655/149147328-174fc8a0-07ab-4cd2-a2bf-1c4bf76c6e5d.png)

# 七段顯示器--e
![image](https://user-images.githubusercontent.com/80435655/149147344-41a748a4-7035-4811-ad25-0dcd6597ea96.png)
![image](https://user-images.githubusercontent.com/80435655/149147359-355f5539-a814-4977-8dda-f454f23f8ecf.png)

