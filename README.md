This is a project I worked on while I was taking a VLSI class where I learned the basics of full custom IC design. The goal of the project was to create a 16 bit CPU datapath with data forwarding from the end of the execute stage to the beginning on the TSMC 180nm process. The basic layout consists of the following sections.

    •	32 2-1 multiplexers to select between the data that would be coming from a register file and the forward data from the ALU
    •	32 master-slave flip flops to store the selected data to be passed to the ALU on the next clock cycle
    •	A right shifter capable of right shifting one of the inputs to the ALU by 0-3 bits
    •	A 4x4 carry select adder that was implemented with a single circuit computing the propagate and generate bits for two similar pieces       of sum logic where one was hardwired to have a 0 carry in and the other has a 1 carry in. Then a multiplexer selects the correct           output every 4 bits based on the actual carry in value.
    •	Finally the result value is passed into a buffer that drives the result all the way back to the beginning of the circuit and to some       other part of the chip such as a memory unit.
  
Overall the design was a great success achieving the fastest design in the class with a clock speed of ~580 MHz and the second smallest design with an area of 57.33um x 185.22um.

