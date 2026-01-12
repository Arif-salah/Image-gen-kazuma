# 🎨 Image Gen Kazuma

An advanced, feature-rich **ComfyUI** integration for **SillyTavern**.
This extension replaces the need for the core Stable Diffusion extension if you are a ComfyUI power user.

## ✨ Features

*   **⚡ Smart Integration:** Images appear as native SillyTavern attachments (Gallery view).
*   **🚀 Zero Lag:** Auto-compresses high-res ComfyUI images to optimized JPEGs so your chat history never slows down.
*   **🔁 Swipe-to-Regenerate:** Swipe right on the *last* generated image to instantly create a new variation with the same prompt.
*   **🤖 Auto-Generation:** Automatically visualize the scenario after every AI reply (or every Nth reply).
*   **🛠️ Workflow Manager:**
    *   Import, Create, Edit, and Delete ComfyUI workflows directly inside SillyTavern.
    *   Server-side saving (workflows persist across reloads).
    *   Built-in JSON Editor with syntax highlighting for placeholders.
*   **🎛️ Total Control:**
    *   Support for **4 Simultaneous LoRAs** with individual weight sliders.
    *   Adjust Steps, CFG, Denoise, and Sampler on the fly.
    *   Random or Fixed Seeds.

## 📦 Installation

1.  Open **SillyTavern** -> **Extensions** -> **Install Extension**.
2.  Paste the URL of this repository.
3.  Click **Install**.
4.  Reload SillyTavern.

## ⚙️ ComfyUI Setup

You must start ComfyUI with the `--listen` argument (and optionally `--enable-cors-header` if you run into connection issues).

`run_nvidia_gpu.bat` example:
bat
.\python_embeded\python.exe -s ComfyUI\main.py --windows-standalone-build --listen --enable-cors-header

## 📝 How to Use Workflows

1.  Go to **Extensions** -> **Image Gen Kazuma**.
2.  To use your own workflow:
    *   In ComfyUI, create your workflow.
    *   Enable **Dev Mode Options** in ComfyUI settings.
    *   Click **Save (API Format)**.
    *   In SillyTavern, click **New Workflow** (+) and name it.
    *   Click **Edit** (Pen icon) and paste your JSON.
    *   **IMPORTANT:** Replace specific values with the placeholders below so the extension can control them.

### 🧩 Workflow Placeholders

Use these strings inside your workflow JSON values strings (e.g., `"inputs": { "text": "*input*" }`).

| Placeholder | Description |
| :--- | :--- |
| `"*input*"` | The positive prompt. |
| `"*ninput*"` | The negative prompt. |
| `"*seed*"` | The seed number. |
| `"*model*"` | Selected Checkpoint filename. |
| `"*sampler*"` | Selected Sampler name. |
| `"*steps*"` | Sampling steps (e.g. 20). |
| `"*cfg*"` | CFG Scale value. |
| `"*denoise*"` | Denoising strength (0.0 - 1.0). |
| `"*width*"` | Image width. |
| `"*height*"` | Image height. |
| `"*lora*"` | LoRA 1 filename. |
| `"*lorawt*"` | LoRA 1 weight. |
| `"*lora2*"` | LoRA 2 filename. |
| `"*lorawt2*"` | LoRA 2 weight. |
|  *(...up to lora4)* | |

## 🖼️ Usage Tips

*   **Manual Gen:** Click the **Paintbrush** 🖌️ icon near the chat bar to visualize the last message.
*   **Diagnostic:** Enable "Diagnostic Mode" in settings to see exactly what prompt the LLM is writing before it sends to ComfyUI.
*   **Compression:** Keep "Compress Images" enabled to keep imge size small if you want.

## 📜 License

MIT

