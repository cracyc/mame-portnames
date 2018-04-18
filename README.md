# mame-portnames

This project aims to provide a full set of MAME input port definition files.
These are meant to be used with the 'portname' plugin, which is included with MAME 0.196 onwards.

In order to use them, you need to enable the plugin first. Open mame.ini, make sure 'plugins' is set to 1, and 'plugin' to 'portname'. Multiple plugins can be loaded by separating them with commas (for example 'hiscore,portname,cheat')

Next you need to copy the files from this repository in /ctrlr/portname, and you're set.
  
Launch MAME, open the config menu (default TAB) > Plugin Options > Input ports > Save input names to file.
This will create a <romset>.json file (unless it already exists).
  
Next, you'll need to edit the file with a text editor, and change the generic button labels with descriptive ones. This should be straightforward.

The raw .json file contains a lot of redundant information, since it lists every single input port of that particular romset - dipswitches and so included. These are all defined in MAME itself, so it's redundant to have them here - we don't want to have the majority of data to be redundant, so they may be removed (for now). In the huge majority of cases, renaming joystick controls are also redundant. For now, ports and labels are also unordered, which won't affect the result, but it's not nice to work with.

Some obvious quality control guidelines:

- Avoid spelling errors
- Try to apply consistency in your naming. For example, in shoot 'em up games, I chose the term 'Fire' for any button that shoots. Don't have 'Shot', 'Shoot', 'Fire' mixed together.
- Try to respect the original game's labeling, if it exists. For example, in Street Fighter games, LP, MP and HP are named 'Jab Punch', 'Strong Punch' and 'Fierce Punch' respectively.
- After editing and saving the file, run the game again and check if it works correctly.

That should be it!
