# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### PROCEDURE
1.Create a new project in QuartusII software.
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module as dc and uc for down counter and up counter.
5.Within the module declare input and output variables.
6.Create a loop using if-else with condition parameter as reset value.
7.End the loop.
8.End the module.





### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:G.R.Nandhakumar
RegisterNumber:212222100029 
```
### UP COUNTER
```
module sync(clk,A);
input clk;
output reg [0:2]A;
always@(posedge clk)
begin
    A[0]=(((A[1])&(A[2]))^A[0]);
	 A[1]=(A[2])^(A[1]);
	 A[2]=1^A[2];
end 
endmodule
```
### DOWN COUNTER
```
module exp6a(clk,A);
input clk;
output reg [0:2]A;
always@(posedge clk)
begin
    A[0]=(((~A[1])&(~A[2]))^(A[0]));
	 A[1]=(~A[2])^(A[1]);
	 A[2]=1^A[2];
end 
endmodule 
```


### RTL LOGIC UP COUNTER AND DOWN COUNTER  
### UP COUNTER
![Screenshot (112)](https://github.com/Nandhakumar1313/Exp-7-Synchornous-counters-/assets/120230694/d0039483-6444-49ec-8591-3b22fc63e1b0)

### DOWN COUNTER
![Screenshot (123)](https://github.com/Nandhakumar1313/Exp-7-Synchornous-counters-/assets/120230694/4a5ee3e6-30b0-4553-aec5-e15abaa5dc5b)




### TIMING DIGRAMS FOR COUNTER  
### UP COUNTER
![Screenshot (113)](https://github.com/Nandhakumar1313/Exp-7-Synchornous-counters-/assets/120230694/402e1e0b-3050-498a-a4f0-422d7f042d95)

### DOWN COUNTER
![Screenshot (122)](https://github.com/Nandhakumar1313/Exp-7-Synchornous-counters-/assets/120230694/90e54a37-ddbc-44ba-ae38-f9b257a8cb51)



### TRUTH TABLE 
### UP COUNTER
![240863821-9369055d-615d-49ba-ba8f-4c0e5554a1b4](https://github.com/Nandhakumar1313/Exp-7-Synchornous-counters-/assets/120230694/911ea905-b662-4bf6-8448-c3f0bb081590)

### DOWN COUNTER

![240863898-bb28b117-6684-4410-a74b-14f15032aa89](https://github.com/Nandhakumar1313/Exp-7-Synchornous-counters-/assets/120230694/cd28cb60-b7ef-4dfb-a184-e877fa3e363a)




### RESULTS 
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
