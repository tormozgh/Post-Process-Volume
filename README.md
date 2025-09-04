![Cover](Images/Cover.jpg)

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
##

2. **What’s Inside The release package**  

  - **PostProcessVolume_Sample_Project** (`.toe`)  
  - **PostProcessVolume** (`.tox`)  
##

3. **Explore the Sample Project**  

- Simply open the `.toe` file to see the component in action. It provides a ready-made example so you can quickly understand how everything works.  
##

4. **Add the Component to Your Own Project**  

  - Drop the `.tox` file into your TouchDesigner project.  
##

5. **Input Tab**

   Go to the first tab of the component parameters, called **Input**. Here you’ll configure the initial setup for your 3D environment. This step essentially connects your 3D scene to the component.  

<p align="center">
  <img src="Images/Input.png" alt="ّInput" />
</p>

   - **GEO for World Position**:  
     The component relies heavily on *World Position* data. You must assign your scene’s main geometry here.  
     - If your geometry has an input, connect that input to the component’s SOP input as well.  
     - If your geometry is self-contained (no inputs), you don’t need to connect anything.  
   - **Replicate**:  
     A button to re-replicate the World Position setup if needed.  

  **Render TOP Setup**  
     In this section you’ll configure the rendering pipeline for your 3D scene:  
   - **Res**:
     Overall resolution of the component (this will be the resolution of your 3D environment).  
   - **Geometry**:
      The main geometry of your scene.  
   - **Camera**:
      The primary camera for your scene.  
     > ⚠️ Make sure your camera component is named **`cam1`**. 
 
   - **Light**:
      The main light source for your 3D scene.
##

6. **Volume Tab**  
   In this tab you define the 3D region where your effect will be applied. this is your *volume*.  
   You can either use the built-in default shapes or bring in your own custom geometry.

<p align="center">
  <img src="Images/Input.png" alt="ّInput" />
</p>


   - **Unbound**:  
     Apply the effect to the entire 3D environment.  
   - **Custom SOP**:  
     Assign your own SOP as the volume for the component.  
   - **Custom SOP or Basic Shapes**:  
     Switch between using a default primitive shape or your custom SOP.  
   - **Shapes**:  
     Choose one of the default shapes: **Box**, **Sphere**, or **Torus**.  
     > 🔧 Tip: By diving into the Post Process component, you can manually edit these shapes under the *Volume* section.  

   - **T (Translate)**:
     Move the volume.  
   - **R (Rotate)**:
     Rotate the volume.  
   - **S (Scale)**:
     Scale the volume along individual axes.  
   - **Uniform Scale**:
     Scale the volume uniformly on all axes.  
   - **Show Bounding Volume**:
     Display the bounding box of the defined volume.

##

7. **Effects Tab**  
   In this tab you can configure the visual effects applied to your volume.  
   You can either use the built-in **cinematic effects** or assign your own **custom effect**.  
  > ℹ️ Note: Custom effects added to the component are applied in full 3D using **Depth Map** and **World Position** data.  

<p align="center">
  <img src="Images/Input.png" alt="ّInput" />
</p>



   **Basic Cinematic Effects**  
   A collection of pre-defined cinematic effects is included in the component:  
   - Chromatic Aberration  
   - Vignette  
   - Lens Distortion  
   - Sharpen  
   - Blur  
   - Film Grain  

   **Custom Effects**  
   Create your own effect by assigning a custom TOP to the component.  

   - **Custom FX TOP**:  
     Drop your desired TOP here to use it as a custom effect.  
   - **Blend Mode**:  
     Choose from standard blend modes such as *Normal*, *Add*, *Multiply*, *Overlay*, and *Screen*.  
   - **Effect Strength**:  
     Controls the intensity of the custom effect.

   **Composition**  
   Choose whether to use the **default cinematic effects**, **custom effects**, or a **combination of both**.  

   - **Select Effect Mode**:  
     Pick one of the following options:  
     - *Cinematic*: Use the built-in cinematic effects.  
     - *Custom*: Use your custom effect.  
     - *Both*: Combine both cinematic and custom effects.  
   - **Both Blend Mode**:  
     Choose the blend mode applied when **Both** mode is selected.  

   - **Master Strength**:  
     Adjusts the overall strength of all active effects combined.  
##

8. **Lens Flares Tab**  
   In this tab you can configure a custom-designed lens flare effect.

<p align="center">
  <img src="Images/Input.png" alt="ّInput" />
</p>


   > ⚠️ Note: This effect applies to the **entire scene**, not just the defined volume. 
 
   > ℹ️ Unlike a physically accurate lens flare, this implementation uses **bright points in the image** instead of actual light sources. As a result, it may not always produce exact results — but it can create very cool visual effects 😉. Future updates will improve accuracy.  

   **Lens Flares Controls**  
   - **Lens Flares**: Toggle the effect on/off.  
   - **Strength**: Overall intensity of the lens flare.  
   - **Blend Mode**: Choose how the flare blends with the scene.  
   - **Threshold**: Sets the brightness threshold used to detect highlights.  
   - **Blur Size**: Controls the blur of the flare.  
   - **Ghosts**: Number of flare rings.  
   - **Ghost Spacing**: Distance between the flare rings.  
   - **Chromatic Shift**: Shifts RGB channels for a chromatic effect.  
   - **Hue / Sat / Gain**: Adjusts hue, saturation, and gain of the flare.  

   **Bokeh Shape Setup**  
   Configure the shape of the flare’s bokeh highlights.  
   - **Bokeh Shape**: Enable/disable the custom bokeh shape.  
   - **Shape Strength**: Intensity of the bokeh shape.  
   - **Combine with Input**:  
     - *Set Resolution Only*: Display only the custom bokeh shape.  
     - *Composite and Set Resolution*: Combine the custom bokeh with the main bokeh.  
   - **Composite**: Select the blend mode between the main bokeh and custom bokeh.  
   - **Radius**: Controls the radius of the shape.  
   - **Sides**: Number of sides of the shape.  
   - **Border**: Thickness of the shape’s outline.  
   - **Rotate**: Rotates the shape.  
   - **Translate**: Moves the shape position.  
##

9. **Color Correction Tab**  
   The **Color Correction** tab lets you fine-tune the final look of your scene by adjusting basic color parameters.  
   Even with these simple controls, you can significantly improve the overall quality of the output.  

<p align="center">
  <img src="Images/Input.png" alt="ّInput" />
</p>


   > ℹ️ Note: Color correction affects only the defined **volume**, not the entire scene.  

   **Color Correction Controls**  
   - **Temperature**: Adjust the warmth or coolness of the colors.  
   - **Tint Color & Strength**: Choose a tint color and control its intensity.  
   - **Saturation**: Increase or decrease color saturation.  
   - **Contrast**: Control the contrast levels.  
   - **Gamma**: Adjust midtone brightness using gamma correction.  
   - **Gain**: Control the overall brightness/gain of the image.  
