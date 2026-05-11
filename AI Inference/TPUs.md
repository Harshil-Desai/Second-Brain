Google built their own AI chip, called TPU (Tensor processing Unit), it has a specific purpose, Matrix Multiplication with max efficiency. 

Systolic Array: [[Systolic Array.excalidraw]]

![[Pasted image 20260511230959.png]]

There is only one trade-off that TPU cannot do anything else. But for matrix multiplication its a beast. 

Now google has announced that there will be 2 different types of TPU chips for different type of work. TPU 8t for [[training]] and TPU 8i for [[inference]].

In 8t, there are 9600 chips, 2PB of shared high bandwidth memory, 121 exaflop of total compute, which completes training a model in weeks, rather than months.

In 8i there are 1152 chip, but it has a 384 MB SRAM, low latency token generation.

Both chips runs on google's Axion ARM host CPU.
