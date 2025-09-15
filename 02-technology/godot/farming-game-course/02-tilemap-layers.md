## Creating the Test Scene

In the root folder of the project (**res://**), create a new folder called **scenes**. Within that folder, create another folder called **test**. 

With the **test** folder selected, click on the **2D Scene** button under **Create Root Node:** within the **Scene** dock to create a new 2D scene. 

The 2D Scene will have a 2D Node (2D game object) called **Node2D** by default. Rename the Node by either Pressing `F2`, double clicking on the scene, or right clicking on it and selecting **Rename**. Change the name to **TestSceneTilemap**.

![[new-2d-scene-edit.png]]

<br>

Save the scene using Ctrl + S, or by navigating to **Scene** > **Save Scene**, and select the **test** folder we created (**res://scenes/test**). Click the **Save** button to confirm.

<br>

---

<br>

## Adding Tilemap Nodes

Right-click on the **TestSceneTilemap** Node and select **Add Child Node**. Search for and select **Node2D** to create the new node and confirm by pressing the **Create** button at the bottom.

![[create-node2d-edit.png]]

<br>

Rename **Node2D** to **GameTileMap**.

<br>

---

<br>

## Add Tilemap Layers


Right-click on the **GameTileMap** Node and select **Add Child Node...**.

Search for and select **TileMapLayer** (NOT TileMap), and then press the **Create** button at the bottom to confirm.

![[add-tilemap-layer-edit.png]]

<br>

---

<br>

## Add Tileset

In the root folder of the project, add a folder called **tilesets**.

In the **Scene** dock, make sure **TileMapLayer** is selected and within the **Inspector** dock, find the the Property that is titled **Tile Set** with a value of **\<empty\>**. 

Click on the dropdown button and select **New TileSet**. It should now switch from saying **\<empty\>** to saying **TileSet**.  Right-click on **TileSet** and select **Save As...**.

Make sure the **tilesets** folder is selected in the Path (**res://tilesets**) and save the file as **game_tile_set.tres**.

![[game-tile-set-edit.png]]

<br>

Rename the TileMapLayer from **TileMapLayer** to something that best describes the content which will be on that layer. In this case, the layer will be water, so rename the layer to **Water**.

<br>

---

<br>

## Add Assets to Tileset

In the bottom panel, there are multiple tabs to choose from such **Output**, **Debugger**, **Audio**, **Animation**, etc. 

The two tabs which are the most important right now are the **TileSet** and **TileMap** tabs.

![[bottom-panel-edit.png]]

<br>

Select the **TileSet** tab in the bottom panel and make sure the **Tile Sources** tab is active. 

Navigate the **FileSystem** dock to find the **water.png** file in the game assets (**res://assets/game/tilesets/water.png**) and drag that file into the dark area under **Tile Sources** to add it to the TileSet.

If a pop-up appears titled **Auto Create Tiles in Non-Transparent Texture Regions?** asks if you would you like to automatically create tiles in the atlas, click the **No** button.

![[add-water-tileset-edit.png]]

<br>

---

<br>

## Set Up Tile Animation

Make sure **Setup** is selected and select the first water tile to activate it in the atlas. Now click on the **Select** tab and click on the first water tile again to select it.

This will show a **Base Tile** configuration menu. Within this menu, open the **Animation** dropdown. Because this water animation has four frames (four base tiles), we will increase the **Columns** property to a value of **4**.

![[animation-columns-edit.png]]

<br>

#### Adding Each Frame

Now each frame must be manually selected. Open the **Frames** dropdown and you should see a single element with a **Duration** property set to **1.0 s** (seconds). 

Click the button that says **Add Element** to add the second frame. Repeat this step two more times until all four tiles are visibly selected and then change the **Duration** property for each frame from **1.0** to **0.2** seconds. 

![[water-frames-setup-edit.png]]

<br>

---

<br> 

## Add Water Tiles to Scene

Now it's time to paint the animated water tiles in the game scene. Click on the **TileMap** tab in the bottom panel and select the first tile of four water tiles.

Select the **Rect Tool** in the toolbar and paint the water in the scene by clicking and dragging a box to fill within the window outline.

![[paint-water-tiles-edit.png]]

<br>

---

<br> 

## Configure Project Settings

Before running the scene to see what the game looks like so far, some project settings need to be configure so the pixels appear correctly and everything is sized as expected.

Navigate to **Project** > **Project Settings...** in the top left of Godot and make sure the **General** tab is active.

Under **Display**, select **Window** and change the following values:

- **Size**: 
	- **Viewport Width**:  640
	- **Viewport Height**  360
	- **Mode**: Windowed

- **Stretch**:
	- **Mode**: viewport
	- **Aspect**: keep_height
	- **Scale Mode**: integer

![[project-settings-simple-edit.png]]

<br>

In the upper-right corner, turn on **Advanced Settings** and change the following values:

- **Size**:
	- **Window Width Override**: 1280
	- **Window Height Override**: 720

<br>

---

<br>

## Add Remaining TileMaps

In the **Scene** Dock, select the **GameTileMap** Node. Right click on the Node,  select **Add Child Node...** and add another **TileMapLayer** 2D Node.

![[add-tilemap-layer-edit.png]]

<br>

The new **TileMapLayer** should appear under the **Water** Node in the **Scene** Dock.

Rename the **TileMapLayer** to **Grass** since this layer will be used for the grass tileset.

In the **Inspector** Dock, for the **Tile Set** property, click the **Quick Load...** option and select the **game_tile_set.tres** option.

![[add-grass-tileset-edit.png]]

<br>

#### Add Grass Tileset

In the bottom panel, select **TileSet** and drag the **grass.png** file from the **FileSystem** Dock to the same spot that the **water.png** file was loaded to add it.

Once again, if you see the same popup as before, click **No**.

Make sure the **Setup** tab is active and add the grass tiles you want by clicking to select and highlight them.

Next, click the **Select** tab and click on the upper left corner tile to select the tiles which were highlighted.

![[select-grass-tiles-edit.png]]

<br>

#### Make Grass Terrain

In the **Inspector** Dock, under **TileMapLayer**, make sure **game_tile_set.tres** is selected and a dropdown called **Terrain Sets** is listed.

Under **Terrain Sets** click the **Add Element** button. Expand the **Terrains** dropdown if needed, and click on **Add Element** again to add the terrain.

The default terrain should be called **Terrain 0**. Rename it to **Grass** and select a color that is most visible for painting on top of the tiles (for highlighting the bitmask).

Back in the **TileSet** tab in the bottom panel, look for the dropdown menu titled **Terrains** and expand it. Set the following values:

- **Terrain Set**: 0
- **Terrain**: 0

![[grass-terrain-setup-edit.png]]

<br>

---

<br>

#### Paint Bitmask

Select the **Paint** tab and under **Paint Properties** click on the **Select a property editor** dropdown and choose **Terrains**.

For The **Terrain Set** property, Choose **Terrain Set 0** and for **Terrain**, choose **Grass**.

Manually select each of the tiles which will be have a bitmask applied by clicking on each tile to highlight it. Next, apply the bitmask by painting the mask with the color picked in the previous steps when making the terrain set.

![[grass-bitmask-edit.png]]

<br>

---

<br>

## Using the Bitmask TileMap

In the bottom panel, choose the **TileMap** tab and then choose the **Terrains** tab to show the available terrains. 

You should now see **Terrain Set 0**, which contains the **Grass** terrain. Select the **Grass** terrain and then click on the **Rect Tool** and draw a grass island in the scene. 

![[add-grass-bitmap-edit.png]]

<br>

#### Run the Current Scene

Run the current scene and you should now see something like this (design may vary):

![[run-game-water-grass-edit.png]]

<br>

---

<br>

## Adding Tilled Dirt Layer

Now we repeat the process from the grass layer to create the tilled dirt layer. 

To do this, right-click on **GameTileMap** in the **Scene** Dock and select **Add Child Node...**. Find and select the **TileMapLayer** Node and click the **Create** button at the bottom to confirm.

![[add-tilemap-layer-edit.png]]

<br>

Rename the **TileMapLayer** to **TilledDirt**, and within the **Inspector** Dock, click the **Tile Set** dropdown and select **Quick Load...** and then choose the **Game_tile_set.tres** file.

![[select-tileset-edit.png]]

<br>

---

<br>

#### Add Tilled Dirt TileSet

In the bottom panel, select the **TileSet** tab, and drag the **tilled_dirt_wide.png** file where the **water.png** and **grass.png** files were added.

Click the **No** button if the popup appears again. 

With **Setup** selected, choose the tiles which will be used in the game scene, then click **Select** and click on the upper left tile to select the highlighted tiles.

![[add-tilled-dirt-tileset-edit.png]]

<br>

---

<br>

#### Create Tilled Dirt Terrain

Just like the grass terrain, click on **game_tile_set.tres** within the **Inspector** Dock and add another terrain by clicking the **Add Element** button under the grass terrain. 

Rename the terrain to **Tilled Dirt** and select a color that is most noticeable when painting over the terrain tiles (for the bitmask).

From the **TileSet** tab in the bottom panel, under the **Terrains** dropdown, set the following values:

- **Terrain Set**: 0
- **Terrain**: 1 (because Tilled Dirt is the second terrain created in 0-index).

![[add-tilled-dirt-terrain-edit.png]]

<br>

#### Paint the Bitmap

From the **TileSet** tab in the bottom panel, click the **Paint** tool and change the **Terrain** property value from **Grass** to **Tilled Dirt**. 

Select the tiles which you want to include by left-clicking on them to highlight the tile, and then paint the bitmask after the desired tiles are activated.

![[tilled-dirt-bitmask-edit.png]]

<br>

#### Add Tilled Dirt to Scene

Click the **TileMap** tab in the bottom panel, and you should now see **Tilled Dirt** in the **Terrains** section (under the **Grass** terrain). Click on **Tilled Dirt** to select it.

With the **Rect Tool** selected, add the tilled dirt to the game scene like before with the grass.

![[paint-tilled-dirt-tiles-edit.png]]

<br>

---

<br>

**TODO**: Finish this file