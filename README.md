**Fine-Tuning LLaMA 3.1: Step-by-Step, Everything Explained in Detail**

<center>
    <img src="https://hyperight.com/wp-content/uploads/2024/07/Meta-Llama-31-1024x576.webp" width=4500">
</center>
[Image Reference](https://hyperight.com/wp-content/uploads/2024/07/Meta-Llama-31-1024x576.webp)

<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;">
        <strong>Mental health</strong> is a critical aspect of overall well being for emotional, psychological and social dimensions.
    </p>
</div>
<div style="background-color: #f2f2f2; border-left: 5px solid #4CAF50; padding: 15px; margin: 20px 0;">
    <p><strong>We are going to use Unsloth</strong> because it significantly enhances the efficiency of fine-tuning large language models (LLMs) specially LLaMA and Mistral. With Unsloth, we can use advanced quantization techniques, such as <strong>4-bit</strong> and <strong>16-bit quantization</strong>, to reduce the memory and speed up both training and inference. This means we can deploy powerful models even on hardware with limited resources but without compromising on performance.</p>

<p> Additionally, Unsloth broad compatibility and customization options allow to do the quantization process to fit the specific needs of products. This flexibility combined with its ability to cut <strong>VRAM usage by up to 60%</strong>, makes Unsloth an essential tool in AI toolkit. Its not just about optimizing models its about making cutting-edge AI more accessible and efficient for real world applications.</p>
</div>
#### For fine tuning, I used the following setup:

<ul style="margin1 20px; padding: 10px; list-style-type: disc;">
    <li><strong><a href="https://pytorch.org/" target="_blank">Torch 2.1.1 with CUDA 12.1</a></strong> for efficient computation.</li>
    <li><strong><a href="https://github.com/unslothai/unsloth" target="_blank">Unsloth</a></strong> to achieve 2X faster training speeds for the large language model (LLM).</li>
    <li><strong><a href="https://www.nvidia.com/content/dam/en-zz/Solutions/Data-Center/h100/PB-11773-001_v01.pdf" target="_blank">  H100 NVL GPU</a></strong> to handle the intensive processing requirement but you can use the less power GPU as well.</li>
</ul>

</ul>

<ul style="margin: 10px; padding: 10px; list-style-type: disc;">
    <strong><a href="https://llama.meta.com/" target="_blank">Why LLaMA 3.1?</a></strong>

**Its Open Source and Accessible** and offers the flexibility to customize and fine-tune it with the specific needs. Due to open source weights of the model from Meta, it is very easy to fine tune on any problem and we are going to fine tune it on mental health dataset from the <strong><a href="https://huggingface.co/datasets/Amod/mental_health_counseling_conversations" target="_blank">Hugging Face</a></strong>

<img src="https://miro.medium.com/v2/resize:fit:1400/1*mjbBdZ1-p7cKQkp-bU7aCg.gif">



## **About Author**

**Name:** Muhammad Imran Zaman  
**Email:** imranzaman.ml@gmail.com

**Professional Links:**
- [Kaggle Profile](https://www.kaggle.com/imranzaman)
- [LinkedIn Profile](https://www.linkedin.com/in/muhammad-imran-zaman/)
- [Google Scholar Profile](https://scholar.google.com/citations?user=ImranZaman)
- [YouTube Channel](https://www.youtube.com/channel/UCImranZaman)
- [GitHub Repository](https://github.com/Imran-ml/Mental-Health-Chatbot-LLaMA3.1)
- [Medium Story](https://imranzaman-5202.medium.com/)

