# T2.2 Fine-tuning and hyper-parameter comparison

Fine-tunes `yolo11n.pt` on the training set and compares four configurations on the validation set by mAP50-95. The first uses the provided settings (20 epochs, batch 16, lr0 = 0.001, freeze = 10). The best configuration is then evaluated on the test set. Part of [2D Object Detector](https://github.com/2DObjectDetector).

**Result:** The best configuration was 40 epochs (lr0 = 0.001, freeze = 10).

| Configuration | Validation mAP50-95 |
| --- | --- |
| 1. Baseline (20 epochs, freeze 10) | 0.443 |
| 2. More epochs (40, freeze 10) | **0.482** |
| 3. Less freezing (20 epochs, freeze 5) | 0.421 |
| 4. Combined (40 epochs, freeze 5) | 0.479 |

On the test set, the best configuration scored mAP50 0.720 and mAP50-95 0.454. Training was not fully deterministic (`cache="ram"`), so small variations between runs are expected.

**Run:** Outputs are saved in the notebook, so the results are visible without running it. To rerun: use a Colab GPU runtime and add the `kitti3k_yolo` dataset (not included) and update its path.
