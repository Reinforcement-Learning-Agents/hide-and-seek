## Exported Models (ONNX)
The trained policies are stored in:

- `Assets/NNModels/`

### Models included
- **POCA model (Hide-and-Seek):** `HideAndSeekAgent-1857600.onnx`
- **PPO baseline model:** `PPO_HideAndSeekAgent-699900.onnx`


## Reproduce Training (Windows)
```powershell
mlagents-learn ml-agents_config.yaml --env Builds\Training\unity-ml-agents_hide-and-seek.exe --run-id hns_run1 --force --no-graphics --time-scale 20



# Hide-and-Seek Agent Training (Unity ML-Agents)

This repository contains a Unity ML-Agents Hide-and-Seek environment and training workflow used for an Applied Reinforcement Learning software project.

## Requirements
- Unity 2022.3 LTS (tested on 2022.3.62f3)
- Python 3.8.x (Conda recommended)
- ML-Agents Python package: 0.30.0
- PyTorch 1.7.1

## Project Structure
- Assets/ Unity assets and scenes
- Builds/Training/ *(ignored in git)* built executable used for training
- 
esults/ *(ignored in git)* ML-Agents logs and checkpoints
- ml-agents_config.yaml Trainer configuration
- Assets/NNModels/ Exported ONNX models

## Training (Windows)
1. Build the training executable from Unity:
   - Open Assets/Scenes/Training
   - File → Build Settings → Build → output to Builds/Training/

2. Run training:
\\\powershell
mlagents-learn ml-agents_config.yaml --env Builds\Training\unity-ml-agents_hide-and-seek.exe --run-id hns_run1 --force --no-graphics --time-scale 20
\\\

## TensorBoard
\\\powershell
tensorboard --logdir results
\\\
Open: http://localhost:6006

## Inference (Test Scene)
- Open Assets/Scenes/Test
- Set Behavior Type = Inference Only
- Assign ONNX model from Assets/NNModels/
- Press Play

## Report
The full training report is provided as a Word document in this repository.
