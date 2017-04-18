# Block sites via `etc/hosts`

Need a quick productivity hack that'll help you focus more by prohibiting you from surfing time consuming sites you habitually visit?

Sure there are lots of fancy and nice tools out there e.g. [StayFocusd](https://chrome.google.com/webstore/detail/stayfocusd/laankejkbhbdhmipfmgcngdelahlfoji?hl=en) , [BlockSite](https://addons.mozilla.org/en-US/firefox/addon/blocksite/), router/proxy-server based programs that'll definitely get the job done.

But, did you know Linux has it's own easy way to do the same task out of the box?

TL;DR, to block a site, simply open for editing your `etc/hosts` file and add:
```sh
# blocks www.example.com when you try to visit it on any browser
# alternatively you can use 127.0.0.1

0.0.0.0 www.example.com
```
