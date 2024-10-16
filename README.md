# Preamble
You **must** apply the loose fixes explained here by Adrian: https://gist.github.com/Adrianilloo/6359896e79b6b135d3c925c627c9554b#loose-fixes
This is to stop a crash from happening on server boot up. The following is the gist of it to at least get the server to boot. Again, fixes provided by Adrian.
## Fix bad pointed library errors on SRCDS startup (Linux 32/64 bit)
- Problem crashes SRCDS. Fix: Create symbolic links. From server root folder:

```
ln -s soundemittersystem_srv.so soundemittersystem.so
ln -s scenefilecache_srv.so scenefilecache.so
```

- Another problem which does not crash is SSDK2013 binaries pointing to outdated library names. Fix:
```
mv libtier0.so libtier0.so.bak
ln -s libtier0_srv.so libtier0.so
mv libvstdlib.so libvstdlib.so.bak
ln -s libvstdlib_srv.so libvstdlib.so
```

## Courtesey fixes already provided by:
**Adrian**: https://github.com/Adrianilloo/SourceSDK2013
**Hrgve**: https://github.com/hrgve/hl2dm-bugfix (forked)
**Tyabus**: https://github.com/tyabus/source-sdk-2013-multiplayer-fixes
**weaponcubemap**: https://github.com/weaponcubemap/source-sdk-2013

Additional thanks to **No Air** for providing assistance where needed.

Additional fixes were provided in complement of the above.

Not all fixes and updates are listed here, only the most important ones.

# Fixes:

- General server crash fixes.
- Grenade corner clipping fixed.
- Spectator abuse fixes.
- Impulse 51 is now behind sv_cheats.
- Sprint delay is completely removed. Sprint as soon as you let go of your duck key.
- Completely remove suit and items when going in the spectators team to fix the 1 HP visual.
- Continue sprint after detatching an object held in the physcannon.
- Headcrab canister sound precache fixed.
- Player model fix when switching teams.
- Item and weapon respawn fixes.
T- -Pose in mid air fixed.
- Multiple server crash exploits fixed.
- Spectator: Observer mode fixes.
- Timeleft command fixed to display frag limit if set.
- Fix mp_forcerespawn bypass.
- Fixed props losing collisions when switching to spec while holding an object in the physcannon.
- Fixed spawning on ladders.
- Fixed breaking ladders if disconnecting or dying on them.
- Spawn fixes.
- Barrels no longer blow up if you yoyo and put them down gently.
- Fixed some console spam.
- Fix props ownership abuses.

Weapon fixes:
- Re-add missing weapons sounds to physcannon, RPG, frag grenades and crossbow.- 
- Fix SLAM ownership
- Fix SLAM laser length
- Fix floating SLAMs
- Fix slow bolt on SLAMs.
- Fix rocket slowing down in water.
- Fix silently holding an object in the gravity gun.
- Physcannon negative Z push fix. Object properly flings in the direction the player punts those objects towards.
- Fix holt bolt launching players at really high speeds when stepping onto them.
- Fix orbs pushing you when a second player shot it.
- Fix orbs levitating in the air when a player disconnects while holding one.
- Don't let the AR2 be switched if an orb is being charged.
- Don't let the RPG be switched if a live rocket is in the air.
- Don't let the physcannon be switched if holding an object.
- Fixed annoying snap eye angles at higher pings.
  
  

# Updates:

- Default the tickrate to 100.
- Removed development only flags.
- Always recharge aux power if sv_infinite_aux_power is 1.
- Immediately spawn players when switching teams from spectators.
- Removal of MOTD on join.
- Impulse 101: Gives crossbow ammo.
- Allow movement speed to be adjusted with ConVars.
- Pre-OB movement re-instated.
- Recharge aux power if not moving while holding the sprint key.
- Restore the ability to set custom suit charger values with sk_suitcharger.
- No longer allow sprinting underwater.
- Suit drain rate is customizable with sv_sprint_drain_rate. 25 for HL2DM, 12.5 for HL2.
- Material based footstep sounds.
- No longer kill the player when switching teams (other than when switching to spectators).

The following engine messages were updated:
- Player SOME NAME has joined the game.
- Player SOME NAME has left the game.
- Player SOME NAME joined team TEAM HERE.
They now use colors to stand out better.

- Chat was also updated to support more prefixes, such as *DEAD* when the player is currently dead. Team based messages now properly show the team name rather than just (TEAM) prefix.
- Spectators team chat has been fixed in DM mode (i.e. when teamplay is off).
- Shotgun revised to have a larger cone, but increased damaged.
- Give the frag grenade its proper grenade surface sound.
- Raise max players to 32.


# Additions:

- Suit voice. Controlled by mp_suitvoice.
- Set the game description seen in the browser with sv_game_description.
- Additional outputs for item_healthcharger: OnFull, OnHalfEmpty, OnEmpty
- Chat triggers for "timeleft" and "nextmap". Chat triggers controlled with sv_chat_triggers.
- Allow for removing the tinnitus DSP effect caused explosion with mp_ear_ringing.
- Allow for starting with no weapons with mp_noweapons.
- Trigger_catapult.
- Trigger_userinput.
- Make DM/TDM mode changes instantaneous instead of relying on map restart. Use mp_allow_teamplay_changes to enable or disable, then use chat trigger "!tp", "!teamplay" or console commands "toggle_teamplay", "tp" to toggle through having teamplay on or off.
- Allow or block point_servercommand entities with sv_allow_point_servercommand. Default is disallow. Use always or disallow.
- Timeleft on the HUD. Enable/Disable with sv_timeleft_enable and customize with sv_timeleft_r, sv_timeleft_g, sv_timeleft_b, sv_timeleft_channel, sv_timeleft_x, sv_timeleft_y.
- Speed crawl.
- Add the ability not to change the map when the game is over by reaching the time limit or frag limit with mp_change_level_on_game_over.


