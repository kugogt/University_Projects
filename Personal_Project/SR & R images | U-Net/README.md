# 🧠 Super-Resolution and Image Restoration (Image-to-Image Task) with Advanced U-Net – Flickr2K

Ciao! 👋 Welcome to this personal **Computer Vision** project, which represents an **evolution** of my original university work on image super-resolution.  
While the original project focused on building a baseline pipeline, this upgraded version aims to incorporate state-of-the-art techniques, improve performance and create a more robust and realistic training setup.

The core of this project is a **new U-Net architecture** designed for **2× image super-resolution and restoration**, implemented with several modern deep learning components (before the widespread adoption of Transformer-based approaches).

---

## 📦 Dataset & Degradation Process
The model was trained on the **Flickr2K dataset**.  
Training pairs were generated using a custom degradation pipeline that includes:
- **Downsampling (2×)**
- **Gaussian Blur**
- **Gaussian Noise**
- **JPEG Compression** (NEW!)

---

## ⚙️ Data Pipeline & Augmentation
- Implemented with `tf.data` for efficient loading and batching  
- Data augmentation strategies include:
  - Random crop  
  - Random horizontal & vertical flip (NEW!)
  - Random rotation
  - random brightness (NEW!), contrast (NEW!), saturation (NEW!), hue (NEW!)

---

## 🧩 U-Net Architecture – Upgrades
Compared to the original project, the U-Net was enhanced with multiple improvements:

- **Squeeze-and-Excitation (SE) Blocks**  
- **PixelShuffle** → replacing `Conv2DTranspose`  
- **Global Residual Learning** 
- **Layer Normalization** → replacing BatchNormalization  
- **Dropout** 
- **Mixed Precision Training**

---

## 📉 Loss Functions
- **MAE Loss**  
- **Composite Loss**: MAE + α × Perceptual Loss (with VGG19 features)  
- Normalization of images to `[-1, 1]` and **tanh activation** in the last layer -> preparing the ground for GAN-based losses (NEW!) 

---

## 🔬 Experimentation & Results
- **Full Image Inference** is now supported (previous version required tiled inference).  
- Multiple training runs were performed to compare architectures and degradation settings.  

📷 Example result visualization.
<img width="2460" height="515" alt="__results___46_0" src="https://github.com/user-attachments/assets/9ff77859-80d9-4916-aabb-7601000386c1" />
<img width="2489" height="383" alt="__results___50_1" src="https://github.com/user-attachments/assets/518dd32d-a799-4e0e-a930-77a376f76af0" />

📊 Final Evaluation Results

| Model                                | Test Loss / Combined | Perceptual Loss | MAE    | PSNR   | SSIM  |
|--------------------------------------|----------------------|-----------------|--------|--------|-------|
| **U-Net + MAE**                      | **0.0969**           | –               | 0.0969 | 24.14  | 0.608 |
| **U-Net + Perceptual Loss (α=0.005)** | 0.0995               | 0.9851          | 0.0936 | 24.38  | 0.618 |
| **U-Net + Perceptual Loss (α=0.02)**  | 0.1195               | 0.9856          | 0.0993 | 23.84  | 0.580 |


---

## 🚀 Next Steps: Preparing for GAN
This upgraded architecture was designed with future experiments in mind.  
The use of **tanh** activation and normalized data makes it compatible with **GAN-based training**.  
The next step will be adding **adversarial and perceptual loss** to further improve visual realism.  
👉 Stay tuned!  
