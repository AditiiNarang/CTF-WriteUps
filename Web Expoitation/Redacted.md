# Redacted — Web Exploitation (200 Points)

## Challenge Overview

- **Challenge Name:** Redacted
- **Category:** Web Exploitation
- **Points:** 200
- **Challenge URL:** https://voidweb1.pythonanywhere.com/
- **Flag:** `VOID{wh4t_y0u_s33_1s_wh4t_th3_f0nt_s4ys}`

### Description

Legal has supposedly retired the black marker. VOID's internal memos are now redacted at the typography layer, making sensitive information appear hidden while remaining present in the browser.

The challenge asks us to prove that the memo's redaction is not as secure as it appears.

## Solution

### Step 1: Open the Challenge Website

Visit the challenge URL:

https://voidweb1.pythonanywhere.com/

The page displays a classified internal memo containing apparently obfuscated information, including the sender, recipient, passphrase details, and a new access phrase.

The memo also provides an important hint:

> "Redaction is enforced at the typography layer."

This suggests that the information may not actually be removed. Instead, the website's font or text-rendering technique may be making the original content appear different from what it really is.

### Step 2: Understand the Hint

The key phrase is **"typography layer."**

Traditional redaction permanently removes or obscures sensitive information. However, if a website only changes how text is displayed, the underlying characters may still be present in the page.

This means the visible text might not tell the whole story. The browser's rendering and font-related behavior become important clues.

### Step 3: Investigate the Hidden Text

The challenge's random-looking strings and unusual text presentation suggest that the information is being concealed through a custom typography technique rather than conventional image-based redaction.

The main lesson is to distinguish between:

- **What the browser displays** — the text as it appears visually.
- **What the underlying content contains** — the actual characters or data used to render that text.

A visual appearance alone is not proof that information has been securely removed.

### Step 4: Recover the Flag

After identifying the intended typography-based trick, the challenge flag is:

`VOID{wh4t_y0u_s33_1s_wh4t_th3_f0nt_s4ys}`

## Final Flag

```text
VOID{wh4t_y0u_s33_1s_wh4t_th3_f0nt_s4ys}
```

## Key Takeaways

- Visual redaction is not the same as securely removing sensitive information.
- Custom fonts and rendering techniques can change how text appears in a browser.
- Web challenges may hide clues in the difference between displayed content and underlying data.
- Always verify what information is actually present before trusting a visual representation as secure.

## Conclusion

The **Redacted** challenge demonstrates how typography can be used to conceal information without necessarily removing it. The key was recognizing the hint about the typography layer and understanding that what we see on screen may not accurately represent the underlying content.
