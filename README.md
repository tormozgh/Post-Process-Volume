![Cover](Cover.jpg)

# 🎨 Post Process Volume for TouchDesigner

A custom tool for [TouchDesigner](https://derivative.ca) that lets you apply effects to a specific region of your 3D environment.

These effects can be either the built-in cinematic presets included in the component, or custom effects you provide as an input.

The component is inspired by [Unreal Engine](https://www.unrealengine.com/en-US)’s Post Process Volume, bringing a similar workflow into Touchdesigner.✨  

- Developed by [TORMOZGH](www.instagram.com/tormozgh)

- Version: 0.64 Beta (Released on Sep 2025)



---

## 🚀 How to Use

1. **Download the Component**  
   Get the latest release from the [Releases](../../releases) section.  
   > ⚠️ Note: This component is currently in **Beta** and works with **TouchDesigner 2022.24200 or newer**.  
   Older versions are not recommended (untested). If you manage to run it successfully on earlier builds, please let me know! 🙏  

2. **What’s Inside**  
   The release package includes two files:  
   - A **sample project** (`.toe`)  
   - The actual **component** (`.tox`)  

3. **Explore the Sample Project**  
   Simply open the `.toe` file to see the component in action.  
   It provides a ready-made example so you can quickly understand how everything works.  

---

4. **Add the Component to Your Own Project**  
   - Drop the `.tox` file into your TouchDesigner project.  
   - Go to the first tab of the component parameters, called **Input**. Here you’ll configure the initial setup for your 3D environment.  
   - This step essentially connects your 3D scene to the component.  

   **Key Parameters in the Input Tab**  
   - **GEO for World Position**:  
     The component relies heavily on *World Position* data. You must assign your scene’s main geometry here.  
     - If your geometry has an input, connect that input to the component’s SOP input as well.  
     - If your geometry is self-contained (no inputs), you don’t need to connect anything.  
   - **Replicate**:  
     A button to re-replicate the World Position setup if needed.  

---

5. **Render TOP Setup**  
   In this section you’ll configure the rendering pipeline for your 3D scene:  
   - **Res**: Overall resolution of the component (this will be the resolution of your 3D environment).  
   - **Geometry**: The main geometry of your scene.  
   - **Camera**: The primary camera for your scene.  
     > ⚠️ Make sure your camera component is named **`cam1`**.  
   - **Light**: The main light source for your 3D scene.  
