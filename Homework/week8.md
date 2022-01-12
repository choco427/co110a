# CPU
```
CHIP CPU {

    IN  inM[16],         // M value input  (M = contents of RAM[A])
        instruction[16], // Instruction for execution
        reset;           // Signals whether to re-start the current
                         // program (reset==1) or continue executing
                         // the current program (reset==0).

    OUT outM[16],        // M value output
        writeM,          // Write to M? 
        addressM[15],    // Address in data memory (of M)
        pc[15];          // address of next instruction

    PARTS:
    // Put your code here:
    
    //ARegister更新
    Not(in=instruction[15] ,out=Alc1);                    //條件一:輸入非指令
    And(a=instruction[15],b=instruction[5],out=Alc2);     //條件二:輸入為指令且要求存於A
    Or(a=Alc1 ,b=Alc2 ,out=Aload);                        //滿足任一A更新
    Mux16(b=instruction ,a=aout ,sel=Alc1 ,out=Ain);      //滿足條件一時，A輸入為instruction，不滿足為ALU運算結果
    ARegister(in=Ain ,load=Aload ,out[0..14]=addressM ,out=Adata);

    //DRegister更新
    And(a=instruction[15],b=instruction[4],out=Dlc);      //輸入為指令且要求存於D時，D更新
    DRegister(in=aout ,load=Dlc ,out=Ddata);

    //ALU運算
    Mux16(b=inM,a=Adata,sel=instruction[12],out=ay);      //判斷對A or M
    ALU(x=Ddata ,y=ay ,zx=instruction[11] ,nx=instruction[10] ,zy=instruction[9] ,ny=instruction[8] ,f=instruction[7] ,no=instruction[6] ,out=aout ,out=outM ,out[15]=com,zr=equal,ng=less); //ALU運算

    //判斷是否大於0
    Or(a=equal,b=less,out=nmore);
    Not(in=nmore,out=more);

    //跳躍指令
    And(a=instruction[0],b=more,out=con0);
    And(a=instruction[1],b=equal,out=con1);
    And(a=instruction[2],b=less,out=con2);
    Or(a=con0,b=con1,out=con01);
    Or(a=con01,b=con2,out=con012);
    And(a=con012,b=instruction[15],out=PCload);

    //PC
    PC(in=Adata ,load=PCload ,inc=true ,reset=reset ,out[0..14]=pc);

    //writeM
    And(a=instruction[3],b=instruction[15],out=writeM);
}
```
![image](https://user-images.githubusercontent.com/80435655/149153271-ef3d4226-1e44-48a0-851a-662a654031be.png)
