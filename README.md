# Dyeable Armor

A Minecraft Bedrock Edition add-on that introduces a complete set of dyeable armor pieces, allowing players to customize their armor colors using dyes.

## Features

- **Complete Armor Set**: Helmet, Chestplate, Leggings, and Boots
- **Dyeable**: Use cauldrons with dyed water to change armor colors

## Installation

1. Download both the Behavior Pack (BP) and Resource Pack (RP)
2. Import both packs into Minecraft Bedrock Edition
3. Apply the Resource Pack to your world
4. Enable the Behavior Pack in your world settings
5. Start playing!

## How to Use

### Dyeing Armor
1. Fill a cauldron with water
2. Use any dye on the water-filled cauldron to color the water
3. With the armor piece in hand, interact with the dyed water cauldron
4. The armor will change color based on the dye used in the cauldron
5. Mix different dyes in the cauldron for custom colors

## Technical Details

### Behavior Pack Structure
```
BP/
├── manifest.json
└── items/
    ├── dye_helmet.json
    ├── dye_chestplate.item.json
    ├── dye_leggings.item.json
    └── dye_boots.item.json
```

### Resource Pack Structure
```
RP/
├── manifest.json
├── attachables/
│   ├── dye_helmet.attachable.json
│   ├── dye_chestplate.attachable.json
│   ├── dye_leggings.attachable.json
│   └── dye_boots.attachable.json
├── models/entity/attachable/
│   ├── dye_helmet.geo.json
│   ├── dye_chestplate.geo.json
│   ├── dye_leggings.geo.json
│   └── dye_boots.geo.json
├── textures/
│   ├── item_texture.json
│   ├── items/ (item icons)
│   └── entity/attachable/ (armor textures)
```

## Key Components

### Dyeable Component
The armor uses the `minecraft:dyeable` component with a default color:
```json
"minecraft:dyeable": {
    "default_color": "#ffffff"
}
```

### Color-Change Materials
Attachables use special materials that support color changing:
- `entity_alphatest_change_color` - Standard dyeable material
- `entity_alphatest_change_color_glint` - Enchanted dyeable material

## TGA Tutorial Reference

For a detailed tutorial on creating TGA textures for dyeable items, watch: [TGA Tutorial](https://youtu.be/MV_Pitb7G1U?si=WDj06ZER1wnYmZS-)

### TGA Texture Requirements
For proper color changing functionality:
- **Item Icons**: Use opacity value of 3 for non-color-changeable parts, 255 for dyeable parts
- **Armor Models**: Use opacity value of 1 for non-color-changeable parts, 255 for dyeable parts
- Save textures in TGA format to support alpha channel opacity

## Creating Custom Dyeable Items

***Note***: 
1.Use opacity 3 to make undyeable layer/part not transparent on item,


To create your own dyeable items:

1. **Add the dyeable component** to your item JSON:
   ```json
   "minecraft:dyeable": {
       "default_color": "#ffffff"
   }
   ```
   
2.**Use 2 textures on item**:
  ```json
	"minecraft:icon": {
		"textures": {
			"default":"dye_boots",
			"dyed":"dye_boots"
		}
	}
  ```

3. **Use color-change materials** in attachables:
   ```json
   "materials": {
       "default": "entity_alphatest_change_color",
       "enchanted": "entity_alphatest_change_color_glint"
   }
   ```
4. **Use TGA or Not**
   TGA make some layer/part dyeable and some dyeable by the opacity,
   use opacity 255 to make it dyeable
   use the opacity 3(for item icon) or 1 (for model's texture) to make it undyeable

   For a detailed tutorial on creating TGA textures for dyeable items, watch: [TGA Tutorial](https://youtu.be/MV_Pitb7G1U?si=WDj06ZER1wnYmZS-)

   but if you use png all the texture layer/part will be dyeable

   


## Requirements

- Minecraft Bedrock Edition 1.21.50 or higher

## Credits

- **Author**: Causal
- **Repository**: [GitHub - Dyeable Armor](https://github.com/causal-guide/Dyeable-Armor/)
- **Models Generated with**: Blockbench Item Wizard 1.2.1

## License

This project is available on GitHub. Please check the repository for license information.

## Support

If you encounter any issues or have questions:
1. Check the GitHub repository for updates
2. Report bugs through GitHub Issues
3. Join the community for support and discussions

---

*Happy crafting and stay colorful!* 🎨⚔️
