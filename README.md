# Minecraft 1.21 Components

Components were added in 1.20.5 and reworked the item nbt system. Note that the entity `nbt` is the same so dont worry :D.
Use [MCSTACKER](https://Mcstacker.net) to generate these commands because it is much faster.

## Attribute Modifiers

Attribute Modifier is a component that allows you to change an entity's attributes such as `scale`, or `interaction range`.
This component has a few key terms: `id`, `type`, `amount`, `operation`, and `slot.`
`Operation` has a few different types: `add_value`, `add_multiplied_base`, and `add_multiplied_total`.

`add_value` is the simplest of all of them and just adds a number onto another number.

`add_multiplied_base` increments the base value by a number `amount.`

From what it looks like, `add_multiplied_total` does the exact same thing as `add_multiplied_base.`

If we want to add 15 to the scale value of our player while in the offhand, (1 is default) the command would look like this:

`attribute_modifiers=[{id:"scale",type:"generic.scale",amount:15,operation:"add_value",slot:"offhand"}]`

An important note is that there are two types of attributes: `generic, zombie, and player.`
Player attributes include `sneaking speed, block interaction range, and mining efficiency.`
Generic attribues are for all entities such as `scale, movement speed, luck, and knockback resistance.`
Zombie only has one attribute and it regards the spawn reinforcements on villages.

The full command to give ourselves an item that can add these attributes looks like this:

`/give @p heart_of_the_sea[attribute_modifiers=[{id:"scale",type:"generic.scale",amount:15,operation:"add_value",slot:"offhand"}]]`

Certain attributes only work on certain entities, such as `generic.jump_strength`, this one only works on horses.

## Banner Patterns

The banner pattern component allows you to not use a loom to create custom designs, and give you a finished banner directly.

There are two important components inside this component: `pattern`, and `color.`

Pattern(s) are the designs on banners. They can be a banner pattern item such as `Thing`, or `Creeper`, or a loom design like `gradient_ip`
Color is just the dye color of the design.

An example of this would be:

`banner_patterns=[{pattern:"minecraft:mojang",color:white}]`

A full command would look like this:

`/give @p red_banner[banner_patterns=[{pattern:"minecraft:mojang",color:white},{pattern:"gradient_up",color:black}]]`

## Block Entity Data

Block entity data works on a few blocks such as beehives, or mob spawners. It only works on blocks that spawn mobs.

## Block State

The block state component is very important because it allows you to give yourself a block such as a chain, but when you place it down, it will be waterlogged or facing a different direction than normal.

An example for the chain would be:

`block_state={waterlogged:"true",axis:"x"}`

And a full command would look like this:

`/give @p chain[block_state={waterlogged:"true",axis:"x"}]`

## Bucket Entity Data

Bucket entity data is a simple component that allows you to change the properties of a mob spawned from a bucket such as an axolotl or a salmon.

An example of this is:

`bucket_entity_data={NoGravity:1b,Silent:1b,Invulnerable:1b,Glowing:1b,NoAI:1b,Health:50f}`

A full command would look like this:

`/give @p cod_bucket[bucket_entity_data={NoGravity:1b,Silent:1b,Invulnerable:1b,Glowing:1b,NoAI:1b,Health:50f}]`

## Can Place On / Can break

These components allow for more customization in adventure gamemode maps.

For example:

can_break={predicates:[{blocks:"ender_chest"}],show_in_tooltip:true}

`show_in_tooltip` tells whether the "can break" tag will show in the item description.

A full command would look like this:

`/give @p diamond_block[can_place_on={predicates:[{blocks:"ender_chest"}],show_in_tooltip:true}]`
