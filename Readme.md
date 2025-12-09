
# 🖼️ ZimageGen App - ComfyUI Workflows

This repository contains the ComfyUI workflows used to power the image generation features of the **ZimageGen** application. These workflows have been optimized for quick and high-quality image synthesis across various Stable Diffusion models.

The workflows are provided as `.json` files and can be easily loaded into **ComfyUI**.

## 🚀 Hardware & Testing

All included workflows were successfully tested on the following hardware:

* **GPU:** NVIDIA RTX 4080
* **VRAM:** 16 GB

## 📂 Available Workflows

Below are the details for each of the ComfyUI workflows included, specifying the model and key parameters.

### 1. JuggernautXL

This workflow utilizes the popular JuggernautXL model, known for its high-quality, realistic, and artistic generations.

* **File:** `JuggernautXL.json`
* **Checkpoint:** `juggernautXL_ragnarokBy.safetensors`
* **Sampler:** `dpmpp_2m`
* **Scheduler:** `karras`
* **Steps:** 28
* **CFG:** 4

### 2. SDXL Turbo Quick

This highly-optimized workflow uses the SDXL Turbo model for extremely fast image generation, leveraging a low number of sampling steps.

* **File:** `SDXLturbo_Quick2.json`
* **Checkpoint:** `sd_xl_turbo_1.0_fp16.safetensors`
* **Sampler:** `euler_ancestral`
* **Scheduler:** `normal`
* **Steps:** 4
* **CFG:** 1.1

### 3. Flux Schnell (Quick)

The Flux Schnell workflow uses a distilled model designed for rapid, high-fidelity results with minimal steps.

* **File:** `flux_quick.json`
* **Checkpoint:** `flux1-schnell-fp8.safetensors`
* **Sampler:** `euler`
* **Scheduler:** `simple`
* **Steps:** 4
* **CFG:** 1 (Note: The `flux1-schnell` model is optimized for CFG=1.0, and the negative prompt will be ignored at this setting).

### 4. Qwen Image Rapid

This workflow is based on the Qwen Image Edit Plus model and is structured for efficient generation.

* **File:** `Qwen Image Rapid.json`
* **Checkpoint:** `Qwen-Rapid-AIO-SFW-v8.safetensors`
* **Sampler:** `sa_solver`
* **Scheduler:** `beta`
* **Steps:** 4
* **CFG:** 1

### 5. Z-Image-Turbo

This workflow leverages the Z-Image-Turbo model architecture for rapid text-to-image synthesis.

* **File:** `image_z_image_turbo_t1.json` (Includes an embedded subgraph: **Z-Image-Turbo Text to Image**)
* **UNET Model:** `z_image_turbo_bf16.safetensors`
* **CLIP Model:** `qwen_3_4b.safetensors`
* **VAE Model:** `ae.safetensors`
* **Sampler:** `res_multistep`
* **Scheduler:** `simple`
* **Steps:** 4
* **CFG:** 1

---

## 🛠️ Usage

To use these workflows:

1.  **Download ComfyUI** and ensure it's set up correctly.
2.  **Download the necessary model checkpoints** (the workflow JSONs assume the models are in your standard `ComfyUI/models/checkpoints/` or other relevant model directories like `text_encoders` and `vae`).
3.  **Open ComfyUI** in your browser.
4.  **Drag and drop** the desired `.json` file (`JuggernautXL.json`, `SDXLturbo_Quick2.json`, etc.) directly onto the ComfyUI canvas.
5.  **Press "Queue Prompt"** to generate the image.

