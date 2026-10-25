# Hangman (93 Points)

**Category:** Pwn / Binary Exploitation  
**Points:** 93  
**Connection:** `nc 0.cloud.chals.io 30804`  
**Tagline:** don't let him hang  
**Flag format:** `VOID{...}`

## Challenge Overview
The challenge exposes a service over `nc`. The flag text —
"don't hang, just rop, bro" — strongly suggests this is a classic
**stack-based buffer overflow solved with a ROP (Return-Oriented
Programming) chain**, rather than an actual hangman word-guessing game.
The name "Hangman" is likely a red herring / pun on "hanging" the
stack/return address.

## Step 1: Recon
Connected to the service and inspected its behavior.

```bash
nc 0.cloud.chals.io 30804
```

TODO: what the service printed (menu, prompt, any hangman-style game text).

## Step 2: Get the binary
TODO: how the binary was obtained (provided in a zip, or pulled via the
service itself), and basic checks:

```bash
file ./hangman
checksec ./hangman
```

TODO: results — architecture, PIE/NX/canary/RELRO status.

## Step 3: Find the vulnerability
TODO: where the overflow is (which input, which buffer, how many bytes
overflow the return address). This is usually found with a tool like
Ghidra/IDA or by fuzzing input lengths.

## Step 4: Build the ROP chain
Since NX likely prevents shellcode execution on the stack, the exploit
chains existing instructions/gadgets (`ret2libc` / `ret2win` style) to
reach the goal (spawn a shell or call a win function).

```python
# TODO: actual exploit script, e.g. using pwntools
from pwn import *

io = remote("0.cloud.chals.io", 30804)
offset = 0  # TODO
rop_chain = b""  # TODO: gadgets / libc addresses

io.sendline(b"A" * offset + rop_chain)
io.interactive()
```

## Step 5: Capture the flag
TODO: what the shell/output showed once the chain executed successfully.

## Flag
```
VOID{d0nt_h4ng_just_r0p_br0}
```

## Key Takeaways
- A playful title can be a pun on the actual vulnerability class — here,
  "Hangman" hints at ROP/stack hijacking, not a word game.
- Check binary protections (`checksec`) before deciding on an exploit
  strategy — NX usually rules out plain shellcode.
- Build and test ROP chains locally against the binary before firing at
  the remote service.