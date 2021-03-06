Plug-in Presets for Notion
==========================

A plug-in preset is a folder with these items:

* A file named `Preset.xml`
* A folder named `Instruments`
* Within the Instruments folder, you can have optionally have one level of sub-folders for an instrument family (e.g. Brass / Wind / Strings)
* In the Instruments folder (or optional sub-folder), a Notion file for each instrument


Preset.xml
----------

This is a minimal definition for a presets XML file. Use your own reverse domain name to keep your preset identifier unique, but you can structure the identifier as you like. 

    <preset>
        <identifier>com.mydomain.pluginmaker.plugin.v1</identifier>
        <name>Preset Name Here</name>
    </preset>


An instruments file
-------------------

Each Notion file in the Instruments folder defines one instrument, which will then come up as an instrument in your preset.

Each file should have:

* One part with a plug-in instrument
* One rules definition in `Use Rules`

The part will be used as a template when adding this instrument to the score, so things like the staff name, clef, transposition, abbreviation, and staff type will be copied when you add this instrument into your score.

You can put music and tests of various expressions in this file. This is useful and recommended. 


Preset Expressions
------------------------

Many sound libraries have sounds that don't have a standard technique name in notation. You can have your preset access these with a preset expression, or user technique.

In the preset definition, keep the number unique. This number will be used to match an expression you've entered in the score and the rule you make for it.

    <preset>
        <identifier>com.mydomain.pluginmaker.plugin.v1</identifier>
        <name>Preset Name Here</name>
        <user-techniques>
            <technique number=1>Octaves</technique>
            <technique number=2>Rips</technique>
        </user-techniques>
    </preset>

Once you've created the expression in the XML and the corresponding rule in the Notion file, you can use it. Click the Techniques box in the Palette, then the arrow. This will show 'User' in the cursor. Place it where you wish in the score - Notion will then give you the list of expressions that you created.

Preset locations
----------------
You can save the folder in one of two possible locations (depending on how you wish to organise yourself):

On macOS, Notion will look for presets here:

* `/Users/<user>/Documents/Notion/Presets` (you will need to create this folder if it does not already exist)
* `/Library/Application Support/Notion Music/Notion 6/Presets`

On Windows, Notion looks here:

* `C:\Users\<users>\Documents\Notion\Presets`(you will need to create this folder if it does not already exist)
* `C:\Program Files\Notion 6\Presets` (or where you have installed Notion)

The location of the second of each locations above will change with the app's major version, so Notion 7 will have presets in its own folder.


Using the presets
----------------
On launching, Notion will check the two preset locations above, and add any Presets it finds to Score Setup. 
Look under VST Presets>Your Preset Name in Score Setup.

Select the instrument, and Notion will add it to the score.


