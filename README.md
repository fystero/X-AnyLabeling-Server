# X-AnyLabeling-Server for any inference image size of sam3 model

为segment_anything_3 和segment_anything_3_video提供任意推理尺寸的的支持

## 原理

在模型加载预训练权重时，屏蔽掉register_buffer中与freqs_cis有关的参数，让模型初始化过程中自动计算该参数，生成适应新尺寸的图片位置编码，新尺寸下模型也能够正常工作

## 效果

原模型只支持设置推理分辨率为1008x1008，不具有适应各种任务的灵活性。如标注小目标任务时，用户往往希望增大推理尺寸，增加模型的准确率。另一方面，小的推理尺寸可以节约显存，提升推理速度，让模型运行在更多设备上。

·700x700尺寸下的效果

<img title="" src="https://github.com/fystero/X-AnyLabeling-Server/blob/main/assets/ScreenShot_2026-03-17_141431_836.png?raw=true" alt="" width="503">
