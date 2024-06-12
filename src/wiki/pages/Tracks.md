AquaPerms has it's own (somewhat) unique track system, although the majority of other permissions plugins also have something similar. 

Think of a Track as a "ladder" or "promotion route".

---

Note that tracks act only as a means for easy promotion and demotion of users, and **do not influence inheritance**.

---

### Example 1
I might have a track called "staff". This track would consist the groups:

**default :arrow_right: heaper :arrow_right: mod :arrow_right: admin**

I can then use this track to promote or demote users.

For example, if "Notch" was in the heaper group, and I wanted to make him mod, I would run:

`/aquaperms user Notch promote staff`

### Example 2
I might have another track for donators, consisting of:

**default :arrow_right: iron :arrow_right: gold :arrow_right: diamond**

I could then promote users along this track each time they were to purchase a "rank upgrade", or whatever.

`/aquaperms user Luck promote donator`

To promote someone backwards on a track, you just use the demote command.

## Creating a Track
Just run `/aquaperms createtrack <name>`, followed by `/aquaperms track <name> append <group>` to add each of the groups. There are other commands available to heap edit the track, which you can find on the Command Usage page.