\# 2-bit Asynchronous Up-Counter (Discrete Flip-Flops)



\*\*IC used:\*\* SN74HC74N (dual D flip-flop)

\*\*Trainer:\*\* MCP M21-7000



\## Concept

Built a ripple counter from raw flip-flops instead of using a 

counter IC. Each flip-flop's inverted output (Q-bar) feeds back 

into its own D input, causing it to toggle every clock edge. 

Q-bar of stage 1 then drives the clock of stage 2, making stage 2 

toggle at half the frequency.



\## Key rule learned

Q-bar -> next stage clock = up-counter

Q -> next stage clock = down-counter

(This is because Q-bar's rising edge aligns with the "carry" moment 

when the previous bit rolls from 1 back to 0.)



\## Verification

Hand-built a truth table predicting Q0/Q1 over 8 clock pulses before 

powering the circuit, then confirmed the physical LED sequence matched: 

00 -> 01 -> 10 -> 11 -> 00 (clean binary up-count).



\## Debugging note

Initial fast clock speed made the "11" state appear to never occur 

(both LEDs never seemed lit). Slowing the clock frequency revealed 

this was a perception/timing issue, not a logic error -- a real 

example of ripple-counter propagation delay between stages.

