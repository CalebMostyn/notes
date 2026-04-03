Fancy and new terminal emulator. Has very vast configuration options and transparent background support.

Had issue with prompt not being colored with default Ubuntu .bashrc ([fix](https://github.com/ghostty-org/ghostty/discussions/3537)).

Added password feedback by editing sudoers file (`visudo`):
```
Defaults env_reset,pwfeedback
```

## Terminal Shortcuts
- Ctrl+u : delete from cursor to beginning of line
- Ctrl+k : delete from cursor to end of line
- Ctrl+w : delete previous word
