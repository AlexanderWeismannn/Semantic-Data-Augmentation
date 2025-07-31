# Generative Semantic Augmentation with Blender and ComfyUI

Welcome to the project page for my research on depth-aware semantic image augmentation using generative AI. This work combines the power of 3D rendering in Blender with prompt-based synthesis in ComfyUI to generate high-quality training data under low-data conditions.

[📄 **Click here to view the full PDF**](thesis.pdf)

---

## Why?

In computer vision, data scarcity remains a critical bottleneck—especially in domains requiring specialized datasets. This research proposed a pipeline that leverages generative tools to create semantically meaningful images for improved model training. This approach uses depth estimation, 3D modeling, and diffusion-based synthesis for image augmentation.

---

## Full Pipeline Details

<img width="2008" height="626" alt="image" src="https://github.com/user-attachments/assets/543846a3-fefc-4bb8-b579-da2f04386b61" />
An original dataset is captured. Next being sent through the pipeline where depth maps are generated, 3D renders are taken, image prompts are created, and then combined together to generate new semantic images. These images are then added into the dataset and a computer vision model is trained on the "augmented" dataset.


## Blender Integration

We utilize Blender as the core 3D rendering engine for generating synthetic scenes. Key components include:

- **Depth-aware mesh construction** using predicted depth maps.
- **Camera placement and lighting control** for photorealistic rendering.
- **Batch automation** using Blender Python scripts for efficient rendering.

The shader node workflow is provided below:
<img width="1915" height="977" alt="image" src="https://github.com/user-attachments/assets/4706e897-52e7-47dc-8a34-945306002c05" />

This provides fine-grained control over perspective, lighting, and geometry—crucial for producing consistent and high-fidelity training samples.
![apple_DA_animation0001-0210-ezgif com-optimize](https://github.com/user-attachments/assets/a4e2e3c9-4fb1-4758-b31e-8fcf7e063327)

We automate combining the depth maps and source image together to form the new 3D topology using the ["render_automation.py"](render_automation.ipynb) script. 

---

## ComfyUI Pipeline

ComfyUI is used to synthesize photorealistic images from prompts generated based on object labels and scene templates. We utilize the below workflow to generate our images:

<img width="2725" height="1467" alt="image" src="https://github.com/user-attachments/assets/f3e3ae0f-2243-4ba6-aa5f-58457ecec28c" />


And example training script can be viewed in the ["model_training.ipynb"](model_training.ipynb) file.



