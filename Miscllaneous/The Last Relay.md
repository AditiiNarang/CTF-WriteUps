# The Last Relay (100 Points)

**Category:** OSINT / Social / Network (IRC-based)  
**Points:** 100  
**Solves:** 21  
**Connection:** https://void-ctf-the-last-relay.chals.io/  
**Flag format:** `VOID{...}` (per challenge description)

## Challenge Description
The Relay is dying. An anonymous emergency IRC network is still online,
but its automated operators disagree about what happened during the
final evacuation. The archive says one thing. The live relay says
another. The diagnostic client says a third. Reconstruct the evacuation
and recover the final payload before the Relay wipes itself.

Connect to the room, inspect the public services, compare what the bots
tell you, and decide which evidence can be trusted. The relay is
anonymous — you may need to discuss observations with other
participants in the public room. Messages and artifacts can be
misleading; corroborate them before trusting them.

Objective: complete the five authoritative investigation modules,
collect the shared evidence needed by the verifier, and submit the
generated session flag to CTFd.

Note: players may bluff, which reduces points — so information from
other participants needs its own verification.

## Step 1: Connecting to the relay
TODO: how the IRC room/service was reached (client used, channel name).

## Step 2: Identifying the bots
TODO: which automated operators were present (archive bot, live relay
bot, diagnostic client) and what each one reported.

## Step 3: Comparing the three accounts
TODO: the specific contradictions between the archive, the live relay,
and the diagnostic client, and which details lined up versus which
didn't.

## Step 4: Working through the five investigation modules
TODO: what each of the five modules asked for, and the evidence
gathered from each.

## Step 5: Corroborating evidence
TODO: how conflicting or possibly-bluffed information from other
players/bots was verified before being trusted.

## Step 6: Generating and submitting the session flag
TODO: how the verifier combined the collected evidence into the final
session flag.

## Flag
```
CTF{relay_84054d8d9304fc831799ca9823ada6a6}
```

Note: this flag's format (`CTF{...}`) doesn't match the challenge's
stated format (`VOID{...}`) — double-check this is the flag for this
specific challenge/instance before relying on this write-up.

## Key Takeaways
- Multiple "authoritative" sources can disagree on purpose — corroborate
  before trusting any single one.
- In social/live challenges, other participants can bluff; verify
  claims independently rather than taking them at face value.
- Session-based flags (generated per-instance) mean this exact flag
  value won't be reusable for other players or future instances.