# CIS 5660 HW03 Procedural Buildings

<p float="center">
 <img src="/asset/cover.gif" width="55%" />
</p>

https://github.com/user-attachments/assets/1b8dd8a9-1b7a-470c-abf8-b0b151a99bb7



## Project Overview
This is a Houdini procudural building project that gives artists controls over the building shape attributes as well as asset attributes.

All the assets are created inside Houdini.

## Observe the Reference Photo
The building style I want to replicate is traditional Yemen architect. I found them very procedural and I really like the decoration patterns on the wall :)


<p float="center">
 <img src="https://github.com/user-attachments/assets/140ef000-9f15-4bfa-8d52-a99063e450a6" width="25%" />
 <img src="https://github.com/user-attachments/assets/29d475e9-e0d4-4a0d-96ea-cf8834421bbf" width="45%" />
  <img src="https://github.com/user-attachments/assets/ce0ea8da-7d41-4187-802f-b5ee410e7359" width="25%" />
</p>

Take a close look at the real photos, we will have the following core features:

1. Two-layer windows. A round shape + a square shape
2. No two-layer windows for the first floor, only small windows.
3. Decoration strips between each floor.
4. Special shape and extended flagpole on the roof.

## Features
### Assets
I made four assets: two-layer large window, small window, door and balcony. Beside from balcony that match size with the door, other three types of assets have their individual controls.

![image](https://github.com/user-attachments/assets/295f8b0b-d0a7-43d0-85ab-64bba1f3d0d7)

You can toogle the attribute of each asset in the round green control button.

---

#### Large Windows
![image](https://github.com/user-attachments/assets/0f2ef119-cd50-4db6-a6ce-74167b7ebf06)

You can change the divide numbers for the window frames and also the overall width and height to the entire window.

<p float="center">
 <img src="/asset/window1.gif" width="35%" />
</p>



The node network for large windows:

<p float="center">
 <img src="https://github.com/user-attachments/assets/41c5e455-0c1d-4e4d-8aa0-021abf35948b" width="55%" />
</p>

#### Small Windows
I provided the user with two types of small windows: around and square. For each floor, user can select which type they want to use. They can also adjust the overall width and height with the green around little control handle.

![image](https://github.com/user-attachments/assets/700b37d1-7923-482f-9c34-ac8e2bda12ee)


<p float="center">
 <img src="/asset/window2.gif" width="45%" />
 <img src="/asset/window2_1.gif" width="35%" />
</p>




#### Doors and balcony
![image](https://github.com/user-attachments/assets/7f2b39d4-7e4e-4844-a937-5b1a9bfc5239)

The door will automatically change to a double door if its width is larger than some threshold. This threshold can be set manuually. 

<p float="center">
 <img src="/asset/door.gif" width="45%" />
</p>


For balcony, it matches size with the door so it will stretch with door.

The node network for doors and balcony looks like this:
![image](https://github.com/user-attachments/assets/6da7fb41-b9bf-4fe7-aa93-9e7d68528904)


### Rules and logic

<p float="center">
 <img src="/asset/control.gif" width="55%" />
</p>

#### First Floor
Only door and small windows will show up in the first floor. 


#### Roof
Add some distinguish shapes around the roof border. Also randomly add some flagpoles.

![image](https://github.com/user-attachments/assets/5741716f-004c-4d45-81ae-1699484ff51a)


Like how we scatter other assets, assign groups to assets that belongs to the roof and use chain node to scatter the roof assets.

![image](https://github.com/user-attachments/assets/89443050-d5fb-4bc0-9763-07baaeffec7a)


#### Border and Support

Instead of adding both up and down borders for each floor, I only add the upper one because I may later on add the decoration pattern to it so I don't want the upper and bottom border to overlap with each other. The support will appear when the width of the higher floor exceeds the lower floor. User can adjust the border width/height and thickness of the support.

<p float="center">
 <img src="/asset/support.gif" width="55%" />
</p>

#### Pillars
Users can decide whether or not this floor will have pillars. The pillars will not appear on the first floor if we take a close look at the reference image.

<p float="center">
 <img src="/asset/pillar.gif" width="55%" />
</p>

## What's next
There are still many improvements to do for this project, naming a few:
- Use Substance Designer/painter to produce the procedural patterns of decorations on the wall
- UVs
- Better shapes for assets
- ...
