# Anima

![Anima Logo](https://github.com/lyogavin/Anima/blob/main/anima_logo.png?raw=true)


This is the first open source 33B Chinese LLM, we also support DPO alignment training and we have open source 100k context window. The latest update is AirLLM, a library helps you to infer 70B LLM from just single GPU with just 4GB memory.

第一个开源的基于QLoRA的33B中文大语言模型，支持了基于DPO的对齐训练。

我们也开源了100K输入窗口的开源模型Anima100K，基于Llama2，可商用。

最新开源了单卡跑70B模型的AirLLM。


*Read this in [English](README_en.md).*

<div align="left">

<a href="https://github.com/lyogavin/Anima/stargazers">![GitHub Repo stars](https://img.shields.io/github/stars/lyogavin/Anima?style=social)</a>
[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)](https://github.com/LianjiaTech/BELLE/blob/main/LICENSE)
[![Generic badge](https://img.shields.io/badge/wechat-Anima-brightgreen?logo=wechat)](https://static.aicompose.cn/static/wecom_barcode.png?t=1671918938)
[![Generic badge](https://img.shields.io/badge/🤗-Huggingface%20Repo-green.svg)](https://huggingface.co/lyogavin/Anima33B-merged)
[![Generic badge](https://img.shields.io/badge/🤗-Huggingface%20Repo-green.svg)](https://huggingface.co/lyogavin/Anima-7B-100K)
</div>

## 🔄 更新 Updates


[2023/11/17] Open source: AirLLM, inference 70B LLM with 4GB single GPU.

开源AirLLM，单卡4GB显存跑70B大模型，无需量化，无需模型压缩

[2023/09/06] open source 100K context window Llama2 based LLM

更新支持100k 上下文的基于Llama2的可商用大模型

[2023/06/29] Open source alignment training based on DPO+QLORA

更新基于DPO+QLoRA的Human Feedback训练

[2023/06/12] Open source the first 33B Chinese Large language model

开源了第一个基于QLoRA的中文33B大语言模型


## AirLLM, inference 70B LLM with 4GB single GPU

AirLLM optimizes inference memory usage, allowing 70B large language models to run inference on a single 4GB GPU card. No quantization, distillation, pruning or other model compression techniques that would result in degraded model performance are needed.

AirLLM优化inference内存，4GB单卡GPU可以运行70B大语言模型推理。不需要任何损失模型性能的量化和蒸馏，剪枝等模型压缩。


Find out more [Here](https://github.com/lyogavin/Anima/tree/main/air_llm)。

## 100K context length LLM

We released the new Anima open source 7B model, supporting an input window length of 100K! It’s based on LLama2, so available for commercial use!

With specifically curated long text question answering training data for the 100K input length, and a lot of memory optimizations, we enabled the LLama2 model to scale to 100K input length.


当输入长度支持100k，你甚至可以把整个知识库都放入Prompt交给模型。或者可以把一本书直接放到Prompt里边。再也不用各种费劲的向量化，文本分割。。。。

我们堆了各种最新的猛料：[XEntropy](https://github.com/NVIDIA/apex/tree/master/apex/contrib/xentropy)，[Paged 8bit Adamw](https://github.com/TimDettmers/bitsandbytes), [LORA](https://github.com/huggingface/peft), [Flashattention2](https://github.com/Dao-AILab/flash-attention)，并且专门针对长输入对于training和Inference代码都做了修改定制，使得单卡100G就可以训练100k窗口。单卡40G就可以进行推理。

训练数据上，从几十种公开数据集中精选了专门针对长输入的30k～100k长度的长文本训练数据，专门针对100K输入对模型进行了训练。

Find out more [Here](https://github.com/lyogavin/Anima/tree/main/anima_100k)。

[![Generic badge](https://img.shields.io/badge/🤗-Huggingface%20Repo-green.svg)](https://huggingface.co/lyogavin/Anima-7B-100K) 


## Anima 33B Chinese

We believe the future of AI will be fully open and democratized. AI should be a tool that’s accessible to everyone, instead of only the big monopolies(some of them have the term “open” in their names 😆 .). QLoRA might be an important step towards that future. We want to make some small contribution to the historical process of democratization of AI, we are open sourcing the 33B QLoRA model we trained: all the model parameters, code, datasets and evaluations are opened! 🤗


因此我们认为[QLoRA](https://arxiv.org/abs/2305.14314) 的工作很重要，重要到可能是个Game Changer。通过QLoRA的优化方法，第一次让33B规模的模型可以比较民主化的，比较低成本的finetune训练，并且普及使用。我们认为33B模型既可以发挥大规模模型的比较强的reasoning能力，又可以针对私有业务领域数据进行灵活的finetune训练提升对于LLM的控制力。

Find out more [Here](https://github.com/lyogavin/Anima/tree/main/training)。


[![Generic badge](https://img.shields.io/badge/🤗-Huggingface%20Repo-green.svg)](https://huggingface.co/lyogavin/Anima33B-merged) 


## Alignment training based on DPO and QLoRA

We open sourced latest alignment techinque - DPO.

Anima模型又开源了基于QLoRA的最新的DPO技术。

DPO是最新的最高效的RLHF训练方法。RLHF一直是生成式AI训练的老大难问题，也被认为是OpenAI的压箱底独家秘笈。DPO技术改变了这一切，让RLHF彻底傻瓜化！

我们开源了RLHF的低成本QLoRA的实现，一台GPU机器就可以训练33B模型的DPO！

Find out more [here](https://github.com/lyogavin/Anima/tree/main/rlhf)。

[![Generic badge](https://img.shields.io/badge/🤗-Huggingface%20Repo-green.svg)](https://huggingface.co/lyogavin/Anima33B-DPO-Belle-1k-merged) 


## Wechat 微信公众号

扫码：

![group](https://github.com/lyogavin/Anima/blob/main/assets/wechat_pub_account.jpg?raw=true)


## Wechat group 微信群

扫码进群：

<img src="https://github.com/lyogavin/Anima/blob/main/assets/wechat_group.png?raw=true" alt="group" style="width:260px;"/>





## Contribution 参与贡献

Buy me a coffee please! 欢迎大家参与贡献本项目 🙏

**如果你喜欢我们的项目，请帮忙点个⭐吧!**

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://bmc.link/lyogavinQ)




## ✍️ 艾写科技 & Anima AI LLC

<img src="https://static.aicompose.cn/static/logo/dabble-icon-recolor_trans_bg.svg?t=1698957644" alt="aiwrite" style="width:60px;padding-bottom:35px"/> <img src="https://static.aicompose.cn/static/logo/animaai_logo.png?t=1696952962" alt="aiwrite" style="width:170px;"/>

This work is from Anima AI LLC and aiwrite.ai.

此工作来自于[艾写科技](https://aiwrite.ai)， [Anima AI LLC](https://animaai.cloud)。



