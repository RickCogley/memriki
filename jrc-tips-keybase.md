# Keybase Tips

[Keybase](https://keybase.io/) is a free, open source service with the tagline:

> Crypto for everyone, not just programmers!

Keybase has built-in encrypted chat for teams and individuals, encrypted file sharing, encrypted git, and lets you publish a profile page [like this](https://rickcogley.keybase.pub/). Perhaps even more importantly, it is about identity. You are the sum of your various social profiles across the web, and keybase helps you prove it. 

This page is a simple tip list for keybase.

## Devices

When you register your devices with keybase, so that you can decrypt messages on them, be sure to make one or more "paper keys", and store them in a physically safe vault or other facility. That way, even if you lose all your devices, you still have a way into your account. 

If you do lose a device, be sure to *revoke* it, so that it is clear that you no longer have it. You can always add it again if you are able to get it back. 

You and anyone else can monitor those adds and revocations by viewing the "sigchain". Here is [my sigchain](https://keybase.io/rickcogley/sigchain). 

## Sending Logs

If you have a problem, sometimes you are asked by the keybase team to send them. On the command line, just do:

```
keybase log send
```

... and follow the prompts. 

## KBFS and Sharing

Keybase file system or `kbfs` gets mounted in your system so that it is well integrated with, for example, Mac Finder or Windows Explorer. You can share files publicly or privately. It is dynamic, space-based cache, which will sync with your hard drive as needed. If you are in a folder using it, those files will be copied to your local hard drive, but kbfs is smart enough to not fill up your hard drive. In this sense, it is something like Google's File Stream service that syncs Drive. 

Certain folders already exist for users, and are just available. So you don't need to do a `mkdir` and create them, rather just `cd` to them, and the system will magically do the rest. To see my public folder for instance:

```
cd /keybase/public/rickcogley
```

You can share files privately as well. To open a private folder between you and say, user `alice`, just access `/keybase/private/myuser,alice`, then drop whatever files in there, so Alice can access them. You can open such a path directly from Finder's Go menu, on macOS. 

## Sync Specific KBFS Folders

By default `kbfs` syncs dynamically as you use it, and based on how much disk space you have available. However, you can tell it to keep a specific folder in sync. Check sync status then set a folder for sync, like this:

```
keybase fs sync show /keybase/private/mykeybaseuser/important-stuff
keybase fs sync enable /keybase/private/mykeybaseuser/important-stuff
keybase fs sync show /keybase/private/mykeybaseuser/important-stuff
```

## Finding Messages

While searching is not yet possible from within the chat UI, you can search your chats from the command line, and it even works for CJK character sets like Japanese. 

```
keybase chat search --sent-by tarotanaka 我が輩は猫である
```

## Create a Public Profile Page

Find your public folder on `kbfs`, and put an `index.html` or `index.md` into it. Mine is for example `/keybase/public/rickcogley`. An `index.html` placed there can access assets like a regular website (say, an image file in `/keybase/public/rickcogley/index_assets/`). Then access `https://yourkeybasename.keybase.pub` to see it render. 

Mine is at [https://rickcogley.keybase.pub/](https://rickcogley.keybase.pub/).