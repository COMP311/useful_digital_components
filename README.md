<!-- omit in toc -->
# Useful Digital components

This document explains useful components in Digital.

<details open>
    <summary>Contents</summary>

- [Tunnel](#tunnel)
- [Splitter/merger](#splittermerger)
  - [Ungraded exercise](#ungraded-exercise)
    - [Testing](#testing)

</details>

## Tunnel

The Tunnel component (Components > Wires > Tunnel) will save you a lot of time debugging by simplifying your circuit wiring.

A tunnel is like an invisible wire between two points. For example, these two circuits are logically equivalent:

<p align="center">
  <img src="https://i.imgur.com/QMht3mK.png">
</p>

<p align="center">
  <img src="https://i.imgur.com/Uroonpl.png">
</p>

Perhaps this doesn't immediately seem useful. However, consider the following two circuits, one without tunnels and one with tunnels:

<p align="center">
  <img src="https://i.imgur.com/yhsAHK1.png">
</p>

<p align="center">
  <img src="https://i.imgur.com/I8YNwgt.png">
</p>

The two circuits are logically equivalent, but the latter is clearly easier to construct, read, and debug.

All tunnels with the same name (which you can set by right-clicking the Tunnel) are connected and have the same value.

Please use tunnels when constructing circuits!

## Splitter/merger

In the first few labs, we will see only 1-bit values on inputs, outputs, and wires. However, multi-bit values are common. For example, a 32-bit number in your computer can be represented as 32 wires that each carry 1 bit. However, we do not want to draw 32 wires, and it is preferable to draw a single wire that denotes 32 bits.

Here is an example in Digital. First, we create an input component and set it to 2-bit.

<p align="center">
  <img src="https://i.imgur.com/F2iHpQ4.png">
</p>

Then we use the splitter/merger component (Components > Wires > Splitter/Merger). For example,

<p align="center">
  <img src="https://i.imgur.com/twDwoIP.png">
</p>

While simulating, we set the input's value to `0b10`. The wire from the input component contains both bits. This wire is connected to the splitter/merger's input dot, and the 2-bit wire is split into two wires that each contain 1 bit. Note that bit<sub>1</sub> is on and bit<sub>0</sub> is off, as expected.

In general, the splitter/merger component can split a multi-bit value into smaller parts or merge multiple values into a single value. To be concise, we'll use the term "splitter" from now on, but you should remember that it can both split and merge.

Here's another example, in which we split a 32-bit input into four separate bytes.

<p align="center">
  <img src="https://i.imgur.com/YObxjeP.png">
</p>

The splitter is configured as follows:

<p align="center">
  <img src="https://i.imgur.com/QvnfEZB.png">
</p>

The input is 32-bit, so we set "Input Splitting" to 32, which creates the blue input dot labeled 0-31 on the splitter. For four groups of 8 bits, we set "Output Splitting" to "8,8,8,8". This creates four red output dots labeled 24-31, 16-23, 8-15, and 0-7 on the splitter. Lastly, all outputs are 8-bit.

### Ungraded exercise

Note: This exercise is not graded and is purely for you to confirm whether or not you understand this section.

To test your understanding of this section, open [splitter.dig](splitter.dig). This file contains a 10-bit input displayed in binary format and a 1-bit output. Do not change the bit widths of the input or output. You may change the number format, though this is unnecessary.

In this file, create a circuit that outputs 1 if the 10-bit input is negative and odd when interpreted as a 2's complement number. Otherwise, the output should be 0.

#### Testing

See the [Lab 0 instructions](https://github.com/COMP311/lab-0?tab=readme-ov-file#testing) for testing a circuit in Digital.
