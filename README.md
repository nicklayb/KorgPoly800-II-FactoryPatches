# Poly800-II Factory patches

This repo contains everything that one needs to reset a KORG Poly800-II to factory. 

I can't tell exactly what happened, but I somehow cleared my Poly800-II with MIDI flooding (I'm suspecting). The unit was kinda reset and I had no patches at all. Even thought it forced me to get creative and create new patches, I really wanted to get them back. After some back and forth in the [User manual](https://www.korg.com/us/support/download/manual/1/387/4003/) and some internet research, I've been able to reset it back to its old glory.

## Requirements

- You'll need a MIDI SyxEx player, since I did it on a Mac, I used [SysEx Librarian](https://www.snoize.com/sysexlibrarian/) with [MIDI Monitor](https://www.snoize.com/midimonitor/) as a combo. I haven't been able to Play file with SysEx then immediately record messages so the Monitor was useful to catch it back.
- A MIDI to USB adapter. If you have a MIDI controller that has both In and an Out it probably can be used, though I'm not sure if the SysEx can break the controller. I recommend a simple dongle like the Roland UM-ONE, which is the one I used.

## Instructions

1. Connect the Poly800-II to both MIDI In and MIDI Out of the dongle.
2. Power the Poly800-II.
3. Open both SysEx Librarina and MIDI Monitor.

### (Optional) Dump the Poly's data to a syx file.

In order to make sure I don't fill it with something else, and since I had built some patches already, I wanted to back it up, just in case.

The devices has no way to dump the data by itself, it requires a SysEx message called "Data Dump Request" (See DataDumpRequest.syx) to be sent.

1. Open `DataDumpRequest.syx` on SysEx Librarian
2. Hit Play on the request file
3. Watch the MIDI Monitor, it should receive a SysEx package (The user manual talks about a wait time of 300ms before sending)
4. Take the SysEx message and save to a `.syx` file.

Again, this might not be necessary if your Poly800-II has nothing at all in it.

### Dump the factory patches in the Poly

1. Open `Poly-800II factory patches.syx` in SysEx Librarian
2. Hit Play on the patches file.
3. The Poly should blink once and all should be back in there.

### Resources

- [This post](http://www.synthzone.com/forum/ubbthreads.php/topics/16668/Re:_Poly-800_II_dump_request_U) for simplify the HEX necessary for the DataDumpRequest.
- [This website](http://sunshine-jones.com/korg-factory-patch-cassettes/) for providing factory patches sysex file.
