# The BGB Emulator/Debugger

The [BGB emulator](http://bgb.bircd.org/) is a Windows Gameboy emulator with
an awesome set of debugging/development tools. It runs nicely under
[Wine](https://www.winehq.org/).

BGB is very powerful but also not super well documented. Here's a rough guide to
using BGB for development and some tips/shortcuts.

## Debugger UI

![BGB Debugger interface](screenshots/bgb.debugger.png)

There are four main areas in the debugger window:

1. **The disassembly view**: The _top left_ quadrant, showing instructions/code
   and highlighting the current address/line being executed (the PC register
   value). This is the largest quadrant of the debugger screen and the one 
   you'll be using the most. In the screenshot above BGB is stopped at address
   `$5866` and the instruction `ld b,a`.
1. **The hexdump view**: The _bottom left_ quadrant, showing a region of
   memory in common hexdump format. In the screenshot above BGB is showing
   `$C050` to `$C11F`. It's hard to tell from the screenshot but the cursor has
   selected the address `$COB5` which holds the value `$0B`.
1. **The register view**: The _top right_ quadrant, showing registers and
   flags. You'll frequently be scanning this area to understand the state of
   the CPU and its register set. As a quick example, in the screenshot above
   BGB shows the `AF` register pair having value `$0A40`, and the `z` flag is
   empty. The `PC` register value is `$5866`, which matches the address
   highlighted in the top left quadrant.
1. **The stack view**: The _bottom right_ quadrant, showing the stack. In the
   screenshot above the stack window is showing `$FFFE` to `$FFC0`. The top of
   the stack at `$FFE6` (indicated by the `SP` register) is highlighted to show
   where the next `pop`/`push` will occur.

## Debugger Controls

If you have experience with existing debuggers you might find BGB's terminology
a little bit non-standard/confusing. Most of these options (and a few more) are
under the _"Run"_ menu of the debugger (_Alt+R_). Selecting them from the menu
every time you're stepping through some assembly gets old fast so here's a quick
reference table with keyboard shortcuts and some terminology mappings that might
help folks experienced with other debuggers:

| **BGB Command**  | **Keyboard Shortcut** | **Comment**                               |
|------------------|-------------------|-----------------------------------------------|
| Run              | F9                | "Continue" in some debuggers                  |
| Run no break     | Shift-F9          | Run + ignore all breakpoints                  |
| Trace            | F7                | "Step Into" in some debuggers                 |
| Run to next line | F3                | "Step" in some debuggers                      |
| Run to cursor    | F4                | Run until line selected in disassembly view   |
| Step out         | F8                | Run until return from traced procedure call   |
