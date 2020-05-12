# Project Style Guideline

## 1. General Rules

* Everything should be in **English**.
* You should strictly follow this guideline.
* All structure, assets, and code in our project(s) should look like a single person created it.
* The usages of third-party dependencies should be as less as possible. Licenses should be token into consideration.
* **Do not break the law**
  *  Don't distribute content you don't have the rights to distribute
  * Don't infringe on someone else's copyrighted or trademark material
  * Don't steal content
  * Follow licensing restrictions on content, e.g. attribute when attributions are needed

## 2. C++ Code: [Epic's Coding Standard](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard)

### 2.1 General Rules

* All feature or bug fixes **must be tested** by one or more unit-tests.
* All API must be documented.
* Do not submmit broken code to version control system.

### 2.2 Naming Conventions

* The first of each word in a **name**(such as **type name** or **variable name**) is **capitalized**, and there is usually **no underscore between words**. For example, `Health` and `UPrimitiveComponent` are correct, but not `lastMouseCoordinates` or `delta_coordinate`.
* **Type names** are **prefixed** with an additional **upper-case letter** to distinguish them from variable names. For example, `FSkin` is a typename, and `Skin` is an instance of `FSkin`.
  * Template classes are prefixed by `T`
  * Classes that inherit from `UObject` are prefixed by `U` 
  * <!--TODO-->

## 3. Unreal Assets

## 3.1 Asset Naming Conventions

Naming conventions should be treated as law. A project that conforms to a naming convention is able to have its assets managed, searched, parsed, and maintained with incredible ease.

Most things are prefixed with prefixes being generally an acronym of the asset type followed by an underscore.

### 3.1.1 Base Asset Name `Prefix_BaseAssetName_Variant_Suffix`

