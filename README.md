# Build-LLaMa: Aligning Architects' Feedback and Domain Knowledge in 3DArchitectural Design Generation
Abstract: *IHow can large language models (LLMs) become 3D architects? In the Architecture, Engineering, and Construction (AEC) stages, generating 3D buildings is a complex task that requires both domain expertise and alignment with user requirements. While machine learning has been increasingly applied to 3D building design, current evaluation methods often rely on statistical metrics like CD and F-score, which fail to reflect real-world human preferences and domain-specific knowledge. As a result, models that perform well on these metrics may still fail to generate practical 3D designs, as architects consider factors such as shape, aesthetics, and structural rationality.
To address this:
(1) We propose the \textbf{BuildMetricsNet}, the first 3D building dataset with textual descriptions and evaluation scores of structural feasibility, aesthetic quality, and overall spatial scores, which could be used for further fine-tuning of large language models.
(2) We introduce the \textbf{Build-LLaMa}, a novel framework that pre-trains on generations of text to 3D building mesh, and conducts further fine-tuning with architects' feedback and domain knowledge. 
(3) We comprehensively evaluate the 3D generation potential of various large language models and carefully assess RLHF effectiveness through architects' validation, providing a new benchmark for 3D generation capacity of large models and offering insights for the architectural community. The code, dataset, and model weights will be released upon acceptance.*


[**Paper**]() | [**Project Page**]() | [**Model Weights**]() | [**Huggingface Demo**]() |


*Figure 1) Graphic Abstract of Segement Any Architecture Facade (SAAF).*
![img](assets/01.png)

*Figure 2) Schematic diagram of the reference segmentation dataset.*
![img](assets/05.png)

*Figure 3) The pipeline of SAAF. Given the input image and text query, the multimodal LLM (e.g, LLaVA ) generates text output. The last-layer embedding for the <SEG> token is then decoded into the segmentation mask via the decoder..*
![img](assets/06.png)

*Figure 4) Segmentation results of SAAF on different datasets.*
![img](assets/02.png)

*Figure 5) SAAF performs wall and window segmentation based on semantic guidance.*
![img](assets/03.png)



## Dataset

*Realistic Image_completed.*
![img](sample/001.jpg)

*Realistic Image_partial.*
![img](sample/002.jpg)

*Perspective Image.*
![img](sample/003.jpg)

*Render Image.*
![img](sample/004.jpg)

*CAD Image.*
![img](sample/005.jpg)

*Pen drawing Image.*
![img](sample/006.jpg)

*Illustration Image.*
![img](sample/007.jpg)

*Watercolor Image.*
![img](sample/008.jpg)

*Book Image.*
![img](sample/009.jpg)

*Digital Model Image.*
![img](sample/010.jpg)

*Historical Document Image.*
![img](sample/011.jpg)

## TODO List

- [x] Release part of Segment-Any-Architecture-Facade dataset. 
- [ ] Release Segment-Any-Architecture-Facade inference code and pretrain weights.
- [ ] Upload Segment-Any-Architecture-Facade training dataset.
- [ ] Release Segment-Any-Architecture-Facade code.



## Inference

```
python Segment_Any_Architecture_Facade_Sample.py --dataset ArchiMetricsNet --batch_size 32  --color_configuration 0 --model_path ckpts/exp/model10000.pt --num_samples 64
```
## Train

```
python Segment_Any_Architecture_Facade_Train.py --dataset ArchiMetricsNet --batch_size 32  --color_configuration 0 
