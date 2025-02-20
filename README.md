# Grape

# Introduction
GRAPE (Generator of RNA Aptamers Powered by AI-Assisted Evolution) is an AI-driven framework designed to accelerate RNA aptamer discovery and optimization. Aptamers are short nucleic acid sequences capable of binding specific targets with high affinity, making them valuable for applications in therapeutics, diagnostics, and synthetic biology.

Traditional aptamer selection methods, such as SELEX, often require multiple rounds of enrichment and are limited by in vitro conditions that do not fully capture intracellular interactions. GRAPE overcomes these limitations by integrating a Transformer-based conditional autoencoder with nucleic acid language models. It is uniquely guided by Next-Generation Sequencing (NGS) enrichment data obtained from CRISPR/Cas-based intracellular screening (CRISmers), enabling biologically relevant and highly functional aptamer generation.

GRAPE demonstrates superior performance compared to existing generative models by producing diverse, rational, and high-affinity aptamers with just a single round of intracellular screening. This has been validated across multiple targets, including human and viral proteins, highlighting its potential as a transformative tool in RNA evolution.

## Create Environment with yml
First,download the repository and create the environment.
```bash
   git clone https://github.com/tansaox2008123/Grape.git
   conda env create -f environment.yml
```

And you can get more details in these websites
RNA-FM https://github.com/ml4bio/RNA-FM.
Evo https://github.com/evo-design/evo

## Quickstart
Train your own model should follow this code
```bash
   python train_with_guidance.py  1 --cuda 0 --train_file your_train_file.txt --test_file your_test_file.txt --model_name your_model_name.txt --batch_size 1000
```
Numbers 1, 2, and 3 represent training the model using RNA-FM, EVO, and without using an LLM model, respectively.
The training file format can be referenced from the dateset following file.

generation RNA aptamers should follow this code
```bash
   python generation.py 1 --cuda 0 --input_file your_sample_aptamers.txt
   --output_file your_output_file.txt --model_name your_model_name.model --num 1000
```
The generation of Grape need sample RNA aptamers. And the format of sample_aptamers.txt should be same as training file ,and the num is generating the number of aptamers seq.

## Refernce
```bash
   RNA-FM
   @article{shen2024accurate,
  title={Accurate RNA 3D structure prediction using a language model-based deep learning approach},
  author={Shen, Tao and Hu, Zhihang and Sun, Siqi and Liu, Di and Wong, Felix and Wang, Jiuming and Chen, Jiayang and Wang, Yixuan and Hong, Liang and Xiao, Jin and others},
  journal={Nature Methods},
  pages={1--12},
  year={2024},
  publisher={Nature Publishing Group US New York}
}
   Evo
   @article{nguyen2024sequence,
   author = {Eric Nguyen and Michael Poli and Matthew G. Durrant and Brian Kang and Dhruva Katrekar and David B. Li and Liam J. Bartie and Armin W. Thomas and Samuel H. King and Garyk Brixi and Jeremy Sullivan and Madelena Y. Ng and Ashley Lewis and Aaron Lou and Stefano Ermon and Stephen A. Baccus and Tina Hernandez-Boussard and Christopher Ré and Patrick D. Hsu and Brian L. Hie },
   title = {Sequence modeling and design from molecular to genome scale with Evo},
   journal = {Science},
   volume = {386},
   number = {6723},
   pages = {eado9336},
   year = {2024},
   doi = {10.1126/science.ado9336},
   URL = {https://www.science.org/doi/abs/10.1126/science.ado9336},
}
```

