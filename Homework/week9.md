# Memory
```
CHIP Memory {
    IN in[16], load, address[15];
    OUT out[16];

    PARTS:
    // Put your code here:
    DMux(in=load,sel=address[14],a=RRun,b=SKRun);
    DMux(in=SKRun,sel=address[13],a=SRun,b=n);

    RAM16K(in=in, load=RRun, address=address[0..13], out=ROut);
    Screen(in=in, load=SRun, address=address[0..12], out=SOut);
    Keyboard(out=kbo); //24576

    Mux16(a=SOut, b=kbo, sel=address[13], out=temp);
    Mux16(a=ROut, b=temp, sel=address[14], out=out);
}
```
![image](https://user-images.githubusercontent.com/80435655/149156200-f9fa62d7-3a6f-4f9c-b9ee-8b2f12004545.png)

# Computer
```
CHIP Computer {

    IN reset;

    PARTS:
    // Put your code here:
    CPU(instruction=instructionR, reset=reset, inM=MeOut, writeM=CPUw, outM=CPUOut, addressM=CPUaddr, pc=CPUp);
    Memory(in=CPUOut, load=CPUw, address=CPUaddr, out=MeOut);
    ROM32K(address=CPUp, out=instructionR);
}
```

# ComputerAdd

```
| time |reset|ARegister|DRegister|PC[]|RAM16K[0]|RAM16K[1]|RAM16K[2]|
| 0    |  0  |       0 |       0 |   0|       0 |       0 |       0 |
| 1    |  0  |       2 |       0 |   1|       0 |       0 |       0 |
| 2    |  0  |       2 |       2 |   2|       0 |       0 |       0 |
| 3    |  0  |       3 |       2 |   3|       0 |       0 |       0 |
| 4    |  0  |       3 |       5 |   4|       0 |       0 |       0 |
| 5    |  0  |       0 |       5 |   5|       0 |       0 |       0 |
| 6    |  0  |       0 |       5 |   6|       5 |       0 |       0 |
| 7    |  1  |       0 |       5 |   0|       0 |       0 |       0 |
| 8    |  0  |       2 |       5 |   1|       0 |       0 |       0 |
| 9    |  0  |       2 |       2 |   2|       0 |       0 |       0 |
| 10   |  0  |       3 |       2 |   3|       0 |       0 |       0 |
| 11   |  0  |       3 |       5 |   4|       0 |       0 |       0 |
| 12   |  0  |       0 |       5 |   5|       0 |       0 |       0 |
| 13   |  0  |       0 |       5 |   6|       5 |       0 |       0 |
```
# ComputerMax
```
| time |reset|ARegister|DRegister|PC[]|RAM16K[0]|RAM16K[1]|RAM16K[2]|
| 0    |  0  |       0 |       0 |   0|       3 |       5 |       0 |
| 1    |  0  |       0 |       0 |   1|       3 |       5 |       0 |
| 2    |  0  |       0 |       3 |   2|       3 |       5 |       0 |
| 3    |  0  |       1 |       3 |   3|       3 |       5 |       0 |
| 4    |  0  |       1 |      -2 |   4|       3 |       5 |       0 |
| 5    |  0  |      10 |      -2 |   5|       3 |       5 |       0 |
| 6    |  0  |      10 |      -2 |   6|       3 |       5 |       0 |
| 7    |  0  |       1 |      -2 |   7|       3 |       5 |       0 |
| 8    |  0  |       1 |       5 |   8|       3 |       5 |       0 |
| 9    |  0  |      12 |       5 |   9|       3 |       5 |       0 |
| 10   |  0  |      12 |       5 |  12|       3 |       5 |       0 |
| 11   |  0  |       2 |       5 |  13|       3 |       5 |       0 |
| 12   |  0  |       2 |       5 |  14|       3 |       5 |       5 |
| 13   |  0  |      14 |       5 |  15|       3 |       5 |       5 |
| 14   |  0  |      14 |       5 |  14|       3 |       5 |       5 |
| 15   |  1  |      14 |       5 |   0|       3 |       5 |       5 |
| 15   |  0  |      14 |       5 |   0|   23456 |   12345 |       5 |
| 16   |  0  |       0 |       5 |   1|   23456 |   12345 |       5 |
| 17   |  0  |       0 |   23456 |   2|   23456 |   12345 |       5 |
| 18   |  0  |       1 |   23456 |   3|   23456 |   12345 |       5 |
| 19   |  0  |       1 |   11111 |   4|   23456 |   12345 |       5 |
| 20   |  0  |      10 |   11111 |   5|   23456 |   12345 |       5 |
| 21   |  0  |      10 |   11111 |  10|   23456 |   12345 |       5 |
| 22   |  0  |       0 |   11111 |  11|   23456 |   12345 |       5 |
| 23   |  0  |       0 |   23456 |  12|   23456 |   12345 |       5 |
| 24   |  0  |       2 |   23456 |  13|   23456 |   12345 |       5 |
| 25   |  0  |       2 |   23456 |  14|   23456 |   12345 |   23456 |
```
# ComputerRect
```
| time |ARegister|DRegister|PC[]|RAM16K[0]|RAM16K[1]|RAM16K[2]|
| 0    |       0 |       0 |   0|       4 |       0 |       0 |
| 1    |       0 |       0 |   1|       4 |       0 |       0 |
| 2    |       0 |       4 |   2|       4 |       0 |       0 |
| 3    |      23 |       4 |   3|       4 |       0 |       0 |
| 4    |      23 |       4 |   4|       4 |       0 |       0 |
| 5    |      16 |       4 |   5|       4 |       0 |       0 |
| 6    |      16 |       4 |   6|       4 |       0 |       0 |
| 7    |   16384 |       4 |   7|       4 |       0 |       0 |
| 8    |   16384 |   16384 |   8|       4 |       0 |       0 |
| 9    |      17 |   16384 |   9|       4 |       0 |       0 |
| 10   |      17 |   16384 |  10|       4 |       0 |       0 |
| 11   |      17 |   16384 |  11|       4 |       0 |       0 |
| 12   |   16384 |   16384 |  12|       4 |       0 |       0 |
| 13   |   16384 |   16384 |  13|       4 |       0 |       0 |
| 14   |      17 |   16384 |  14|       4 |       0 |       0 |
| 15   |      17 |   16384 |  15|       4 |       0 |       0 |
| 16   |      32 |   16384 |  16|       4 |       0 |       0 |
| 17   |      32 |   16416 |  17|       4 |       0 |       0 |
| 18   |      17 |   16416 |  18|       4 |       0 |       0 |
| 19   |      17 |   16416 |  19|       4 |       0 |       0 |
| 20   |      16 |   16416 |  20|       4 |       0 |       0 |
| 21   |      16 |       3 |  21|       4 |       0 |       0 |
| 22   |      10 |       3 |  22|       4 |       0 |       0 |
| 23   |      10 |       3 |  10|       4 |       0 |       0 |
| 24   |      17 |       3 |  11|       4 |       0 |       0 |
| 25   |   16416 |       3 |  12|       4 |       0 |       0 |
| 26   |   16416 |       3 |  13|       4 |       0 |       0 |
| 27   |      17 |       3 |  14|       4 |       0 |       0 |
| 28   |      17 |   16416 |  15|       4 |       0 |       0 |
| 29   |      32 |   16416 |  16|       4 |       0 |       0 |
| 30   |      32 |   16448 |  17|       4 |       0 |       0 |
| 31   |      17 |   16448 |  18|       4 |       0 |       0 |
| 32   |      17 |   16448 |  19|       4 |       0 |       0 |
| 33   |      16 |   16448 |  20|       4 |       0 |       0 |
| 34   |      16 |       2 |  21|       4 |       0 |       0 |
| 35   |      10 |       2 |  22|       4 |       0 |       0 |
| 36   |      10 |       2 |  10|       4 |       0 |       0 |
| 37   |      17 |       2 |  11|       4 |       0 |       0 |
| 38   |   16448 |       2 |  12|       4 |       0 |       0 |
| 39   |   16448 |       2 |  13|       4 |       0 |       0 |
| 40   |      17 |       2 |  14|       4 |       0 |       0 |
| 41   |      17 |   16448 |  15|       4 |       0 |       0 |
| 42   |      32 |   16448 |  16|       4 |       0 |       0 |
| 43   |      32 |   16480 |  17|       4 |       0 |       0 |
| 44   |      17 |   16480 |  18|       4 |       0 |       0 |
| 45   |      17 |   16480 |  19|       4 |       0 |       0 |
| 46   |      16 |   16480 |  20|       4 |       0 |       0 |
| 47   |      16 |       1 |  21|       4 |       0 |       0 |
| 48   |      10 |       1 |  22|       4 |       0 |       0 |
| 49   |      10 |       1 |  10|       4 |       0 |       0 |
| 50   |      17 |       1 |  11|       4 |       0 |       0 |
| 51   |   16480 |       1 |  12|       4 |       0 |       0 |
| 52   |   16480 |       1 |  13|       4 |       0 |       0 |
| 53   |      17 |       1 |  14|       4 |       0 |       0 |
| 54   |      17 |   16480 |  15|       4 |       0 |       0 |
| 55   |      32 |   16480 |  16|       4 |       0 |       0 |
| 56   |      32 |   16512 |  17|       4 |       0 |       0 |
| 57   |      17 |   16512 |  18|       4 |       0 |       0 |
| 58   |      17 |   16512 |  19|       4 |       0 |       0 |
| 59   |      16 |   16512 |  20|       4 |       0 |       0 |
| 60   |      16 |       0 |  21|       4 |       0 |       0 |
| 61   |      10 |       0 |  22|       4 |       0 |       0 |
| 62   |      10 |       0 |  23|       4 |       0 |       0 |
| 63   |      23 |       0 |  24|       4 |       0 |       0 |
```
