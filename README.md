# Unraid SuperMicro IPMI Auto Fan Control

A pair of dirty little bash scripts to automate control of the fan speeds for a SuperMicro board using ipmitool. 

This pair of scripts is specifically designed for Unraid's "User Scripts" plugin, though I'm sure it can be adapted to other linux systems with a bit of knowhow. You'd most likely just need to detemrine the best way to retrieve the CPU/HDD temps for your linux flavor of choice, but the ipmitool portions should carry over

It started out as me having trouble getting tools designed to do this to work right and just being very tired of loud fans (especially since my server is in my home office). I still wanted the fans to crank up some when heavy processing was being done. I fleshed it out a bit and added in-line comment instructions on how to modify it to suit your own needs.

Very basic rundown:
- Gather all of the CPU temps, determine max
- Gather all of the HDD temps, determine max*
- Set speeds of the fan zones based configurable temperature thresholds (5 speed settings per fan zone)
- Use cron to run the script every few minutes

Full disclosure: I very rarely write bash scripts, but this gets the job done. Feel free to modify it to suit your needs though!

I'm currently using these on 6.10.0-rc2, I remember there being a minor (but breaking) change to the awk syntax when I upgraded from 6.9.2 and I can probably help revert it if needed.
