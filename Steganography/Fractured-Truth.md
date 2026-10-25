# Fractured Truth (300 Points)

**Category:** Forensics / Misc  
**Points:** 300  
**Solves:** 76

## Challenge Overview

- **Title:** Fractured Truth
- **Category:** Forensics / Misc
- **Points:** 300

### Description

An intercepted transmission has been broken into pieces. Two signals remain, but not everything they reveal can be trusted.

Reconstruct the fragments, scan the codes, and separate the truth from the deception.

**Flag Format:** `VOID{...}`

## Step-by-Step Solution

### Step 1: Analyzing the Clues

The description contained several hints about what to do.

- **"Broken into pieces"** suggested that the files were fragments of a larger image that had to be put back together.
- **"Scan the codes"** suggested that the reconstructed image was a scannable code, such as a QR code.
- **"Two signals remain"** suggested that there were two codes to find among the fragments.
- **"Not everything they reveal can be trusted"** suggested that one of the codes was a decoy, so each result had to be checked before submitting.

### Step 2: Inspecting the Fragments

The challenge provided **12 fragments**. None of them could be scanned on its own, because each contained only part of a code.

TODO: file names and formats, and what the fragments looked like
(which parts of the code each piece held).

### Step 3: Reconstructing the Code

I arranged the 12 fragments in the correct positions and joined them into a single image. This restored the missing parts of the code, including the alignment markers a scanner needs to detect and orient it.

TODO: how the pieces were aligned (manually or with a script) and which tool was used.

### Step 4: Scanning the Reconstructed Code

I scanned the rebuilt image with a code scanner. Once the pieces were joined, it decoded successfully, which confirmed the reconstruction was correct.

TODO: the decoded text, and the scanner or tool used.

### Step 5: Separating Truth from Deception

The description warned that not everything could be trusted, so I compared what each code revealed instead of accepting the first result.

TODO: what the second code said, which one was the decoy, and what made the real one trustworthy.

The trustworthy code led to the flag.

## Flag

```text
VOID{s33_th3_wh0l3_p1ctur3}
```

The flag text ("see the whole picture") matches the solution: the answer only appeared once all the fragments were viewed together.

## Key Takeaways

- **Reassemble before analyzing:** Individual fragments may reveal nothing, but together they form a readable whole.
- **Check the structure of scannable codes:** A code needs its alignment markers and complete layout before a scanner can read it.
- **Do not trust the first result:** When a challenge warns about deception, compare every output before submitting.
- **Read the flag as a hint:** The flag text itself often confirms the intended solution.

This challenge showed how patient reconstruction and careful verification can turn scattered fragments into a reliable answer.