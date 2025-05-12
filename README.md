# verilog-lab-4-registers-solved
**TO GET THIS SOLUTION VISIT:** [Verilog Lab 4-Registers Solved](https://www.ankitcodinghub.com/product/verilog-lab-4-registers-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;91443&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Verilog Lab 4-Registers Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
Lab 4 Registers

In this lab you will use registers in a couple of applications. The first is a register file and the second is an accumulator. You will test both applications on the FPGA board.

Pushbuttons

When pushbuttons are used in synchronous digital circuits, they introduce a few issues.

<ol>
<li>A user can push the button at any time regardless of the clock, if the push button is used
as input to a storage element, timing violations might occur and that might result in

metastability (more on that in later weeks). This issue can be fixed with a synchronizer.
</li>
<li>Pushbuttons are mechanical buttons, and they might bounce around a value. For
example, if pressing a button should yield logic 1, the actual value might bounce between 0 and 1 for a short time, then stabilizes at 1. This issue can be fixed with a debouncer.
</li>
<li>Pushbuttons are sometimes used to enable a single action (i.e., load a register with a single value) regardless of how many clock cycles pass. This needs an edge detector circuit that converts the pushbutton level to a single clock cycle enable signal. In other words, pressing a button will result in a short pulse regardless of how long the user keeps the button pressed.</li>
</ol>
The included button.v file is an all-in-one synchronizer, deobouncer, and edge-detector, it solve all issues mentioned above. The circuit takes a clock and a pushbutton as inputs and converts the pushbutton assertion to a single cycle pulse. Run the button_tb.v testbench to see it in action.

The circuit is based on a right shift register with a special output logic. The shift register can be of any size, the size can be changed by changing the local parameter N and you might want to change the size depending on your application. At the output, the shift register value is checked for a pattern of ones followed by a single 0. This means that a button was in logic 0 then was pressed and held for N-1 clock cycles at logic 1. For example, when N = 3, the output will be asserted when it sees 110, which means the button was pressed and held for 2 clock cycles after it was at logic 0. If the button was held for longer, the content of the register will be 111 and the output pulse will be returned to 0.

You should use this circuit in the following parts whenever you are using a pushbutton.

</div>
</div>
<div class="layoutArea">
<div class="column">
1

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
Part 1 (Building a register file)

Processors contain an array of registers called a register file. They are usually implemented using RAM. However, in this part, you will build a register file using regular registers with flip- flops.

Figure 1: Register File

Figure 1 shows a register file that contains 2N registers (rows) and each row is of size BITS (columns). This particular implementation utilizes two ports, a write port and a read port. The dual ports allow a user to access the register file for reading and writing simultaneously.

You can write a new word into the register file by placing it at data_w and specifing the write address on address_w, asserting WE will then invoke the write operation. A similar process can be used for reading a word from the register file, place an address on address_r and data_r will have the word stored at that address.

Generic Register File

1. Build a generic register file (call it reg_file) that takes two parameters N and BITS. 2. The generic register file should utilize 2N registers and each of the registers should be of

size BITS.

3. The write port can be implemented using an Nx2N binary decoder.

4. The read port can be implemented using an Nx2N binary decoder and a 2N Tri-State

Buffers.

5. Use the following provided code:

a. simple_register_load.v for the base registers

b. decoder_generic.v whenever you need a decoder

c. You need to figure out how a tri-state buffer works. Hint: the following

implements a tri-state buffer of input a and output b assign b = (enable) ? a : 1’bz;

</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
6. Include a schematic diagram of your design with your submission

Register File Application

Verify the functionality of the register file by implementing it on the FPGA board:

1. Place your implementation in a new file called reg_file_application.v 2. Instantiate a version of the register file that contains 128 rows with 4 bits each. 3. SW3  SW0 should be connected to data_w

4. SW10  SW4 should be used to specify address_w or address_r. There isn’t

enough switches on the board to separate the addresses, so you will have to

demultiplex them

5. SW15 should be used to specify which address is being specified on SW10SW4. For

example if SW15 is 1’b1 then the adderss at SW10SW4 is the read address

6. The down push button should be connected to WE

7. The data_r should be displayed on one of the seven segment digits. Use the provided

hex2sseg.v

Question: How many Flip-Flops are being used on the board? Look at the utilizing report to figure out the answer.

</div>
</div>
<div class="layoutArea">
<div class="column">
3

</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
Part 2 (Building an Accumulator)

Many processors contain a special function register called an accumulator (you might have seen it called a working register). The register stores the result of the last operation and might also be used in following operations.

Figure 2: 4-bit accumulator

Figure 2 shows a diagram of a simple accumulator that can store and accumulate the result from an adder/subtractor. Build this accumulator and test it on the FPGA board using the following specifications:

<ul>
<li>User a 4-bit register</li>
<li>Use a 4-bit adder/subtractor. You can use the provided adder_subtractor.v</li>
<li>SW3SW0 should be connected to input X</li>
<li>SW15 should be connected to the Add/Sub input</li>
<li>loadshouldbeconnectedtothedownpushbutton</li>
<li>reset_nshouldbeconnectedtotheresetbutton</li>
<li>You should display the value stored in the accumulator on one of the seven segment
digits

Submission check list:

[ ] All Verilog code you generated or modified

[ ] All testbenches written

[ ] Embed all screenshot of your testbench output in your README.md

[ ] Embed all block diagram generated in your README.md

[ ] Short videos demonstrating each of the parts you implemented on the FPGA
</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
