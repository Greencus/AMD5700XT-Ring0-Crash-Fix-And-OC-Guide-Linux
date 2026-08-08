# Resources:

-[This arch forum post](https://bbs.archlinux.org/viewtopic.php?pid=2144012#p2144012) clued me into a more stable voltage that handles very gpu heavy games that were causing crashes on the settings from the original repo.

-[This Reddit comment](https://www.reddit.com/r/Amd/comments/l4b7b1/comment/gko0m8b/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button), which for sake of preservation,  I will include here.
```
The conservative OC w/ 40% fan speed: 2000MHz @ 1050mv, +10% power limit.
Bad silicon w/ 70%+ fan speed (loud): 2060MHz @ 1200mv, with +50% power limit
Average silicon w/ 50% fan speed: 2060-2090MHz @ 1150mv, with +50% power limit
Good silicon with 50% fan speed: 2100MHz @ 1100mv, with +50% power limit
Excellent silicon with 70% fan speed: 2150MHz @ 1180mv, with +50% power limit

Softmods required. Cooling upgrades probably required:
Good silicon on water (what I run): 2160MHz @ 1223mv, with +70% power limit.
Godlike silicon on water: 2200-2240MHz @ 1250-1270mv, +90% power limit.

For Samsung GDDR6:
Poor IMC: 1800-1812MHz
Good IMC: 1820-1840MHz
Great IMC: 1840MHz (There's nearly always a frequency hole w/ Samsung from 1840-2010Mhz. It sucks.)
Godlike IMC and modules (Unicorns, only a few confirmed can run above 2000MHz where the timing strap changes, unknown if stable): 2010MHz

For Micron GDDR6
Poor IMC: 1800-1820MHz
Good IMC: 1870-1900MHz
Godlike IMC and modules: 1950MHz (Haven't seen a 2000MHz+ Micron card yet. 1950Mhz is highest I've seen, maybe just extremely rare too.)
```
By this comment's information my card appears to have quite bad silicon despite being a supposedly overclock focused card. If you have this card maybe you're in the same position? 
I got my clocks by using a stable voltage and clock speed of 1100 and 1905, then dividing 1905 by 1100 to get 1.73181818182, I then set my clock speed and divided it by 1.73181818182 and the voltages I've gotten have been stable. I cannot get a stable memory overclock.

## **Original author used these guides, that have since been taken down:**

[This Reddit thread](https://www.reddit.com/r/linuxquestions/comments/1lbbiwm/amd_radeon_rx_5700_xt_irregular_crashes_only/).

[This undervolting guide](https://www.reddit.com/r/overclocking/comments/16gmhhk/undervolting_rx_5700_xt_a_deep_dive_into/).
