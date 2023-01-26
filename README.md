# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
1.create module encoder decoder
2.get inputs outputs for encoder decoders
3.perform or operation for encoder and logic fordecoder
4.perform rtl logic and get waveform

### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: panimalar.p
RegisterNumber:  22009107
*/
~~~
module encoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7); 
or(c,d1,d3,d5,d7); 
endmodule


module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(~a&~b&~c);
assign d1=(~a&~b&c);
assign d2=(~a&b&~c);
assign d3=(~a&b&c);
assign d4=(a&~b&~c);
assign d5=(a&~b&c);
assign d6=(a&b&~c);
assign d7=(a&b&c);
endmodule
~~~
### RTL LOGIC  



![Screenshot (196)](https://user-images.githubusercontent.com/121490826/214824697-46c226e4-e6b5-4411-9a5c-0715e6702b69.png)



![Screenshot (167)](https://user-images.githubusercontent.com/121490826/214824391-6b8350bd-caa8-4901-ac4b-7beb106b5648.png)


### TIMING DIGRAMS  
![Screenshot (168)](https://user-images.githubusercontent.com/121490826/214824502-9c44547f-4f35-42c9-baff-1e5e49ee2dbe.png)



![Screenshot (195)](https://user-images.githubusercontent.com/121490826/214824298-400834ae-5831-4b1e-8f2b-5857316cdb85.png)


### TRUTH TABLE 

![Screenshot (200)](https://user-images.githubusercontent.com/121490826/214825134-552aa849-cf46-4ec6-9bc0-94c70abd58a5.png)


![Screenshot (199)](https://user-images.githubusercontent.com/121490826/214825154-f2915de8-a6f7-4fb6-994e-038fb118a84e.png)



### RESULTS 
Thus the program to desing encoder decoder is done.
