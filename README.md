# Segment-Any-Architecture-Facade
Abstract: *In the context of the digital development of architecture, the automatic segmentation of walls and windows is a key step in improving the efficiency of building information models and computer-aided design. This study proposes an automatic segmentation model for building facade walls and windows based on multimodal semantic guidance, called Segment Any Architectural Facades (SAAF). First, SAAF has a multimodal semantic collaborative feature extraction mechanism. By combining natural language processing technology, it can fuse the semantic information in text descriptions with image features, enhancing the semantic understanding of building facade components. Second, we developed an end-to-end training framework that enables the model to autonomously learn the mapping relationship from text descriptions to image segmentation, reducing the influence of manual intervention on the segmentation results and improving the automation and robustness of the model. Finally, we conducted extensive experiments on multiple facade datasets. The segmentation results of SAAF outperformed existing methods in the mIoU metric, indicating that the SAAF model can maintain high-precision segmentation ability when faced with diverse datasets. Our model has made certain progress in improving the accuracy and generalization ability of the wall and window segmentation task. It is expected to provide a reference for the development of architectural computer vision technology and also explore new ideas and technical paths for the application of multimodal learning in the architectural field.*


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
