# Pear Media AI Prototype

A responsive AI-powered web application built as part of the **Pear Media Assignment**.  
This prototype demonstrates **multi-API integration** for both **text-based prompt enhancement** and **image-based analysis/variation generation** workflows.

---

## 📌 Assignment Objective

The objective of this project is to design and implement a **webpage-based AI product prototype** that:

- Accepts **text prompts** and enhances them using an NLP model.
- Generates AI images from the **approved enhanced prompt**.
- Accepts **image uploads** from the user.
- Analyzes the uploaded image using a **vision-capable AI model**.
- Generates **new image variations** based on the analyzed image style, subject, and mood.

This prototype was designed to satisfy the assignment requirements within a **6-hour development window**.

---

# ✨ Features

## 1) Text Workflow — Prompt Enhancement to Image Generation
- User enters a simple text prompt.
- The application analyzes the prompt using an **NLP API**.
- The prompt is enhanced into a **more detailed and image-generation-friendly version**.
- The enhanced prompt is displayed in an **editable approval box**.
- After approval, the enhanced prompt is sent to an **image generation API**.
- The final AI-generated image is displayed in the results section.

### Example Flow
"A futuristic cat"  
⬇  
Enhanced Prompt  
⬇  
Approved Prompt  
⬇  
AI Generated Image

---

## 2) Image Workflow — Image Analysis to Variation Generation
- User uploads an image from local storage.
- The application converts the image into **Base64 format** for API transmission.
- A **vision model** analyzes the uploaded image and extracts:
  - Main subject
  - Key objects
  - Mood / atmosphere
  - Color palette
  - Artistic style
- The system automatically generates a **variation prompt** based on the analysis.
- This variation prompt is then used to generate a **new AI image variation**.

### Example Flow
Uploaded Image  
⬇  
Image Analysis  
⬇  
Generated Variation Prompt  
⬇  
AI Variation Image

---

# 🧠 APIs Used

This project integrates **multiple APIs** to demonstrate the required AI workflow.

## 1) Gemini API (Google AI Studio)
Used for:
- **Text enhancement**
- **Prompt engineering**
- **Image analysis**
- **Visual understanding**

### Why Gemini?
Gemini was selected because it supports:
- Fast text generation
- Structured prompt improvement
- Multimodal image understanding
- Good free-tier support for prototypes

---

## 2) OpenAI Image Generation API *(or replace with Stability/Hugging Face if used)*
Used for:
- **Text-to-image generation**
- **Variation image generation**

### Why OpenAI Images?
OpenAI image generation was chosen because it:
- Produces high-quality results
- Is easy to integrate with REST APIs
- Works well with descriptive prompts enhanced by Gemini

---

# 🏗️ Tech Stack

## Frontend
- **React (Vite)**
- **JavaScript**
- **CSS3**
- **Fetch API**

## Backend
- **Node.js**
- **Express.js**
- **dotenv**
- **cors**
- **multer** *(if image handling middleware is used)*

## Hosting / Deployment
- **Vercel** → Frontend deployment
- **Render** → Backend deployment

## Development Tools
- **VS Code**
- **Git**
- **GitHub**
- **Postman** *(optional for testing APIs)*

---

# 🖼️ UI Overview

The application uses a simple **tab-based UI** for a clear user experience.

## Tab 1 — Creative Studio (Text Workflow)
Contains:
- Prompt input box
- Enhance Prompt button
- Editable enhanced prompt box
- Generate Image button
- Final generated image display

## Tab 2 — Style Lab (Image Workflow)
Contains:
- Image upload input
- Uploaded image preview
- Analyze Image button
- Image analysis result box
- Generate Variation button
- Final variation image display

---

# 🔁 Complete Application Workflow


## Workflow A — Text Input → Enhanced Prompt → Image

### Step 1: User Prompt Input
The user enters a simple creative idea such as:

> “A cyberpunk tiger in neon rain”

### Step 2: Prompt Enhancement
The prompt is sent to the **Gemini API**, which transforms it into a more descriptive and optimized image prompt by adding:
- Camera angle
- Lighting
- Mood
- Art style
- Scene composition
- Visual detail

### Step 3: User Approval
The enhanced prompt is displayed in an **editable textarea** so the user can:
- Approve as-is
- Edit manually
- Fine-tune before generation

### Step 4: Image Generation
The approved prompt is sent to the **Image Generation API**, which returns an AI-generated image.

### Step 5: Result Display
The final image is shown inside the application UI.

---

## Workflow B — Image Upload → Analysis → Variation

### Step 1: Upload Image
The user uploads a local image.

### Step 2: Convert to Base64
The frontend converts the uploaded file into **Base64 format** using the browser `FileReader` API.

### Step 3: Visual Analysis
The image is sent to the **Gemini Vision API**, which analyzes the image and identifies:
- Main subject
- Objects present
- Visual theme
- Color palette
- Style / artistic impression
- Mood / tone

### Step 4: Variation Prompt Generation
The AI analysis is used to generate a new prompt for creating a similar but creatively altered image.

### Step 5: Variation Image Generation
The variation prompt is sent to the **Image Generation API** to create a new AI-generated image.

### Step 6: Result Display
The new variation image is shown in the UI.

---

# 📁 Project Structure

bash
pearmedia-ai-prototype/
├── server/
│   ├── index.js
│   └── .env
│
├── src/
│   ├── components/
│   │   ├── TextWorkflow.jsx
│   │   ├── ImageWorkflow.jsx
│   │   ├── Navbar.jsx
│   │   └── ResultCard.jsx
│   │
│   ├── App.jsx
│   ├── App.css
│   └── main.jsx
│
├── public/
├── .env
├── .gitignore
├── package.json
├── vite.config.js
└── README.md
