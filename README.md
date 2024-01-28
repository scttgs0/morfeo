# MORFE/O - Meyer's Own Re-combinable FrankenEmulator / Odin version

A new emulator m68k-based of [Foenix machines](https://c256foenix.com/).
Currently only a kind of ``a2560x`` platform is supported, but morfeo
is modular and extensible...

**Warning:** current status should be considered as /pre-alpha/. Currently
only smal subset of platform is supported and debug features, like in morfe
are not implemented yet.

**Warning:** both screens are set to hi-res and GUI is fixed to x2 scale,
because of limitation of my eyes. Scaling and DIP-switches should be 
implemented in near future, I hope - but in-code resolution change works
well.

# Some screenshots

![splash screen](doc/morfeo-1.png)
![running system](doc/morfeo-2.png)

# Building

At this moment emulator was built and tested only on Ubuntu 22.04 LTS.

1. You need a working copy of [Odin](https://odin-lang.org/docs/install/)
   language - follow link and install Odin in preffered way.

2. A sdl2 development files: ``apt install libsdl2-dev``

3. Clone repo and run binary:

```shell
git clone https://github.com/aniou/morfeo
cd morfeo
make
```

4. Type ``make help`` for further options.

# Running

At this moment only two keys are supported. See for standard output logs
for unsupported functions and not-implemented-yet memory regions!

|Key     |Effect
---------|---------------------------
F8       |Change active head in multi-head setups
F12      |Exit emulator

# FQA

### Why not morfe (an Go-based)?

Because interfacing C-libraries from Go is cumbersome and excellent m68k
core (Musashi) is written in C.

### But why Odin?!

Because I need some fun too.

### Why MCP banner show "C256 Foenix"?

Because a proper ID bits in GABE emulation part are not implemented yet.

### In which areas morfeo is better than morfe?

* clean architecture
* faster
* irq support
* timer support
* current memory map of a2560x platform

### In which areas morfeo is worse than morfe?

* lack of debugging tools for code
* lack of 65c816 support
* Golang is more portable 
* more memory leaks

### What about feature XXX

In future. I have limited resources and morfe/morfeo were created as
development platform for system software, thus lack of support in 
graphics and sound

# Included software

That project include:

* [getargs](https://github.com/jasonKercher/getargs) module
* [Musashi](https://github.com/kstenerud/Musashi) core
* a ``hex.odin`` file imported (and tweaked) from Odin core library 
