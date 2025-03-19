readme_content = """
# ESS Inpainting Dataset

This dataset contains synthetic video frames for Energy Storage Systems (ESS) monitoring, as described in the paper "Low-Latency Progressive GAN Inpainting for Energy Storage Monitoring at 15 ms" by Hamzah Faraj.

## Dataset Structure
- **Total Frames**: 78,000
- **ETI**: 15,000 frames, simulating arid conditions (50°C, 0.1 mm/s dust), with thermal events (1°C per second increase).
- **SPM**: 60,000 frames, simulating offshore conditions (70% humidity, 20% salt spray corruption).
- **TMP**: 3,000 frames, synthetic occlusion (15-50%) with Gaussian noise (σ=0.1) and 5% salt-and-pepper noise.

## Frame Specifications
- **Resolution**: 480p (854x480 pixels)
- **Format**: Grayscale, 8-bit depth, saved as NumPy arrays (.npy files)
- **Frame Rate**: 60 FPS (intended for playback)

## Directory Structure
- `ETI/`: Contains 15,000 frames (`frame_000000.npy` to `frame_014999.npy`)
- `SPM/`: Contains 60,000 frames (`frame_000000.npy` to `frame_059999.npy`)
- `TMP/`: Contains 3,000 frames (`frame_000000.npy` to `frame_002999.npy`)

## Usage
Each `.npy` file is a 480x854 NumPy array representing a single frame. Load with NumPy:
```python
import numpy as np
frame = np.load('ETI/frame_000000.npy')
