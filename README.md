**SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS**

**AIM:**

 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Vivado 2023.3.

**APPARATUS REQUIRED:**

Vivado 2023.3
  
**PROCEDURE:**

STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.



**SR FLIPFLOP:**

**LOGIC DIAGRAM:**


![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

**VERILOG CODE:**


```
module srff(s,r,clk,rst,q);
input s,r,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({s,r})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=1'bX;
endcase
end
end
endmodule
```

**OUTPUT:**


![316233145-0f6d3c8a-68ed-42c1-950f-97b055ceaf98](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/2698bed3-00fe-4896-9660-97a03fa8f59e)


**JK FLIPFLOP:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

**VERILOG CODE:**

```
module jkff(j,k,clk,rst,q);
input j,k,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({j,k})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=~q;
endcase
end
end
endmodule
```

**OUTPUT:**

![316233162-f10f8a81-e7aa-44f7-a5ee-70f276eeb4ba](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/eabee665-b0bd-480c-a1c4-ebc525b793e6)

**T FLIPFLOP:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)

**VERILOG CODE:**

```
module tff(clk,rst,t,q);
input clk,rst,t;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else if (t==0)
q=q;
else
q=~q;
end
endmodule
```

**OUTPUT:**
![316233164-111a7a8f-4e01-4ac4-90c1-4a1a45d13115](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/17039deb-ff9e-4c1b-abc3-f017823259c9)


**D FLIPFLOP:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)

**VERILOG CODE:**

```
module dff(d,clk,rst,q);
input d,clk,rst;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else
q=d;
end
endmodule
```

**OUTPUT:**

![316233181-03c4477f-c15a-4898-9e11-df5f1ff4850a](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/ad754e58-5bad-4051-8e2b-d5dfc1d26472)

**COUNTER:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

**UPDOWN COUNTER:**

**LOGIC DIAGRAM:**

![image](https://github.com/Dhinesh0024/VLSI-LAB-EXP-4/assets/160568927/dd12585a-157f-4b6f-a0c3-b421bb52434c)


**VERILOG CODE:**

```
module udc(clk,rst,updown,out);
input clk,rst,updown;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1)
out=4'b0000;
else if(updown==1)
out=out+1;
else
out=out-1;
end
endmodule
```

**OUTPUT:**

![320868824-c37fe928-351f-4e40-bf5a-49491aab4bfc](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/f8652db4-8b09-4109-a4b6-dbe859fe93fc)


**MOD-10 COUNTER:**

**LOGIC DIAGRAM:**

![image](https://github.com/Dhinesh0024/VLSI-LAB-EXP-4/assets/160568927/3a4a4da2-7488-411d-8ea5-2e57c4fd942f)


**VERILOG CODE:**

```
module mod10(clk,rst,out);
input clk,rst;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1 | out==4'b1001)
out=4'b0000;
else
out=out+1;
end
endmodule
```

**OUTPUT:**

![320869850-c6465024-ee28-4781-ba9a-9bec97dd2c1a](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/c6b15328-16ba-45d4-9006-5cc53eb3b816)


**RIPPLE CARRY COUNTER:**

**LOGIC DIAGRAM:**

![320877668-129b1a22-407f-4f38-adff-b4dbf3595eb7](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/f672f89e-cd95-41b1-a295-82cdaa18035d)



![320877790-fecad9d3-7f49-4c98-91f4-443803a60e37](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/518e3451-1cc3-454d-8205-6a9c7e949b53)



**VERILOG CODE:**

```
module tff(q,clk,rst);
input clk,rst;
output q;
wire d;
dff df1(q,d,clk,rst);
not n1(d,q);
endmodule

module dff(q,d,clk,rst);
input d,clk,rst;
output q;
reg q;
always @(posedge clk or posedge rst)
begin
if (rst)
q=1'b0;
else 
q=d;
end
endmodule

module rcc(clk,rst,q);
input clk,rst;
output [3:0]q;
tff tf1(q[0],clk,rst);
tff tf2(q[1],q[0],rst);
tff tf3(q[2],q[1],rst);
tff tf4(q[3],q[2],rst);
endmodule
```

**OUTPUT:**

![320874442-4a1a2d79-9e4d-4b0a-bda9-64bb19952f67](https://github.com/vishwajayakumar/VLSI-LAB-EXP-4/assets/169515345/e48d0080-576e-47fc-9b01-2235a7e6dc02)


**RESULT:**

 Hence SR, JK, T, D - FLIPFLOP, COUNTER DESIGN are simulated and synthesised using Vivado 2023.2


