## Create New Project

Use the following settings (project name and path can be unique):

![[create-new-project.png]]

<br>

---

<br>

## Download Game Assets

![[sprout-lands.png]]

**Sprout Lands Asset Pack**: https://cupnooble.itch.io/sprout-lands-asset-pack

<br>

---

<br>

## Godot Layout & Profile Setup

Click on **2D** at the top to switch a 2D Viewport and then change the dock positions in Godot to look like the image below. Once you have the layout setup, save it by navigating to: **Editor** > **Editor Layout** > **Save Layout**.

![[godot-layout-edit.png]]

<br>

#### Manage Editor Feature Profile

Navigate to **Editor** > **Manage Editor Features**. This will open up the **Manage Editor Feature Profiles** window which should by default display no current profile:

![[manage-editor-feature-profiles.png]]

Click on the **Create Profile** button to manage editor features and give it a unique name of your choice. I named it **Main Profile**.

<br>

#### Turn Off 3D

Turn off the 3D aspects by un-checking the box that says **3D Editor** under the **Main Features**. Press the **OK** button at the bottom to confirm changes.

![[manage-editor-features-edit.png]]

<br>

---

<br>

## Add & Configure Game Assets

Unzip the Sprout Lands Asset Pack folder if you have not done so already.

<br>

Within the **FileSystem** dock in the root folder of the game (The path **res://** will always point at the project root), right click and navigate to **Create New** > **Folder** and give it the name **assets**. Press the **OK** button to confirm creation. 

If you see a file called **icon.svg**, you can right click and select **Delete**. Press the **Remove** button to confirm.

You should now only see the **assets** folder under **res://**.

![[assets-folder-edit.png]]


<br>

#### Import & Edit Game Assets

Navigate to the un-zipped Sprout Lands pack, and drag the **Characters**, **Objects** and **Tilesets** folders into the **assets** folder we just created in Godot. 

With the assets now imported, rename every asset folder and file to follow the snake_case naming convention, where all the letters are lowercase, and words are separated by underscores (no spaces). This is good practice and results in a predictable experience across different operating systems.

<br>

Create a new folder within **assets** and give it the name **game** and drag the **characters**, **objects** and **tilesets** folder into **game** to further organize the project.

Your **FileSystem** should now look like this (and all folders/files should be lowercase and following the snake_case style):

![[imported-assets-edit.png]]