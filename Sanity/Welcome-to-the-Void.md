# 1. Welcome to the Void (100 Points)

**Category:** Sanity / OSINT / Steganography  
**Points:** 100

## Challenge Overview

- **Title:** Welcome to the Void
- **Category:** Sanity
- **Points:** 100

### Description

Every year, the Void Society opens its doors to new members. Most see a warm welcome, a few emojis, and a thank-you note. They like it, scroll past, and move on.

But Mira, our resident paranoid developer, insisted on adding something to this year’s welcome.

> “A society of hackers shouldn’t welcome people with words alone,” she said. “Let the curious ones earn their entry.”

She left you a note:

> “Find where Void Society greets the world professionally. Our newest welcome holds more than words. Skip the first face you see, ignore the second, and the third will let you in. After all, it’s where curiosity meets cyber security.”

**Flag Format:** `flag{...}`

## Step-by-Step Solution

### Step 1: Analyzing the Clues

The challenge description contained several hints that helped identify where to look for the flag.

- **“Where Void Society greets the world professionally”** suggested LinkedIn, a professional networking platform.
- **“Where curiosity meets cyber security”** matched the tagline used in the VOID Society @ KIET LinkedIn welcome post.
- **“Skip the first face you see, ignore the second, and the third will let you in”** suggested that the required information was hidden in the third image of the post's carousel.

The LinkedIn welcome post contained five images. Following the clue led me to inspect the third slide.

### Step 2: Inspecting the Third Image

The third image showed a presenter standing beside a screen displaying a presentation titled:

**“What is CTF? / Capture The Flag”**

I carefully examined the slide, focusing on the section labeled **“3 - Capture it.”**

The flag was embedded in the presentation slide and was difficult to read clearly at the original image size. I enhanced the image to make the text more visible.

After zooming in and inspecting the relevant section, I recovered the flag.

## Flag

```text
flag{f0und_m3}
```

## Key Takeaways

- **Pay attention to contextual clues:** Challenge descriptions often hint at the exact platform or source that needs to be investigated.
- **Explore social media carefully:** Useful information can be hidden in carousel posts, presentation slides, and images rather than in the post caption.
- **Follow the sequence in the hint:** References to first, second, and third can indicate a specific image or slide.
- **Enhance images when necessary:** Zooming in or improving image clarity can reveal small text that is otherwise difficult to read.
- **Combine OSINT with visual inspection:** Finding the correct public source is only the first step; examining its contents carefully can reveal the final answer.

This challenge demonstrated how contextual clues and careful inspection of publicly available content can be combined to solve a beginner-friendly CTF challenge.

