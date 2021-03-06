[Rocket](../Readme.md)/[rocket](../rocket.md)/[IBuf](https://github.com/freechipsproject/rocket-chip/blob/master/src/main/scala/rocket/IBuf.scala)
========================
*A buffer in between of IF and ID to handle RVC.*

*****************

class Instruction
--------------------
*Instruction data struction from instruction fetch unit.*


+ Bundle component

| name                   | type             | description                           |
| :---                   | :--:             | :---                                  |
| pf0                    | Bool             | page fault on the first half of instruction |
| pf1                    | Bool             | page fault on the second half of instruction |
| ae0                    | Bool             | access exception on the first half of instruction |
| ae1                    | Bool             | access exception on the second half of instruction |
| replay                 | Bool             | replay this instruction due to instruction cache |
| btb\_hit               | Bool             | indicated a predicted branch target (taken) |
| rvc                    | Bool             | RVC instructions                      |
| inst                   | [ExpandedInstruction](./RVC.md#class-expandedinstruction) | expanded instruction               |
| raw                    | UInt             | raw instruction                       |

class IBuf
-------------------------
*Buffer for decoding RVC instructions*
**This module is not fully implemented yet.**

+ I/O, type and parameters

| name                   | type             | direction  | description                           |
| :---                   | :--:             | :--:       | :---                                  |
| p                      | Parameters       | param      | configuration                         |
| imem                   | DecoupledIO[FrontendResp] | I | fetched instructiond from instruction cache |
| kill                   | Bool             | I          | kill instructions from core pipe      |
| pc                     | UInt             | O          | current PC of IF                      |
| btb\_resp              | BTBResp          | O          | update to BTB for RAS                 |
| inst                   | Vec[DecoupledIO[[Instruction](#class-instruction)]] | O | instructions for core pipe        |



<br><br><br><p align="right">
<sub>
Last updated: 08/07/2017<br>
[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/), &copy; (2017) [Wei Song](mailto:wsong83@gmail.com)<br>
[Apache 2.0](https://github.com/freechipsproject/rocket-chip/blob/master/LICENSE.SiFive), &copy; (2016-2017) SiFive, Inc<br>
[BSD](https://github.com/freechipsproject/rocket-chip/blob/master/LICENSE.Berkeley), &copy; (2012-2014, 2016) The Regents of the University of California (Regents)
</sub>
</p>
