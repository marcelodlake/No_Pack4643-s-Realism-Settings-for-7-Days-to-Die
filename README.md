Config.zip contains all XML files to be put into game root > Data > Config. Make a backup of your XMLs before doing so.

The settings XML (No_Pack6463's_Realism_Settings.XML) can be placed into your C:\Users\username\AppData\Roaming\7DaystoDie\Presets folder.

As requested by some of you, I made my 7 Days to Die realism settings public.

Here's a summary.

First off, Brightness is toned down below 30%. You can go as down as you want, the game does a pretty good job at adapting the light amount when you change ambients. If you want real frightening nights, I suggest you grab the Horror Nights mod.
Major SANDBOX settings (that differ from default):

[PLAYER] Ranged damage 200%, Melee damage 250%;

[ENTITIES] Enemy density: LOW. Max enemy tier: FERAL (I avoid magical/supernatural enemies - the rancher and some simple mutated zombies are enough for me. But feel free to add all crazy mobs if you want);

[WORLD] Biome progression: NO. Biome game stage: Very low. Max Tech Type: 2. Temp survival: YES. Blood moon frequency: 5 Days, +- 3 Days (Blood moon can't be predicted). BM Warning: Evening. Heatmap sensitivity: HIGH. Storm warning: NO.

[RESOURCES] Biome loot stage: Low. Global loot stage: Low. Drink abundance: 150%. Medical abundance: 150%. Melee abundance: 200%. Currency abundance: None. Treasure map chance: None. Crafting progression: NO. Magazine progress: 7. Crafting timer: 300%. Item degradation: Low. Repair degradation: 20%. 

[TRADERS]: All turned off.

[TASKS] All turned off.

[MISC] Vehicle fuel usage: 50%. This is so the game doesn't force you to become both an Oil Shale miner and a chemist to be able to ride a vehicle. You can sustain your gas by looting exclusively.

Airdrops can be turned off if you want to play safe around immersion.

Those are the main settings, but the important tweaks com from the XMLs, like the ones I provided in this repository inside a ZIP file.
They should go insode the Game root folder > Data > Config. They can be altered as you want. You can right click them and edit them with notepad. Be very careful as syntax is delicate. If you don't know what you're doing ask ChatGPT LOL.

• [Zombie block damage tuned down]: Open items.xml and locate all "DamageBlock" properties coming from "meleeHandZombie" classes,  and change them as you like.
Example: <item name="meleeHandZombie01">
look at the value expressed right below it, like <property name="DamageBlock" value="8"/> and change it to 1. This means they have to hit a wooden door 1000 times to actually destroy them, if they're alone. Do this to all "melee hand zombies" including feral variants, charged attacks, and in less than 5 minutes you're done. I don't like the idea of vultures, dogs or other small animals dealing block damage, so I set those to zero. Their damage is psychological though. Boars do 1 damage, bears do 2 damage, and really 

• [Gun damage]: Open items.xml and overhaul the damage dealt by all ammo types, as you like. For instance, "ammo44MagnumBulletBall" means the .44 revolver shots, normal variant. Find "<passive_effect name="EntityDamage" where it reads operation="base_set" value="65" and change it to something like 150. I like it even higher, but I make this ammo the rarest (see more ahead). With this config you can one shot or drop to their knees, most zombies with the revolver, considering a centermass. 
Find the other ammo kinds (Shotgun Shells, Arrows, Bolts) and types (HP, AP) and change them. I like the shotgun to deal at least double the damage. I don't change the 9mm, but increase rifle damage 150%. Only really monstrous zombies should be able to survive a shotgun shell or a magnum shot to the chest.

• [Traps last longer]: Open blocks.xml and locate all "MaxDamage" properties from traps like Wood Spikes, Metal Spikes, Barbed Wire, and change them as you want. Zombies will get grinded and the traps will survive another day in this version (note they can still make it beyond the barricades!).

• [Make ammo rare if you're not crafting it]: Inside loot.xml there are the loot groups (ignore all Quest ammo loots for those will be disabled): 
For instance: <lootgroup name="group44MagnumSmall"> this is the loot group for a small amount of .44 bullets. Right below it you'll see their count: count="20,30". I don't recall the vanilla amount, but I tweaked it down to "2,3". Yeah, scavenging for an entire day to find two or three bullets. But those bullets are lethal so... It makes up.
For the other size groups for all loot I had it around a fraction of the original values. I was proportional to the damage overhaul I just did above. The more lethal the gun, the rarer its ammunition should be. Remember there are special ammo types like HP and AP. Slugs for shotguns etc.

• [Realistic hunger]: Not super necessary but I think the player eats too much. Water is ok, but food gauge should degrade in half the original speed. So I included entityclasses.xml and located <entity_class name="playerMale">, and changed <passive_effect name="FoodChangeOT" operation="base_subtract" value=".00400"/>. The default was 0.00800 so I halved it. I still eat food when I'm full, or to celebrate a big battle.
