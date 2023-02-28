# Python-Programs

WARNING: Work in progress! Some parts of this program are not yet working as intended and much remains to be implemented.

Beyond Bastion is a text-based game that I'm working on to sharpen my Python skills. The final product will be something like Oregon Trail with RPG elements.

It is not yet in a playable state; however, it features a party system with randomized characters, an inventory system, and an equipment system, all navigable through numbered menus with formatted text output for the player.

The inventory system operates using a list of instances of an object called an ItemStack, each of which contains a reference to an item singleton as well as values for the quantity of the item and what the ItemStack's stat modifiers are (if its item is a piece of equipment). When an ItemStack containing a piece of equipment is initialized, the ItemStack queries its held item, which returns a table of semi-random stat modifiers. The monetary value of the ItemStack (indicated in-game by "gr", short for girn - the game world's currency) is then derived from its modifiers. This way, unique but balanced loot can be dynamically generated.

Characters have six semi-randomized base stats: Strength, Intelligence, Charisma, Endurance, Vitality, and Composure. They also have two combat stats: Attack and Defense. These are derived from the character's Strength and Composure, respectively. The character's maximum Health, Energy, and Sanity values are derived from their Vitality, Endurance, and Composure, respectively. These stats being semi-randomized will allow for characters to be generated dynamically in a similar fashion to equipment. In the future, the player will encounter characters throughout the world and may then decide to add them to their party.

Currently, the game randomly generates a party of 4 characters with preset names and places one of each item currently implemented into the player's inventory. This is only for testing purposes.

KNOWN ISSUES:
- Game crashes if the player kicks all characters out of their party. A simple check will be implemented in the future to ensure the player cannot do this.
- Equipment system does not yet calculate base stat modifiers from equipment correctly. Likely due to recent changes to how modifiers are stored within an ItemStack.
