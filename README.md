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
![image](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/0a16658e-46ae-4560-9589-c4c5c829fdab)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
```
Step 1: Module Declaration. module is a keywords defined in Verilog . 
Step 2: Input-Output Delecaration. Clock and reset are the inputs. 
Step 3: Declare the always keyword. 
Step 4: Use if loop for the functionality.
Step 5: Assign the counter_up & _down.
Step 6: End the module
```




### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:SUBASHINI.S
RegisterNumber:22009344
*/
```
### UP COUNTER
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



### DOWN COUNTER

module exp6a(clk,A);
input clk;
output reg [0:2]A;
always@(posedge clk)
begin
    A[0]=(((~A[1])&(~A[2]))^(A[0]));
	 A[1]=(~A[2])^(A[1]);
	 A[2]=1^A[2];






### RTL LOGIC UP COUNTER AND DOWN COUNTER:
UP COUNTER:

![image](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/f36d4427-18a2-4193-ab90-edd48e327ece)



DOWNCOUNTER:

![image](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/b4544253-b309-416d-9388-34a4e67e3a2a)






### TIMING DIGRAMS FOR COUNTER  
UP COUNTER

![242934123-cd3fbd22-8dfc-4a96-8b01-0905ddaf2397](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/ffeeae57-260e-40ad-9400-dd0290178685)

DOWNCOUNTER

![242934173-565a7f68-0a41-41fc-a818-ba32bce5b1ef](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/2e03670d-f2d4-4d87-a135-c52d3c213e87)





### TRUTH TABLE:
UP COUNTER
![242934277-32e6c4c3-283d-41ec-8f1a-b4745dc1dd58](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/8b9fd121-13fe-4790-abf5-9ece676be95c)

DOWN COUNTER

![242934306-66ac536d-6415-466d-acbb-7f6464533cae](https://github.com/SubashiniSenniappan/Exp-7-Synchornous-counters-/assets/119404951/4c6e97c1-cf53-41f1-b0d1-b54d53f13b55)

### RESULTS:
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.












### TRUTH TABLE 






### RESULTS 
