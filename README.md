## Blender2Bloodborne

This is a toolset for extracting Bloodborne models. I try to keep pipeline as close to Blender as possible

1. Get Bloodborne PS4 files 🏴‍☠️
2. Downlad [PS4 PKG Tool](https://github.com/pearlxcore/PS4-PKG-Tool/releases/tag/v1.5)
3. Open Bloodborne_Game.pkg with it. PKG Content → View PKG Content → Wait... → right click Image0 → Extract to. (I use'll folder "extracted") The app may seem to stuck. It simply doesn't have loading screen. Wait 10-20 mins
4. Download [BinderTool](https://github.com/Atvaark/BinderTool/releases)
5. Go to extracted/dvdroot_ps4/map. Drag-n-drop any *.dcx file on BinderTool.exe
  - *.tpf.dcx will create another *.tpf.dcx
  - *.flver.dcx will create *.flver
6. Use ./utils/BloodborneTools. It was originaly hosted on [XENHAX](https://zenhax.com/viewtopic.php?f=5&t=7006&sid=8cd60cb622907a6a69e92d882328d4b8). But mediafire may remove it in the future, so here's a duplicate
  - Drag-n-drop *.flver on BloodBorne_model_v3.exe. It will create *.smd and *.ascii
  - Drag-n-drop *.tpf.dcx on Bloodborne_texture.exe. It will create *.dds and *.dx10
7. Install [Blender XPSTools](https://github.com/johnzero7/XNALaraMesh/releases/tag/v2.0.2) plugin
8. Blender → File → Import → XNALara / XPS → XNALara/XPS Model (.ascii/.mesh/.xps)