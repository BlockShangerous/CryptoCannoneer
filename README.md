# CryptoCannoneer
Node Red Flows that control the turret

https://www.youtube.com/watch?v=Ww46XBP3j0Y

https://blockshangerous.com/cryptocannoneer/

This is a turret controlled via Telegram that runs on a raspi and is programmed with nodered.

There is also a Stellar Lumens (XLM) integration that awards players with TRRT Token whenever they successfully fire the turret.
TRRT Token can then be sent back to the issuer and literally burned via a flamethrower!

![Cannoneer Flow](https://user-images.githubusercontent.com/79179630/115274504-990b0500-a0f5-11eb-9e1f-23bb06f0cf15.PNG)

Features Overview:

Telegram Integration allows for group control via chat commands

/fire triggers the solenoid holding back the compressed air

/up and /down move the tilt actuator for .5s

/left and /right default to 2s but also have a parser and can accept any amount of time. examples: /left .5 or /right 17

/help will bring up a keyboard to make controls easier


the turret automatically disarms after firing, /arm will rearm it after a 3s delay

There is an admin safety that can disable firing

After someone successfully uses /fire the award function is triggered
This checks the database to see if that telegram user has an associated Stellar account, if not, it creates one, uses friendbot to fund it (testnet), and creates a trustline to TRRT
It then awards 1 TRRT token to that Stellar account

If the user has started a DM with the bot it can privately message the Stellar keys to them if they use /account


## BURNINATOR

The world's first cryptocurrency controlled flamethrower!

Literally burn your token!

So my background is actually in stage lighting for concerts so I grabbed a couple of DMX controlled pyro stage fire projectors off ebay.
These are connected to wifi enabled outlets that get turned on and off via the nodered flow.

The burninator flow monitors the issuing account on Stellar for receipt of TRRT token then triggers the wifi outlet for .1s/TRRT burned
On Stellar, when custom tokens are returned to the issuer they are removed from the network and effectively "burned."

The /burn command will send 1 TRRT from your Stellar account to the issuer. This command also has a parser if you would like to fire off multiple fire blasts!

The admin disable for the flamethrowers is checked before the /burn command sends any token to ensure people don't waste their TRRT if the flamethrowers are not armed

Ironically, the flamethrowers run off automotive starting fluid and so they literally burn ETHER (this really cracks me up)
![IMG_7147](https://user-images.githubusercontent.com/79179630/115277046-a37ace00-a0f8-11eb-8c06-ab66c9ddfc26.jpg)


If you want to support this project please consider donating and/or buying some NFTs (coming soon!). This has been a ton of fun but also expensive and time consuming. I really would love to see this become profitable so I can expand and create a shooting gallery where people can fire golf balls at bottles and other breakables! If I can start making a profit on this I would also like to get a more suitable location and create an automatic reloader so this could theoretically run 24/7. (Obviously the flamethrowers won't be on unsupervised, but people could still play and earn while I sleep)
