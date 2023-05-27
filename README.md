## Blender2Bloodborne

This is a toolset for extracting Bloodborne models. I try to keep pipeline as close to Blender as possible

1. Get Bloodborne PS4 files 🏴‍☠️
2. Downlad [PS4 PKG Tool](https://github.com/pearlxcore/PS4-PKG-Tool/releases/tag/v1.5)
3. Open Bloodborne_Game.pkg with it. PKG Content → View PKG Content → Wait... → right click Image0 → Extract to. (I use'll folder "extracted") The app may seem to stuck. It simply doesn't have loading screen. Wait 10-20 mins
4. Download [BinderTool](https://github.com/Atvaark/BinderTool/releases)
5. Go to extracted/dvdroot_ps4/map. m21, m22, m23 folders are for textures. m21_00_00_00, m22_00_00_00, m23_00_00_00 are for models (I guess). Drag-n-drop any files on BinderTool.exe[^1]
    - *.tpf.dcx will create another *.tpf (texture)
    - *.flver.dcx will create *.flver (model)
    - filename_0.tpfbhd then filename_0.tpfbdt. It will create a folder with lots of *.tpf (textures archive)
6. Use ./utils/BloodborneTools. Tools were originaly attached to [XENHAX](https://zenhax.com/viewtopic.php?f=5&t=7006&sid=8cd60cb622907a6a69e92d882328d4b8) post. Attached via URL to some old cloud storage. So I duplicated them to this repo, just in case[^2]
    - Drag-n-drop *.tpf on Bloodborne_texture.exe. It will create *.dds and *.dx10
    - Drag-n-drop *.flver on BloodBorne_model_v3.exe. It will create *.smd and *.ascii
7. Install [Blender XPSTools](https://github.com/johnzero7/XNALaraMesh/releases/tag/v2.0.2) plugin
8. Blender → File → Import → XNALara / XPS → XNALara/XPS Model (.ascii/.mesh/.xps)

[^1]: I should write a script to recursively unpack all this. It has -r flag. But it fails to work with .tpfbhd .tpfbdt files
[^2]: I should write a script to recursively unpack all this. Also convert all *.dds and *.dx10 to *.png. Rewrite texture paths in all *.ascii

Also worth mentioning. Options I found and tested. May be it will be useful for your pipeline
  - [Yabber](https://www.nexusmods.com/sekiro/mods/42). Can be used as *.dcx packer / unpacker on step 5
  - [FLVER_Editor](https://github.com/asasasasasbc/FLVER_Editor). Works as drag-n-drop *.flver viewer. Can export to *.dae. But messes up verticies positions a bit
  - [Blender Source Tools](http://steamreview.org/BlenderSourceTools/). For opening *.smd files. Not needed in current pipeline
  - [DarkSoulsModelViewerDX](https://github.com/soulsmods/DarkSoulsModelViewerDX). Some 2019 proj C# source code. No builds. [Description](https://www.reddit.com/r/darksouls/comments/ab5a5y/darksoulsmodelviewerdx_a_new_model_and_map_viewer/)
  - [Blender FLVER plugin](https://github.com/elizagamedev/blender-flver). Wasn't working
  - [UXM Selective Unpacker](https://github.com/Nordgaren/UXM-Selective-Unpack) works for all Souls except Bloodborne