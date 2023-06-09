# BM-Wrapped-Docs
Documentation for everything bm-wrapped, by https://discord.gg/callie

**• Snipe balancer**

When BM-Wrapped finds a snipe, it'll cycle through the list of users with functioning flipTokens and check who would want the deal. 
The user closest to the bottom of the (purchase) queue, the user with less value sniped, will get the snipe. If the snipe is successful they'll have their totalSnipeValue increased which will make them less likely to get the snipe. This distributes snipes equally between users and is why having a good config is important (you won't always get the coolest 1.3/1k snipe).

**• Tutorial**
```
Before doing anything you'll NEED a bm-wrapped whitelist from discord.gg/callie, this isn't free...
1. Do /whitelist time-left and copy the key (it'll be under the spoiler)
2. Do /attach-key (under the bm-wrapped bot) and give it the key you copied
3. Do /config base and fill in the config it gives you (THE CONFIG CHANGED THE OLD ONE WONT WORK)
4. /config edit, then drag in your config (as a file)
5. do /accounts add (if you don't know how to get a fliptoken look below)
6. /2fa add (if you don't know how to get ur 2fa token look below)
```

**• How to get a fliptoken**
```
1. Go to https://www.rbxflip.com/shop and press F12 (or right click and click inspect)
2. Click the "Application" tab: click on the two arrows pointing to the right and click Application 
3. Click LocalStorage > https://www.rbxflip.com/ > Access token
4. There will be a box with a lot of letters/numbers in it, copy all of them
```

**• How to get the 2fa token**
```
Same code you used with your authenticator app / adurite's auto2fa
1. Go to your security settings on Roblox (https://www.roblox.com/my/account#!/security)
2. Disable "Authenticator App (Very Secure)"
3. Re-enable "Authenticator App (Very Secure)" and click "Can't scan the QR code? Click here for manual entry."
4. Copy the token that appears on your screen
  4a. The bot will ask you for a 2fa code, make sure you add this code to your own 2fa app
```

# Config settings
Most of these are self explanatory but, here are some of the docs i've written for them.

If you're getting yaml errors put your config in https://jsonformatter.org/yaml-formatter

 **• customRates**

List of items/demands that have specific rates attached to them. You can set rates to demands, specific rates (as IDS),
and add conditions to these rates. If you were to do ["Normal > value", 2] all valued items with a normal demand would
be bought if sold at or below a rate of 2$/1k, rap/value conditions can be added to specific item rates if you're scared it might get devalued.
EX:
```
customRates:
    - ["itemid/demand > value/rap", 2]
    - ["Normal > value", 2]
```

**• projecteds > revaluedProjecteds**

A bool (true/false), if set to false it won't revalue projecteds with my server's value of them, opposite will happen if set to true.

**• projecteds > ignore**

A bool (true/false), if set to false it won't consider projecteds AT ALL, opposite will happen if set to false.

**• gerneralRates**

Rates for rap/value items that'll be used if there are no custom rates set for them or their demand.

**• doNotSnipe**

Items (by item IDs) or item types that the bot wont consider buying for you.

**• autoResell > autoValue**

Will get recent legitimate sales and averages them to get a resell value, will ignore if it comes out lower than the purchase rate + minimumProfit

**• autoResell > minimumProfit**

Will ignore the set manualResell rate and autovalue rate if the profit (by rate) is less than whatever you set minimumProfit to.

**• autoResell > manualValues**

Mixture of general rates and customrates (just called customResell), please look at the custom rates section when configuring customResell, rap/value settings are just the rates you'd like the bot to list rap/value items. **WARNING:** be sure to set rap/value higher than normal, it's bad to generalized items, some rap items can sell for 2.4+; you'll be able to change the listing rate through the bot embed if you don't like it!

# Commands

/help under @BM-Wrapped will give you a full list of the bot's commands and their descriptions, I won't be writing docs for each of them.

