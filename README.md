# Resources for Illumination estimation
**This is a resource list for illumination estimation, including datasets, methods/codes/papers, metrics, blogs and so on.**

**Maintained by:** [Huang Renjing](https://github.com/rjhuang27)

Looking forward to your sharing! You can come up with your ideas and suggestions in the [issue](https://github.com/rjhuang27/Illumination_Estimation/issues)




## Introduction

Lighting estimation aims to recover illumination from a single image with limited field of view. It has a wide range ofapplications in various computer vision and computer graphics tasks such as high-dynamic-range (HDR) relighting in mixed reality, etc..

## Methods

### Learning-based methods

* **EMLight** [[Pdf]](https://arxiv.org/pdf/2012.11116.pdf)[[code]](https://github.com/fnzhan/Illumination-Estimation)
  * Zhan F, Zhang C, Yu Y, et al. EMLight: Lighting Estimation via Spherical Distribution Approximation[J]. arXiv preprint arXiv:2012.11116,2020. 
* **2020** [[pdf]](https://arxiv.org/pdf/2005.08000.pdf)[[code]](https://github.com/VCL3D/DeepPanoramaLighting)
  * V. Gkitsas, N. Zioulis, F. Alvarez, D. Zarpalas and P. Daras,  "Deep Lighting Environment Map Estimation from Spherical Panoramas," in2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW), Seattle, WA, USA, 2020 pp. 2719-2728.
* **2019** [[pdf]](https://arxiv.org/pdf/1811.12481v2.pdf)
  * Z. Hui, A. Chakrabarti, K. Sunkavalli and A. Sankaranarayanan,  "Learning to Separate Multiple Illuminants in a Single Image," in 2019 *IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), Long Beach, CA, USA, 2019 pp. 3775-3784.
  * (note:是将一张图像分成照明程度不同的两张图像)
* **2019** [[pdf]](https://arxiv.org/pdf/1905.00824v1.pdf)
  * Sun T, Barron J T, Tsai Y T, et al. Single image portrait relighting[J]. ACM Trans. Graph., 2019, 38(4): 79:1-79:12.
* **DPR** [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Zhou_Deep_Single-Image_Portrait_Relighting_ICCV_2019_paper.pdf)[code](https://github.com/zhhoper/DPR)
  * H. Zhou, S. Hadap, K. Sunkavalli and D. Jacobs,  "Deep Single-Image Portrait Relighting," in 2019 IEEE/CVF International Conference on Computer Vision (ICCV), Seoul, Korea (South), 2019 pp. 7193-7201.
  * （note:预测场景光照图，实现人像冲照明，在输入图像包含硬阴影、镜面反射或饱和像素时，预测结果有误差)
* **DPR** [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Zhou_Deep_Single-Image_Portrait_Relighting_ICCV_2019_paper.pdf)[code](https://github.com/zhhoper/DPR)
  * H. Zhou, S. Hadap, K. Sunkavalli and D. Jacobs,  "Deep Single-Image Portrait Relighting," in 2019 IEEE/CVF International Conference on Computer Vision (ICCV), Seoul, Korea (South), 2019 pp. 7193-7201.
  * （note：只有测试代码，无训练）
* **2019** [[pdf]](https://arxiv.org/pdf/1901.02453v3.pdf)
  * Sengupta S, Gu J, Kim K, et al. Neural inverse rendering of an indoor scene from a single image[C]//Proceedings of the IEEE International Conference on Computer Vision. 2019: 8598-8607.
  * (note：预测光照图、法线图、反射率图)
* **2019** [[pdf]](https://arxiv.org/pdf/1903.07145v1.pdf)
  * Azinovic D, Li T M, Kaplanyan A, et al. Inverse path tracing for joint material and lighting estimation[C]//Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019:2447-2456.
  * (note:求解场景的光照信息和BRDF参数，但当场景无发光器时，会出现错误的预测结果)
* **InverseRenderNet** [[pdf]](https://arxiv.org/pdf/1811.12328v1.pdf)[[code]](https://github.com/YeeU/InverseRenderNet)
  * Yu Y, Smith W A P. InverseRenderNet: Learning single image inverse rendering[C]//Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2019: 3155-3164.
  * (note:利用9个参数的球谐函数表示光照信息，光照效果欠佳)
* **2021** [[pdf]](https://arxiv.org/pdf/2102.06591v1.pdf)
  * Yu Y, Smith W. Outdoor inverse rendering from a single image using multiview self-supervision[J]. IEEE Transactions on Pattern Analysis & Machine Intelligence, 2021 (01): 1-1.
* **GLoSH** [[pdf]](https://openaccess.thecvf.com/content_ICCV_2019/papers/Zhou_GLoSH_Global-Local_Spherical_Harmonics_for_Intrinsic_Image_Decomposition_ICCV_2019_paper.pdf)
  * Zhou H, Yu X, Jacobs D W. GLoSH: Global-Local Spherical Harmonics for Intrinsic Image Decomposition[C]//Proceedings of the IEEE International Conference on Computer Vision. 2019: 7820-7829.
  * (note:恢复全局光照信息和局部光照信息，但是包含大量的参数)
* **NIID-Net** [[pdf]](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9199573&casa_token=zYE2CqXkCSIAAAAA:kW7c8OsKXQfIv3-ogk7rxTPcesapQL4-on7AuGFiwlC8I37fkyxG_VDcxSzYsiXRdPNnKJ9F8_jZ)[[code]](https://github.com/zju3dv/NIID-Net)
  * Luo J, Huang Z, Li Y, et al. NIID-Net: Adapting Surface Normal Knowledge for Intrinsic Image Decomposition in Indoor Scenes[J]. IEEE Transactions on Visualization and Computer Graphics, 2020, 26(12): 3434-3445.
  * (note:预测光照矢量图和本征图像)
* **2020** [[pdf]](https://arxiv.org/pdf/1905.02722v1.pdf)[[code]](https://cseweb.ucsd.edu//~viscomp/projects/CVPR20InverseIndoor/)
  * Li Z, Shafiei M, Ramamoorthi R, et al. Inverse rendering for complex indoor scenes: Shape, spatially-varying lighting and svbrdf from a single image[C]//Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. 2020: 2475-2484.
  * (note:预测出双向反射分布函数和光照信息)
* **2020** [[pdf]](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9090568)
  * D. Xu, Z. Li and Y. Zhang,  "Real-time Illumination Estimation for Mixed Reality on Mobile Devices," in 2020 IEEE Conference on Virtual Reality and 3D User Interfaces Abstracts and Workshops (VRW), Atlanta, GA, USA, 2020 pp. 702-703.
* **Lighthouse** [[pdf]](https://arxiv.org/pdf/2003.08367v2.pdf)[[code]](https://github.com/pratulsrinivasan/lighthouse)
  * P. Srinivasan, et al., "Lighthouse: Predicting Lighting Volumes for Spatially-Coherent Illumination," in 2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), Seattle, WA, USA, 2020 pp. 8077-8086.


### Tags

- :high_brightness: <font color='red'> **highlight!** </font>
- :bookmark: retinex

## dataset
[[SAW]](http://opensurfaces.cs.cornell.edu/publications/intrinsic/)
[[CGIntrinsics]](https://github.com/zl548/CGIntrinsics)

## Metrics
* **WHDR** [[project]](https://github.com/tnestmeyer/reflectance-filtering)
*  **AP**
