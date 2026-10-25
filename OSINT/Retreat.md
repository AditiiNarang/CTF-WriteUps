# Retreat (250 Points)

**Category:** OSINT / Geolocation  
**Points:** 250  
**Tagline:** Trace Away  
**Files:** chall.zip (9 images + `flagformat`)  
**Flag format:** `VOID{InitialNumber_FinalNumber}`, e.g. `VOID{100_23}`

## Challenge Overview
The challenge ships nine photographs and a `flagformat` file. The title
"Retreat" and the tagline "Trace Away" suggest following a route, and the
flag format asks for an initial number and a final number.

## Step 1: Inspect the files
The zip contained `1.jpg` to `9.jpeg` and `flagformat`. I checked the image
metadata for GPS coordinates or comments and found nothing useful, so the
photos themselves are the clues.

## Step 2: Identify the theme
Viewed together, the photos appear to show places along one route:

| # | What the photo shows | Likely place |
|---|----------------------|--------------|
| 1 | School entrance, red sign reading "1938-2023", Chinese text | Yudu, Jiangxi (the starting point) |
| 2 | Large arch bridge over a wide river | Xiang River, Hunan |
| 3 | Timber village reflected in water | Dong village, Hunan/Guizhou border |
| 4 | Winding mountain road through forest | Guizhou highlands |
| 5 | Sunset on a river with small boats | Chishui River |
| 6 | Huge river bend between mountains | Jinsha River bend |
| 7 | Suspension bridge over a fast river, small town | Luding Bridge, Dadu River |
| 8 | Distant snowy mountains | Snowy mountain pass |
| 9 | Grassland, sheep, a rider on horseback | Grasslands (Sichuan) |

These locations match the route of the Red Army's **Long March
(1934-1936)**, which also fits the title "Retreat".

Note: these identifications are my visual reading of the photos, not
confirmed by metadata or reverse image search.

## Step 3: Trace the route
Put the photos in route order, from the departure point at Yudu to the
grasslands, to confirm they all belong to the same journey.

## Step 4: Get the two numbers
The flag format asks for the initial and the final number, which I read as
the number of troops at the start of the march and at the end.

TODO: cite the source for 69,000 and 7,000. Wikipedia's Long March page
gives more than 86,000 troops at the breakout and about 8,000 arriving at
Yan'an, so the figures differ by source.

## Flag
```
VOID{69000_7000}
```

## Key Takeaways
- Look at all the images together: a shared theme (here, a historical route)
  often points to the answer.
- Read the flag format file; it tells you what kind of answer is expected.
- Historical figures vary between sources, so note which source you used.