* `BaseAssetName` should be determined by a **short and easily recognizable name** that represents logical name related to the context of this group of assets. For example, if you have a character named Bob, all of Bob's assets should have the `BaseAssetName` of `Bob`.
* `Prefix` and `Suffix` are to be determined by the asset type through the following [3.1.2 Asset Name Modifiers](#3.1.2)
* `Variant` is either a short and easily recognizable name that represents logical grouping of assets that are a subset of an asset's base name for unique and specific variations of assets, or **a two digital number starting at `01`** for unique but generic variations of assets. 
* Variant names can be chained together depending on how your asset variants are made.

#### 3.1.1.1 Examples

##### Bob

| Asset Type               | Asset Name   |
| ------------------------ | ------------ |
| Skeletal Mesh            | SK_Bob       |
| Material                 | M_Bob        |
| Texture (Diffuse/Albedo) | T_Bob_D      |
| Texture (Normal)         | T_Bob_N      |
| Texture (Evil Diffuse)   | T_Bob_Evil_D |

##### Rocks

| Asset Type               | Asset Name   |
| ------------------------ | ------------ |
| Static Mesh (01)         | S_Rock_01    |
| Static Mesh (02)         | S_Rock_02    |
| Static Mesh (03)         | S_Rock_03    |
| Material                 | M_Rock       |
| Material Instance (Snow) | MI_Rock_Snow |

### 3.1.2 Asset Name Modifiers

#### 3.1.2.1 Common Assets

| Asset Type         | Prefix | Suffix    | Notes                                                        |
| ------------------ | ------ | --------- | ------------------------------------------------------------ |
| Level/Map          |        |           | Should be in a folder called Maps <!--TODO link to directory structures--> |
| Level (Persistent) |        | _P        |                                                              |
| Level (Audio)      |        | _Audio    |                                                              |
| Level (Lighting)   |        | _Lighting |                                                              |
| Level (Geometry)   |        | _Geo      |                                                              |
| Level (Gameplay)   |        | _Gameplay |                                                              |
| Blueprint          | BP_    |           |                                                              |
| Material           | M_     |           |                                                              |
| Static Mesh        | S_     |           | Do not use SM_                                               |
| Skeletal Mesh      | SK_    |           |                                                              |
| Texture            | T_     | _?        | See <!--TDOO link to textures-->                             |
| Particle System    | PS_    |           |                                                              |
| Widget Blueprint   | WBP_   |           |                                                              |

#### 3.1.2.2 Animations

| Animation Type      | Prefix | Suffix | Note |
| ------------------- | ------ | ------ | ---- |
| Aim Offset          | AO_    |        |      |
| Aim Offset 1D       | AO_    |        |      |
| Animation Blueprint | ABP_   |        |      |
| Animation Composite | AC_    |        |      |
| Animation Montage   | AM_    |        |      |
| Animation Sequence  | A_     |        |      |
| Blend Space         | BS_    |        |      |
| Blend Space 1D      | BS_    |        |      |
| Level Sequence      | LS_    |        |      |
| Morph Target        | MT_    |        |      |
| Paper Flipbook      | PFB_   |        |      |
| Rig                 | RIG_   |        |      |
| Skeletal Mesh       | SK_    |        |      |
| Skeleton            | SKEL_  |        |      |

#### 3.1.2.3 Artificial Intelligence

| Asset Type        | Prefix       | Suffix | Note |
| ----------------- | ------------ | ------ | ---- |
| AI Controller     | AIC_         |        |      |
| Behaviour Tree    | BT_          |        |      |
| Blackboard        | BB_          |        |      |
| Decorator         | BTDecorator_ |        |      |
| Service           | BTService_   |        |      |
| Task              | BTTask_      |        |      |
| Environment Query | EQS_         |        |      |
| EnvQueryContext   | EQS_         |        |      |

#### 3.1.2.4 Blueprint

| Asset Type                 | Prefix | Suffix                       | Note                       |
| -------------------------- | ------ | ---------------------------- | -------------------------- |
| Blueprint                  | BP_    |                              |                            |
| Blueprint Component        | BP_    | \_<Component Name\>Component | i.e. BP_InventoryComponent |
| Blueprint Function Library | BPFL_  |                              |                            |
| Blueprint Interface        | BPL_   |                              |                            |
| Blueprint Marco Library    | BPML_  |                              | Do not use if possible     |
| Enumeration                | E      |                              | No underscore              |
| Structure                  | F or S |                              | No underscore              |
| Tutorial Blueprint         | TBP_   |                              |                            |
| Widget Blueprint           | WBP_   |                              |                            |

#### 3.1.2.5 Materials

| Asset Type                    | Prefix   | Suffix | Notes |
| ----------------------------- | -------- | ------ | ----- |
| Material                      | M_       |        |       |
| Material (Post Process)       | PP_      |        |       |
| Material Function             | MF_      |        |       |
| Material Instance             | MI_      |        |       |
| Material Parameter Collection | MPC_     |        |       |
| Subsurface Profile            | SP_      |        |       |
| Physical Materials            | PM_      |        |       |
| Decal                         | M_, Ml\_ | _Decal |       |

#### 3.1.2.6 Textures

| Asset Type                          | Prefix | Suffix | Notes |
| ----------------------------------- | ------ | ------ | ----- |
| Texture                             | T_     |        |       |
| Texture (Diffuse/Albedo/Base Color) | T_     | _D     |       |
| Texture (Normal)                    | T_     | _N     |       |
| Texture (Roughness)         | T_   | _R   |      |
| Texture (Alpha/Opacity)     | T_   | _A   |      |
| Texture (Ambient Occlusion) | T_   | _O   |      |
| Texture (Bump)              | T_   | _B   |      |
| Texture (Emissive)          | T_   | _E   |      |
| Texture (Mask)              | T_   | _M   |      |
| Texture (Specular)          | T_   | _S   |      |
| Texture (Metallic)          | T_   | _M   |      |
| Texture Cube          | TC_  |      |      |
| Media Texture         | MT_  |      |      |
| Render Target         | RT_  |      |      |
| Cube Render Target    | RTC_ |      |      |
| Texture Light Profile | TLP  |      |      |
| Texture (Packed)      | T_   | _*   | See [Note: Texture Packing](#note:-texture-packing) |

##### Note: Texture Packing

It is common practice to pack multiple layers of texture data into one texture. An example of this is packing Emissive, Roughness, Ambient Occlusion together as the Red, Green, and Blue channels of a texture respectively. To determine the suffix, simply stack the given suffix letters from above together, e.g. `_ERO`.

> It is generally acceptable to include an Alpha/Opacity layer in your Diffuse/Albedo's alpha channel and as this is common practice, adding `A` to the `_D` suffix is optional.

Packing 4 channels of data into a texture (RGBA) is not recommended except for an Alpha/Opacity mask in the Diffuse/Albedo's alpha channel as a texture with an alpha channel incurs more overhead than one without.

#### 3.1.2.7 Miscellaneous 

| Asset Type                 | Prefix   | Suffix  | Notes                           |
| -------------------------- | -------- | ------- | ------------------------------- |
| Animated Vector Field      | VFA_     |         |                                 |
| Camera Anim                | CA_      |         |                                 |
| Color Curve                | Curve_   | _Color  |                                 |
| Curve Table                | Curve_   | _Table  |                                 |
| Data Asset                 | *_       |         | Prefix should be based on class |
| Data Table                 | DT_      |         |                                 |
| Float Curve                | Curve_   | _Float  |                                 |
| Foliage Type               | FT_      |         |                                 |
| Force Feedback Effect      | FFE_     |         |                                 |
| Landscape Grass Type       | LG_      |         |                                 |
| Landscape Layer            | LL_      |         |                                 |
| Matinee Data               | Matinee_ |         |                                 |
| Media Player               | MP_      |         |                                 |
| Object Library             | OL_      |         |                                 |
| Redirector                 |          |         | These should be fixed up ASAP   |
| Sprite Sheet               | SS_      |         |                                 |
| Static Vector Field        | VF_      |         |                                 |
| Substance Graph Instance   | SGI_     |         |                                 |
| Substance Instance Factory | SIF_     |         |                                 |
| Touch Interface Setup      | TI_      |         |                                 |
| Vector Curve               | Curve_   | _Vector |                                 |

#### 3.1.2.8 Paper 2D

| Asset Type         | Prefix | Suffix | Notes |
| ------------------ | ------ | ------ | ----- |
| Paper Flipbook     | PFB_   |        |       |
| Sprite             | SPR_   |        |       |
| Sprite Atlas Group | SPRG_  |        |       |
| Tile Map           | TM_    |        |       |
| Tile Set           |        |        |       |

#### 3.1.2.9 Physics

| Asset Type        | Prefix | Suffix | Notes |
| ----------------- | ------ | ------ | ----- |
| Physical Material | PM_    |        |       |
| Physical Asset    | PHYS_  |        |       |
| Destructible Mesh | DM_    |        |       |

#### 3.1.2.10 Sounds

| Asset Type        | Prefix  | Suffix | Notes                                                        |
| ----------------- | ------- | ------ | ------------------------------------------------------------ |
| Dialogue Voice    | DV_     |        |                                                              |
| Dialogue Wave     | DW_     |        |                                                              |
| Media Sound Wave  | MSW_    |        |                                                              |
| Reverb Effect     | Reverb_ |        |                                                              |
| Sound Attenuation | ATT_    |        |                                                              |
| Sound Class       |         |        | No prefix/suffix. Should be put in a folder called SoundClasses |
| Sound Concurrency |         | _SC    | Should be named after a SoundClass                           |
| Sound Cue         | A_      | _Cue   |                                                              |
| Sound Mix         | Mix_    |        |                                                              |
| Sound Wave        | A_      |        |                                                              |

#### 3.1.2.11 User Interface

| Asset Type         | Prefix | Suffix | Notes |
| ------------------ | ------ | ------ | ----- |
| Font               | Font_  |        |       |
| Slate Brush        | Brush_ |        |       |
| Slate Widget Style | Style_ |        |       |
| Widget Blueprint   | WBP_   |        |       |

#### 3.1.2.12 Effects

| Asset Type              | Prefix | Suffix | Notes |
| ----------------------- | ------ | ------ | ----- |
| Particle System         | PS_    |        |       |
| Material (Post Process) | PP_    |        |       |

### 3.3 Content Directory Structure

Equally important as asset names, the directory structure style of a project should be considered law. Asset naming conventions and content directory structure go hand in hand, and a violation of either causes unneeded chaos.

There are multiple ways to lay out the content of a UE4 project. In this style, we will be using a structure that relies more on filtering and search abilities of the Content Browser for those working with assets to find assets of a specific type instead of another common structure that groups asset types with folders.

> If you are using the prefix [naming convention](#3.1.2) above, using folders to contain assets of similar types such as `Meshes`, `Textures`, and `Materials` is a redundant practice as asset types are already both sorted by prefix as well as able to be filtered in the content browser.

Here is a example project content structure:

```
|-- Content
    |-- GenericShooter
        |-- Art
        |   |-- Industrial
        |   |   |-- Ambient
        |   |   |-- Machinery
        |   |   |-- Pipes
        |   |-- Nature
        |   |   |-- Ambient
        |   |   |-- Foliage
        |   |   |-- Rocks
        |   |   |-- Trees
        |   |-- Office
        |-- Characters
        |   |-- Bob
        |   |-- Common
        |   |   |-- Animations
        |   |   |-- Audio
        |   |-- Jack
        |   |-- Steve
        |   |-- Zoe
        |-- Core
        |   |-- Characters
        |   |-- Engine
        |   |-- GameModes
        |   |-- Interactables
        |   |-- Pickups
        |   |-- Weapons
        |-- Effects
        |   |-- Electrical
        |   |-- Fire
        |   |-- Weather
        |-- Maps
        |   |-- Campaign1
        |   |-- Campaign2
        |-- MaterialLibrary
        |   |-- Debug
        |   |-- Metal
        |   |-- Paint
        |   |-- Utility
        |   |-- Weathering
        |-- Placeables
        |   |-- Pickups
        |-- Weapons
            |-- Common
            |-- Pistols
            |   |-- DesertEagle
            |   |-- RocketPistol
            |-- Rifles
```

The reasons for this structure are listed in the following sub-sections.

#### 3.3.1 Folder Name

These are common rules for naming any folder in the content structure.

##### 3.3.1.1 Always Use PascalCase

PascalCase refers to starting a name with a capital letter and then instead of using spaces, every following word also starts with a capital letter. For example, `DesertEagle`, `RocketPistol`, and `ASeriesOfWords`.

##### 3.3.1.2 Never Use Spaces

Re-enforcing [3.3.1.1 Always Use PascalCase](#3.3.1.1), never use spaces. Spaces can cause various engineering tools and batch processes to fail. Ideally, your project's root also contains no spaces and is located somewhere such as `D:\Project` instead of `C:\Users\My Name\My Documents\Unreal Projects`.

##### 3.3.1.3 Never Use Unicode Characters And Other Symbols (Including Chinese)

f one of your game characters is named 'Zoë', its folder name should be `Zoe`. Unicode characters can be worse than spaces for engineering tool and some parts of UE4 don't support Unicode characters in paths either.

Related to this, if your project has [unexplained issues](https://answers.unrealengine.com/questions/101207/undefined.html) and your computer's user name has a Unicode character (i.e. your name is `Zoë`), any project located in your `My Documents` folder will suffer from this issue. Often simply moving your project to something like `D:\Project` will fix these mysterious issues.

Using other characters outside `a-z`, `A-Z`, and `0-9` such as `@`, `-`, `_`, `,`, `*`, and `#` can also lead to unexpected and hard to track issues on other platforms, source control, and weaker engineering tools.

#### 3.3.2 Use A Top Level Folder For Project Specific Assets

All of a project's assets should exist in a folder named after the project. For example, if your project is named 'Generic Shooter', *all* of it's content should exist in `Content/GenericShooter`.

> The `Developers` folder is not for assets that your project relies on and therefore is not project specific. See [Developer Folders](#3.3.3 for details about this.

There are multiple reasons for this approach.

#### 3.3.2.1 No Global Assets

Often in code style guides it is written that you should not pollute the global namespace and this follows the same principle. When assets are allowed to exist outside of a project folder it often becomes much harder to enforce a strict structure layout as assets not in a folder encourages the bad behavior of not having to organize assets.

Every asset should have a purpose, otherwise it does not belong in a project. If an asset is an experimental test and shouldn't be used by the project it should be put in a `Developer` folder.

#### 3.3.2.2 Reduce Migration Conflicts

When working on multiple projects it is common for a team to copy assets from one project to another if they have made something useful for both. When this occurs, the easiest way to perform the copy is to use the Content Browser's Migrate functionality as it will copy over not just the selected asset but all of its dependencies.

These dependencies are what can easily get you into trouble. If two project's assets do not have a top level folder and they happen to have similarly named or already previously migrated assets, a new migration can accidentally wipe any changes to the existing assets.

This is also the primary reason why Epic's Marketplace staff enforces the same policy for submitted assets.

After a migration, safe merging of assets can be done using the 'Replace References' tool in the content browser with the added clarity of assets not belonging to a project's top level folder are clearly pending a merge. Once assets are merged and fully migrated, there shouldn't be another top level folder in your Content tree. This method is *100%* guaranteed to make any migrations that occur completely safe.

##### Example: Master Material Example

For example, say you created a master material in one project that you would like to use in another project so you migrated that asset over. If this asset is not in a top level folder, it may have a name like `Content/MaterialLibrary/M_Master`. If the target project doesn't have a master material already, this should work without issue.

As work on one or both projects progress their respective master materials may change to be tailored for their specific projects due to the course of normal development.

The issue comes when, for example, an artist for one project created a nice generic modular set of static meshes and someone wants to include that set of static meshes in the second project. If the artist who created the assets used material instances based on `Content/MaterialLibrary/M_Master` as they're instructed to, when a migration is performed there is a great chance of conflict for the previously migrated `Content/MaterialLibrary/M_Master` asset.

This issue can be hard to predict and hard to account for. The person migrating the static meshes may not be the same person who is familiar with the development of both project's master material, and they may not be even aware that the static meshes in question rely on material instances which then rely on the master material. The Migrate tool requires the entire chain of dependencies to work however, and so it will be forced to grab `Content/MaterialLibrary/M_Master` when it copies these assets to the other project and it will overwrite the existing asset.

It is at this point where if the master materials for both projects are incompatible in *any way*, you risk breaking possibly the entire material library for a project as well as any other dependencies that may have already been migrated, simply because assets were not stored in a top level folder. The simple migration of static meshes now becomes a very ugly task.

#### 3.3.2.3 Samples, Templates, and Marketplace Content Are Risk-Free

An extension to [3.3.2.2](#3.2.2.2), if a team member decides to add sample content, template files, or assets they bought from the marketplace, it is guaranteed, as long your project's top-level folder is uniquely named, these new assets will not interfere with your project.

You can not trust marketplace content to fully conform to the top level folder rule. There exist many assets that have the majority of their content in a top level folder but also have possibly modified Epic sample content as well as level files polluting the global `Content` folder.

When adhering to [3.3.2](#3.3.2), the worst marketplace conflict you can have is if two marketplace assets both have the same Epic sample content. If all your assets are in a project specific folder, including sample content you may have moved into your folder, your project will never break.

#### 3.3.2.4 DLC, Sub-Projects, and Patches Are Easily Maintained

If your project plans to release DLC or has multiple sub-projects associated with it that may either be migrated out or simply not cooked in a build, assets relating to these projects should have their own separate top level content folder. This make cooking DLC separate from main project content far easier. Sub-projects can also be migrated in and out with minimal effort. If you need to change a material of an asset or add some very specific asset override behavior in a patch, you can easily put these changes in a patch folder and work safely without the chance of breaking the core project.

### 3.3.3 Use `Developers` Folder For Local Testing

During a project's development, it is very common for team members to have a sort of 'sandbox' where they can experiment freely without risking the core project. Because this work may be ongoing, these team members may wish to put their assets on a project's source control server. Not all teams require use of Developer folders, but ones that do use them often run into a common problem with assets submitted to source control.

It is very easy for a team member to accidentally use assets that are not ready for use which will cause issues once those assets are removed. For example, an artist may be iterating on a modular set of static meshes and still working on getting their sizing and grid snapping correct. If a world builder sees these assets in the main project folder, they might use them all over a level not knowing they could be subject to incredible change and/or removal. This causes massive amounts of re-working by everyone on the team to resolve.

If these modular assets were placed in a Developer folder, the world builder should never of had a reason to use them and the whole issue would never happen. The Content Browser has specific View Options that will hide Developer folders (they are hidden by default) making it impossible to accidentally use Developer assets under normal use.

Once the assets are ready for use, an artist simply has to move the assets into the project specific folder and fix up redirectors. This is essentially 'promoting' the assets from experimental to production.

### 3.3.4 All Map Files Belong In A Folder Called Maps

Map files are incredibly special and it is common for every project to have its own map naming system, especially if they work with sub-levels or streaming levels. No matter what system of map organization is in place for the specific project, all levels should belong in `/Content/Project/Maps`.

Being able to tell someone to open a specific map without having to explain where it is is a great time saver and general 'quality of life' improvement. It is common for levels to be within sub-folders of `Maps`, such as `Maps/Campaign1/` or `Maps/Arenas`, but the most important thing here is that they all exist within `/Content/Project/Maps`.

This also simplifies the job of cooking for engineers. Wrangling levels for a build process can be extremely frustrating if they have to dig through arbitrary folders for them. If a team's maps are all in one place, it is much harder to accidentally not cook a map in a build. It also simplifies lighting build scripts as well as QA processes.

#### 3.3.5 Use A `Core` Folder For Critical Blueprints And Other Assets

Use `/Content/Project/Core` folder for assets that are absolutely fundamental to a project's workings. For example, base `GameMode`, `Character`, `PlayerController`, `GameState`, `PlayerState`, and related Blueprints should live here.

This creates a very clear "don't touch these" message for other team members. Non-engineers should have very little reason to enter the `Core` folder. Following good code structure style, designers should be making their gameplay tweaks in child classes that expose functionality. World builders should be using prefab Blueprints in designated folders instead of potentially abusing base classes.

For example, if your project requires pickups that can be placed in a level, there should exist a base Pickup class in `Core/Pickups` that defines base behavior for a pickup. Specific pickups such as a Health or Ammo should exist in a folder such as `/Content/Project/Placeables/Pickups/`. Game designers can define and tweak pickups in this folder however they please, but they should not touch `Core/Pickups` as they may unintentionally break pickups project-wide.

#### 3.3.6 Do Not Create Folders Called `Assets` or `AssetTypes`

##### 3.3.6.1 Creating a folder named `Assets` is redundant.

All assets are assets.

##### 3.3.6.2 Creating a folder named `Meshes`, `Textures`, or `Materials` is redundant.

All asset names are named with their asset type in mind. These folders offer only redundant information and the use of these folders can easily be replaced with the robust and easy to use filtering system the Content Browser provides.

Want to view only static mesh in `Environment/Rocks/`? Simply turn on the Static Mesh filter. If all assets are named correctly, they will also be sorted in alphabetical order regardless of prefixes. Want to view both static meshes and skeletal meshes? Simply turn on both filters. This eliminates the need to potentially have to `Control-Click` select two folders in the Content Browser's tree view.

> This also extends the full path name of an asset for very little benefit. The `S_` prefix for a static mesh is only two characters, whereas `Meshes/` is seven characters.

Not doing this also prevents the inevitability of someone putting a static mesh or a texture in a `Materials` folder.

### 3.3.7 Very Large Asset Sets Get Their Own Folder Layout

This can be seen as a pseudo-exception to [3.3.6](#3.3.6).

There are certain asset types that have a huge volume of related files where each asset has a unique purpose. The two most common are Animation and Audio assets. If you find yourself having 15+ of these assets that belong together, they should be together.

For example, animations that are shared across multiple characters should lay in `Characters/Common/Animations` and may have sub-folders such as `Locomotion` or `Cinematic`.

> This does not apply to assets like textures and materials. It is common for a `Rocks` folder to have a large amount of textures if there are a large amount of rocks, however these textures are generally only related to a few specific rocks and should be named appropriately. Even if these textures are part of a [Material Library](#3.3.8).

### 3.3.8 Material Library

If your project makes use of master materials, layered materials, or any form of reusable materials or textures that do not belong to any subset of assets, these assets should be located in `Content/Project/MaterialLibrary`.

This way all 'global' materials have a place to live and are easily located.

> This also makes it incredibly easy to enforce a 'use material instances only' policy within a project. If all artists and assets should be using material instances, then the only regular material assets that should exist are within this folder. You can easily verify this by searching for base materials in any folder that isn't the `MaterialLibrary`.

The `MaterialLibrary` doesn't have to consist of purely materials. Shared utility textures, material functions, and other things of this nature should be stored here as well within folders that designate their intended purpose. For example, generic noise textures should be located in `MaterialLibrary/Utility`.

Any testing or debug materials should be within `MaterialLibrary/Debug`. This allows debug materials to be easily stripped from a project before shipping and makes it incredibly apparent if production assets are using them if reference errors are shown.

### 3.3.9 No Empty Folders

There simply shouldn't be any empty folders. They clutter the content browser.

If you find that the content browser has an empty folder you can't delete, you should perform the following:

1. Be sure you're using source control.
2. Immediately run Fix Up Redirectors on your project.
3. Navigate to the folder on-disk and delete the assets inside.
4. Close the editor.
5. Make sure your source control state is in sync (i.e. if using Perforce, run a Reconcile Offline Work on your content directory)
6. Open the editor. Confirm everything still works as expected. If it doesn't, revert, figure out what went wrong, and try again.
7. Ensure the folder is now gone.
8. Submit changes to source control.

## 3.4 Blueprints

This section will focus on Blueprint classes and their internals. When possible, style rules conform to [Epic's Coding Standard](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard).

Remember: Blueprinting badly bears blunders, beware! 

<!--TODO-->

### 3.4.1 Compiling

All blueprints should compile with zero warnings and zero errors. You should fix blueprint warnings and errors immediately as they can quickly cascade into very scary unexpected behavior.

**Do *not* submit broken blueprints to source control.** If you must store them on source control, shelve them instead.

Broken blueprints can cause problems that manifest in other ways, such as broken references, unexpected behavior, cooking failures, and frequent unneeded recompilation. A broken blueprint has the power to break your entire game.

### 3.4.2 Variables

The words `variable` and `property` may be used interchangeably.

#### 3.4.2.1 Naming

##### 3.4.2.1.1 Nouns

All non-boolean variable names must be clear, unambiguous, and descriptive nouns.

##### 3.4.2.1.2 PascalCase

All non-boolean variable should be in the form of PascalCase. 

For example: `Score` ,`Kills`, `TargetPlayer`, `Range`, `CrosschairColor`, `AbilityID`.

##### 3.4.2.1.3 Boolean `b` Prefix

All bollean should be named in PascalCase but prefixed with a lowercase `b`.

For example: use `bDead` instead of `dead`, use `bEvil` instead of `evil`.

UE4 Blueprint editors know not to include the `b` in user-friendly displays of the variable.

##### 3.4.2.1.4 Boolean Names

###### 3.4.2.1.4.1 General And Independent State Information

All booleans should be named as descriptive adjectives when possible if representing general information. Do not include words that phrase the variable as a question, such as `Is`. This is reserved for functions.

Example: Use `bDead` and `bHostile` **not** `bIsDead` and `bIsHostile`.

Try to not use verbs such as `bRunning`. Verbs tend to lead to complex states.

###### 3.4.2.1.4.2 Complex States

Do not to use booleans to represent complex and/or dependent states. This makes state adding and removing complex and no longer easily readable. Use an enumeration instead.

Example: When defining a weapon, do **not** use `bReloading` and `bEquipping` if a weapon can't be both reloading and equipping. Define an enumeration named `EWeaponState` and use a variable with this type named `WeaponState` instead. This makes it far easier to add new states to weapons.

For example: Do **not** use `bRunning` if you also need `bWalking` or `bSprinting`. This should be defined as an enumeration with clearly defined state names.

##### 3.4.2.1.5 Considered Context

All variable names must not be redundant with their context as all variable references in Blueprint will always have context.

For example, consider a Blueprint called `BP_PlayerCharacter`.

| Bad                 | Good         |
| ------------------- | ------------ |
| PlayerScore         | Score        |
| PlayerKill          | Kill         |
| MyTargetPlayer      | TargetPlayer |
| MyCharacterName     | Name         |
| CharacterSkills     | Skills       |
| ChosenCharacterSkin | Skin         |

All of the variables on the left side are named redundantly. It is implied that the variable is representative of the `BP_PlayerCharacter` it belongs to because it is `BP_PlayerCharacter` that is defining these variables.

##### 3.4.2.1.6 Do *Not* Include Atomic Type Names

Atomic or primitive variables are variables that represent data in their simplest form, such as booleans, integers, floats, and enumerations.

Strings and vectors are considered atomic in terms of style when working with Blueprints, however they are technically not atomic.

> While vectors consist of three floats, vectors are often able to be manipulated as a whole, same with rotators.

> Do *not* consider Text variables as atomic, they are secretly hiding localization functionality. The atomic type of a string of characters is `String`, not `Text`.

Atomic variables should not have their type name in their name.

Example: Use `Score`, `Kills`, and `Description` **not** `ScoreFloat`, `FloatKills`, `DescriptionString`.

The only exception to this rule is when a variable represents 'a number of' something to be counted *and* when using a name without a variable type is not easy to read.

Example: A fence generator needs to generate X number of posts. Store X in `NumPosts` or `PostsCount` instead of `Posts` as `Posts` may potentially read as an Array of a variable type named `Post`.

##### 3.4.2.1.7 Do Include Non-Atomic Type Names

Non-atomic or complex variables are variables that represent data as a collection of atomic variables. Structs, Classes, Interfaces, and primitives with hidden behavior such as `Text` and `Name` all qualify under this rule.

> While an Array of an atomic variable type is a list of variables, Arrays do not change the 'atomicness' of a variable type.

These variables should include their type name while still considering their context.

If a class owns an instance of a complex variable, i.e. if a `BP_PlayerCharacter` owns a `BP_Hat`, it should be stored as the variable type as without any name modifications.

Example: Use `Hat`, `Flag`, and `Ability` **not** `MyHat`, `MyFlag`, and `PlayerAbility`.

If a class does not own the value a complex variable represents, you should use a noun along with the variable type.

Example: If a `BP_Turret` has the ability to target a `BP_PlayerCharacter`, it should store its target as `TargetPlayer` as when in the context of `BP_Turret` it should be clear that it is a reference to another complex variable type that it does not own.

##### 3.4.2.1.8 Arrays

Arrays follow the same naming rules as above, but should be named as a plural noun.

For example: Use `Targets`, `Hats`, and `EnemyPlayers`, **not** `TargetList`, `HatArray`, `EnemyPlayerArray`.

#### 3.4.2.2 Editable Variable

All variables that are safe to change the value of in order to configure behavior of a blueprint should be marked as `Editable`.

Conversely, all variables that are not safe to change or should not be exposed to designers should *not* be marked as editable, unless for engineering reasons the variable must be marked as `Expose On Spawn`.

Do not arbitrarily mark variables as `Editable`.

##### 3.4.2.2.1 Tooltips

All `Editable` variables, including those marked editable just so they can be marked as `Expose On Spawn`, should have a description in their `Tooltip` fields that explains how changing this value affects the behavior of the blueprint.

##### 3.4.2.2.2 Slider And Value Ranges

All `Editable` variables should make use of slider and value ranges if there is ever a value that a variable should *not* be set to.

Example: A blueprint that generates fence posts might have an editable variable named `PostsCount` and a value of -1 would not make any sense. Use the range fields to mark 0 as a minimum.

If an editable variable is used in a Construction Script, it should have a reasonable Slider Range defined so that someone can not accidentally assign it a large value that could crash the editor.

A Value Range only needs to be defined if the bounds of a value are known. While a Slider Range prevents accidental large number inputs, an undefined Value Range allows a user to specify a value outside the Slider Range that may be considered 'dangerous' but still valid.

#### 3.4.2.3 Categories

If a class has only a small number of variables, categories are not required.

If a class has a moderate amount of variables (5-10), all `Editable` variables should have a non-default category assigned. A common category is `Config`.

If a class has a large amount of variables, all `Editable` variables should be categorized into sub-categories using the category `Config` as the base category. Non-editable variables should be categorized into descriptive categories describing their usage.

> You can define sub-categories by using the pipe character `|`, i.e. `Config | Animations`.

Example: A weapon class set of variables might be organized as:

```
|-- Config
|	|-- Animations
|	|-- Effects
|	|-- Audio
|	|-- Recoil
|	|-- Timings
|-- Animations
|-- State
|-- Visuals
```

#### 3.4.2.4 Variable Access Level

In C++, variables have a concept of access level. Public means any code outside the class can access the variable. Protected means only the class and any child classes can access this variable internally. Private means only this class and no child classes can access this variable.

Blueprints do not have a defined concept of protected access currently.

Treat `Editable` variables as public variables. Treat non-editable variables as protected variables.

##### 3.4.2.4.1 Private Variables

Unless it is known that a variable should only be accessed within the class it is defined and never a child class, do not mark variables as private. Until variables are able to be marked `protected`, reserve private for when you absolutely know you want to restrict child class usage.

#### 3.4.2.5 Advanced Display

If a variable should be editable but often untouched, mark it as `Advanced Display`. This makes the variable hidden unless the advanced display arrow is clicked.

To find the `Advanced Display` option, it is listed as an advanced displayed variable in the variable details list.

#### 3.4.2.6 Transient Variables

Transient variables are variables that do not need to have their value saved and loaded and have an initial value of zero or null. This is useful for references to other objects and actors who's value isn't known until run-time. This prevents the editor from ever saving a reference to it, and speeds up saving and loading of the blueprint class.

Because of this, all transient variables should always be initialized as zero or null. To do otherwise would result in hard to debug errors.

#### 3.4.2.7 Advanced Display

If a variable should be editable but often untouched, mark it as `Advanced Display`. This makes the variable hidden unless the advanced display arrow is clicked.

To find the `Advanced Display` option, it is listed as an advanced displayed variable in the variable details list.

#### 3.4.2.8 Config Variables

Do not use the `Config Variable` flag. This makes it harder for designers to control blueprint behavior. Config variables should only be used in C++ for rarely changed variables. Think of them as `Advanced Advanced Display` variables.

### 3.4.3 Functions, Events and Event Dispatchers

<!--TODO naming, return node, number of nodes restriction, description, categorize-->

## 3.5 Static Meshes

<!--TODO ?-->

## 3.6 Maps / Levels

<!--TODO ?-->

## 3.7 Textures

<!--TODO ?-->

## 3.8 Animations

<!--TODO-->

## 3.9 Media Format

<!--TODO ?-->

## 4. Version Control (Git)

### 4.1 General Rules

* Do not leave unnecessary binary in the history (build cache, debug log, etc...).
* Track binary assets using git lfs.
* All the commit messages should follow [Commit Message Rules](#4.2).
* **Never force push.**
* Inform maintainer before performing a merge operation.
* Do not consider the version control system as a cloud drive.
* One feature( or fix), one commit.
* Do not submmit unfinished work. 

### 4.2 Commit Messages

We have very precise rules over how our git commit messages can be formatted. This leads to **more readable messages** that are easy to follow when looking through the **project history**. But also, we use the git commit messages to **generate the change log**.

#### 4.2.1 Commit Message Format

Each commit message consists of a **header**, a **body** and a **footer**. The header has a special format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer than 100 characters! This allows the message to be easier to read on GitHub as well as in various git tools.

The footer should contain a [closing reference to an issue](https://help.github.com/articles/closing-issues-via-commit-messages/) if any.

```
docs(changelog): update changelog to beta.5
fix(release): need to depend on latest rxjs and zone.js

The version in our package.json gets copied to the one we publish, and users need the latest of these.
```

#### 4.2.2 Revert

If the commit reverts a previous commit, it should begin with `revert: `, followed by the header of the reverted commit. In the body it should say: `This reverts commit .`, where the hash is the SHA of the commit being reverted.

#### 4.2.3 Type

Must be one of the following:

- **build**: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
- **ci**: Changes to our CI configuration files and scripts (example scopes: Circle, BrowserStack, SauceLabs)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- **test**: Adding missing tests or correcting existing tests

#### 4.2.4 Scope

The scope should be the name of the part of code affected (as perceived by the person reading the changelog generated from commit messages).

<!--TODO show supported scopes-->

#### 4.2.5 Subject

The subject contains a succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- don't capitalize the first letter
- no dot (.) at the end

#### 4.2.6 Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.

#### 4.2.7 Footer

The footer should contain any information about **Breaking Changes** and is also the place to reference GitHub issues that this commit **Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

---

Author 方泓睿 
