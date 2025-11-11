# Unity SCORM 1.2 Integration Exporter Toolkit

A fully functional **Unity → SCORM 1.2 integration** for WebGL builds.  
This toolkit enables seamless communication between your Unity project and Learning Management Systems (LMS) such as **Moodle**, **SCORM Cloud**, or **TalentLMS**.

---

## 🎮 Live WebGL Demo

You can try a live SCORM-enabled demo hosted on SCORM Cloud here:  
👉 [**Launch WebGL Demo (SCORM Cloud)**](https://app.cloud.scorm.com/sc/InvitationConfirmEmail?publicInvitationId=8dcc9e8d-e382-40c2-98b1-603cf759be1b)

This demo showcases SCORM data communication and completion tracking built using this toolkit.

---

## 📦 Download Unity Package

You can directly import the package into your Unity project:

[![Download Unity Package](https://img.shields.io/badge/Download-.unitypackage-blue?style=for-the-badge&logo=unity)](https://github.com/iamraziq/Unity-SCORM1.2-Integration-Exporter/releases/download/v1.0/unity-scorm12-integration-exporter-kit-raaz-v1.unitypackage)

Once downloaded, drag the `.unitypackage` file into your Unity Editor to import all required assets.

---

## 🚀 Features

- **SCORM 1.2 Compliant:** Tested with standard LMS platforms.  
- **Unity → JavaScript Bridge:** Communicates progress, scores, and completion via `SCORMWrapper.js`.  
- **Automatic Packaging:** Exports a ready-to-upload `.zip` SCORM package.  
- **Manifest Generator:** Dynamically creates `imsmanifest.xml` for LMS compatibility.  
- **Custom Editor Tools:** Includes `ScormExporterAdvanced` for automated build and export.  
- **WebGL-Ready Template:** Ships with preconfigured `index_scorm.html` and `SCORMWrapper.js`.

---

## 🧩 Project Structure

- **Assets/**
  - **Raaz SCORM Integration/**
    - **Editor/**
      - `ScormExporterAdvanced.cs`
    - **Prefabs/**
      - `SCORMManager.prefab`
      - `SCORMProgressHandler.prefab`
    - **Scenes/**
      - `Demo.unity`
    - **Scripts/**
      - `SCORMManager.cs`
      - `SCORMProgressHandler.cs`
  - **WebGLTemplates/**
    - **SCORMTemplate/**
      - `index_scorm.html`
      - `SCORMWrapper.js`

---

## ⚙️ Setup Instructions

Follow these simple steps to integrate and use the SCORM toolkit in your Unity project:

1. **Add the SCORMManager Prefab**
   - Drag and drop the **`SCORMManager` prefab** into your scene.
   - **Important:** The GameObject **must be named exactly `SCORMManager`**.
   - Ensure it has the **`SCORMManager.cs`** component attached.
   - This naming is mandatory because the system currently finds the manager via its GameObject name to update SCORM data.  
     (No `.jslib` plugin is used due to cross-domain functionality in this version.)

2. **Use SCORMProgressHandler for Scene Progress**
   - Attach **`SCORMProgressHandler.cs`** to any object in the scene where you want to report learner progress.
   - This can be used to track completion of specific sections or levels.

3. **Reporting Progress**
   - The `SCORMManager` class contains a helper function:
     ```csharp
     public void ReportLevelProgress(int levelsCompleted)
     ```
   - This was originally built for a project with **two levels hardcoded** in this function,  
     but you can modify it to suit your own scene or module structure.

---

## 🛠️ Build Instructions

### 1. Configure SCORM Template

In Unity:
- Go to **Build Settings > Player Settings > Resolution and Presentation**
- Under **WebGL Template**, select **SCORM Template**  
  (This includes `SCORMWrapper.js` and `index_scorm.html`.)

### 2. Export SCORM Package

In Unity, open:
Tools > SCORM Packaging > Export SCORM Package

Then configure:
- **Identifier:** `Ex:UnitySCORMTest`  
- **Title:** `Ex:Unity WebGL SCORM Test`  
- **Index SCORM File:** `index_scorm.html`  **DON'T CHANGE THIS. This should be as per the scorm index in SCORM Template**
- **JS Wrapper File:** `SCORMWrapper.js`   **DON'T CHANGE THIS. This should be as per the JS script name**
- **Open folder after export:** optional

Click **Build and Export SCORM Package** — this will:
- Build your WebGL project  
- Generate `imsmanifest.xml`  
- Package everything into a SCORM-compliant `.zip` file ready for LMS upload

---

## 📦 SCORM Components Overview

| File | Description |
|------|--------------|
| **SCORMManager.cs** | Handles all SCORM API calls and communication between Unity and LMS. |
| **SCORMWrapper.js** | JavaScript bridge for WebGL to interact with LMS SCORM API. |
| **SCORMProgressHandler.cs** | Manages progress tracking, score updates, and completion percentage. |
| **imsmanifest.xml** | Defines SCORM metadata, organization, and launch file references. |
| **index_scorm.html** | WebGL entry HTML page loading Unity build with SCORM wrapper scripts. |

---

## 🧠 Notes

- The GameObject that contains `SCORMManager.cs` **must be named exactly `SCORMManager`**.  
  The system currently relies on this name for communication between Unity and JavaScript.  
  (Cross-domain communication is handled without a `.jslib` plugin.)
- **ScormExporterAdvanced** automates the full SCORM packaging workflow.
- Compatible with **Unity 2021+** and tested on **SCORM Cloud**.
- Ideal for **WebGL training simulations** or **e-learning modules**.

---

## 📚 License

**MIT License** — feel free to use, modify, and extend this toolkit for your projects.

---

## 🧩 Credits

Developed by **Raziq Ahmed Shariff**  
Senior Game Developer | VR/AR/MR Specialist  

📧 **Email:** [raziqshariff18@gmail.com](mailto:raziqshariff18@gmail.com)  
🌐 **Portfolio:** [raziqshariff18.wixsite.com/portfolio](https://raziqshariff18.wixsite.com/portfolio)  
🔗 **LinkedIn:** [linkedin.com/in/raziq-ahmed-shariff-1231a6127](https://www.linkedin.com/in/raziq-ahmed-shariff-1231a6127?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BPQX0ci3XTtKfGJUEKYQxYA%3D%3D)

---
