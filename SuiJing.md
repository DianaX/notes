## 隋静：基于人工智能与多模态神经影像的脑疾病生物学标记挖掘
视频链接：[隋静：多模态视频](https://www.bilibili.com/video/BV1Di4y1P7UR)
### 数据驱动：
- ICA
- PCA
- CCA
- Data Adaptive
### CCA和ICA的特点：
    CCA：最大化不同模态之间的相关性(共変性)，不保证空间成分的独立性
    ICA：最大优化空间的独立性，不保证模态之间的联系
### 启发：
    将两种技术结合起来，变成MCCA+jICA.
    优点：既能保证独立性，又能保证模态之间的共変性（共変性：不同模态得到的成分之间两两相关会得到一个由高到低的相关性变化，相关性特别高的称为多模态共变成分
### 用于多模态融合的特征：
**fMRI:** Task-related Contrast map  
**Rest state:** fALFF，ReHo  
**Function Connectivity:** seed based  
**Function Network Connectivity:** ICA-based
### 1 无监督多模态融合分析：
    将4D功能影像与3D结构影像一起开展协同分析（先PCA后ICA）
### 2 有监督多模态融合分析：
自闭症的三种亚型（症状由轻到重）：  
- **Asperger's:** 高智商的自闭症儿童
- **PDD-NOS:** 广泛性发育障碍
- **Autistic:** 典型性孤独症患者  

  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;为了进一步考察不同亚型之间的特定脑区变化，我们用自闭症儿童中常用的**ADOS评分**做引导，考察不同亚型之间症状所对应的一些变化脑区到底是哪一些。    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;发现**双侧前额叶**和**颞中回**是所有自闭症儿童都会损伤的脑区。  
### Fusion工具箱
    free download: Fusion ICA Toolbox(FIT)
    可融合FALFF、REHO、FC、GM、WM、EEG、MEG、Gene（不同于单模态影像预处理软件，需具备多模态数据预处理后特征）  
### 抑郁症动态功能连接研究
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;抑郁症被试在和**自我沉思相关的弱功能连接模式**下停留的时间更久。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;异常连接主要位于**背外侧前额叶、顶叶以及小脑**，且和**症状严重性、空间记忆功能**显著相关。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;受此启发，提出了**多尺度卷积循环神经网络算法** ，突破了现有fMRI分析“先借助时间序列构建功能连接矩阵再分类”的传统框架，能够**直接在时间序列上使用RNN模型自动学习（不需要运算FCN或FC）** fMRI的时间-空间特征，提高了算法的可解释性和分类精度（2-5%）。  
### 最新研究：基于多尺度互学习的图卷积神经网络  
- **多尺度图卷积网络**整合从粗到细的空间信息，同时结合脑网络的**相似度**度量，在ADHD、ADNI、WMH等多疾病分类中精度提高3-7%。  
- MTGCN（基于多尺度的三元组图卷积神经网络）使用**加权融合**策略进行模板融合，而M2TGCN使用**互学习**策略。  
- 两个多模板方法（MMTGCN和MTGCN）的结果优于4个单模板的。  
- 与使用较少ROI的模板相比，使用较多ROI的单一模板并不能保证更好的性能。  
- 使用多尺度的脑模板集成学习有助于提高分类结果。