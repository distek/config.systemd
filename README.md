Edit tty1's getty service

`systemctl edit getty@tty1.service`:
```
[Service]
ExecStart=
ExecStart=-/sbin/agetty --skip-login --noclear --noissue --login-options "-f distek" %I 38400 $TERM
Restart=on-failure
```

Enable all services and targets in the user directory:
```
cd user/
systemctl --user enable *
```

Set new default target:
```
systemctl --user set-default sway-session.target
```

Reboot.
