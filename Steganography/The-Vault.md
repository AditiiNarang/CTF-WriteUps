# The Vault (150 Points)

**Steganography**  
**150 Points**

## Challenge Overview

**Title:** The Vault  
**Category:** Steganography  
**Points:** 150

**Description:**

We were given a single image, `challenge.jpg`, with the following story:

> Our operatives intercepted a suspicious photograph from a rogue operative's terminal. Headquarters suspects there's more to this picture than meets the eye. They claim they left some sensitive files behind, but looking at the pixels alone won't save us. Can you dig beneath the surface and crack open The Vault?

**Flag Format:** `VOID{...}`

## Step-by-Step Solution

### Step 1: Checking the File and Its Metadata

The challenge provided a JPEG image named `challenge.jpg`. I started by checking its file type and metadata using the following command:

```bash
file challenge.jpg
```

The output revealed a comment field containing a Base64-encoded string:

```text
Qmkxa00zR0VoaHdjVlZ1blUyTHJjeWNMeE1QVkVnaVM3VDMyODZTQ0VCYkZoNWdkZE1LQg==
```

The clue *"looking at the pixels alone won't save us"* suggested that the solution might involve hidden data outside the visible image.

### Step 2: Decoding the Image Comment

I decoded the Base64 string using the following command:

```bash
echo "Qmkxa00zR0VoaHdjVlZ1blUyTHJjeWNMeE1QVkVnaVM3VDMyODZTQ0VCYkZoNWdkZE1LQg==" | base64 -d
```

This produced another encoded string:

```text
Bi1kM3GEhhwcVVunU2LrcycLxMPVEgiS7T3286SCEBbFh5gddMKB
```

Since the output contained characters compatible with the Base58 alphabet, I tried decoding it using Python.

```python
A = '123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz'
s = "Bi1kM3GEhhwcVVunU2LrcycLxMPVEgiS7T3286SCEBbFh5gddMKB"

n = 0
for c in s:
    n = n * 58 + A.index(c)

print(n.to_bytes((n.bit_length() + 7) // 8, 'big'))
```

The output was:

```text
b'Haha... nice try. But this is a decoy.'
```

This confirmed that the image comment was a decoy rather than the actual flag.

### Step 3: Searching for Appended Hidden Data

Since the metadata did not reveal the flag, I inspected the image file for additional embedded data.

I used the `strings` command and noticed references to three files:

```text
01_hidden.txt
02_hidden.txt
03_hidden.txt
```

This suggested that a ZIP archive might have been appended to the JPEG file.

To locate and extract the appended archive, I used Python:

```python
d = open('challenge.jpg', 'rb').read()
i = d.find(b'PK\x03\x04')

open('emb.zip', 'wb').write(d[i:])
```

The ZIP file was then extracted using:

```bash
unzip emb.zip
```

The archive contained three files that appeared to be text files based on their extensions.

### Step 4: Identifying the Hidden File Types

The file extensions did not match the actual content, so I checked the file types:

```bash
file 01_hidden.txt 02_hidden.txt 03_hidden.txt
```

The output revealed that the files were actually images:

| File | Actual Type | Content |
|---|---|---|
| `01_hidden.txt` | JPEG | Desert dunes photograph |
| `02_hidden.txt` | JPEG | Autumn waterfall photograph |
| `03_hidden.txt` | PNG | Wasteland scene featuring a power plant and a tattered flag |

This showed that the archive contained hidden images disguised as text files.

### Step 5: Finding the Flag

I renamed `03_hidden.txt` to `03.png` and opened the image.

The picture showed a wasteland scene with a power plant and a tattered flag. By inspecting the text displayed on the flag, I recovered the challenge flag.

The text wrapped across two lines on the banner, so I joined the two parts using an underscore.

## Flag

```text
VOID{the_picture_was_inside_the_picture}
```

## Key Takeaways

- **Inspect file metadata:** Image comments and other metadata fields can contain encoded clues or decoy messages.
- **Look beyond the visible image:** Hidden files can be appended to an image without changing its normal appearance.
- **Recognize file signatures:** The ZIP signature `PK\x03\x04` can help identify an archive embedded inside another file.
- **Verify file types:** File extensions can be misleading, so use tools such as `file` to identify the actual format.
- **Follow the evidence:** Encoded metadata may be a decoy. Continue investigating when the result does not match the challenge's main objective.

This challenge demonstrated how steganography can involve not only hiding information within image pixels but also concealing additional files inside an image file.
