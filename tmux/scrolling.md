# Scrolling

**context**: Scrolling in tmux can be a bit of a mystery especially for new users and could very well be the reason why they'll revert to their old ways... 

Let `<prefix>` be whatever your tmux control prefix is. In my case, it’s just the default, `ctrl+b`


To be able to scroll/page through the output in the active pane of your tmux session, simply do:
```
<prefix> [
```
Afterwards, you'll now be able to use the `Up Arrow`, `Down Arrow`, `PgUp` or `PgDn` keys to navigate.

To exit scroll mode, just hit `q`.