---
title: iOS and Wifi setup
---

Whenever I arrive at a new location, I need to setup wifi access for my iPhone, my Mac, iPad (and eventually camera).

So instead of entering foreach device the password, I'll enter it first on my Macbook on Notes and let it sync via Bluetooth (can also work if 3G available) so I can directly copy/paste it on my iPhone and iPad.

I am amazed that Apple did not come up with a better solution, I know that Android supports QRCode that contains the SSID and password of the Wifi access point.

Here's the content of the Code, for example, a WIFI with SSID: `MYSSID` and password: `PASSWORD`, and ecnryption `WPA`:

```
WIFI:S:MYSSID;T:WPA;P:PASSWORD;;
```

You can use [websites](https://www.google.es/?q=qr+code+wifi+password) to generate it for you.

Would be great to have that supported: Just scan with your phone's camera and done! Maybe that will show up in iOS 10, we'll see that soon.
