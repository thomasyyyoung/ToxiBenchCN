# Exploring Multimodal Challenges in Toxic Chinese Detection: Taxonomy, Benchmark, and Findings


<p align="center">
  <strong>Shujian Yang<sup>1</sup>, Shiyao Cui<sup>2</sup>, Chuanrui Hu<sup>3</sup>, Haicheng Wang<sup>1</sup>,<br>
  Tianwei Zhang<sup>4</sup>, Minlie Huang<sup>2</sup>, Jialiang Lu<sup>*1</sup>, Han Qiu<sup>*2</sup></strong><br>
  <sup>1</sup>Shanghai Jiao Tong University, China. 
  <sup>2</sup>Tsinghua University, China. 
  <sup>3</sup>Qihoo 360, China. 
  <sup>4</sup>Nanyang Technological University, Singapore.<br>
  <code>{thomasyang0925, jialiang.lu}@sjtu.edu.cn, qiuhan@tsinghua.edu.cn</code>
</p>

## 📖 Overview

This project introduces **ToxiBenchCN**, a comprehensive benchmark for evaluating the robustness of large language models (LLMs) in detecting **perturbed toxic Chinese content**. Based on a novel taxonomy of **8 multimodal perturbation techniques** (visual, phonetic, semantic), we curate a dataset (CNTP) and benchmark 9 SOTA LLMs, revealing key weaknesses and overcorrection patterns. We also explore two lightweight enhancement strategies: **In-context learning (ICL)** and **supervised fine-tuning (SFT)**.

[[📰 ACL 2025 Paper]](https://arxiv.org/abs/2505.24341) • [[📊 CNTP Dataset]](./CNTP_dataset) • [[📈 Benchmark Results]](./results)

---

## 📚 Taxonomy of Perturbations

| Category       | Type (Abbr.) | Brief Description                                            |
| -------------- | ------------ | ------------------------------------------------------------ |
| Visual (Glyph) | VSim         | Replace characters with visually similar ones                |
|                | Split        | Decompose characters into radicals or strokes                |
|                | Trad         | Substitute simplified characters with traditional variants   |
| Phonetic       | PY_Init      | Use pinyin initials to abbreviate toxic words                |
|                | PY_Full      | Use full pinyin spellings to represent toxic content         |
|                | Homo         | Replace words with homophones to disguise toxicity           |
| Semantic       | Shuffle      | Shuffle character order to alter semantic structure          |
|                | Emoji        | Replace characters with emojis to express offensive meanings |


<div style="text-align: center;">
  <img src="images/examples_of_perturbations.png" alt="examples of 8 perturbations" style="width: 90%;">
  <p>Examples of 8 perturbations</p>
</div>


## 🔍 Key Findings

- 📉 **LLMs struggle with multimodal perturbations** 
  Large language models (LLMs) show limited ability to detect **perturbed toxic content** in Chinese, especially when perturbations involve visual, phonetic, or semantic changes.

- ⚠️ **Small-scale ICL/SFT can lead to overcorrection** 
  In-context learning (ICL) or supervised fine-tuning (SFT) with just a few perturbed examples can increase detection rates, but also cause **overcorrection** — misclassifying many normal Chinese sentences as toxic.



## Citation

If you use the **CNTP dataset** or find our work on helpful for your research, please consider citing our ACL 2025 paper. Here is the BibTeX citation:

```bibtex
@article{yang2025exploring,
    title={Exploring Multimodal Challenges in Toxic Chinese Detection: Taxonomy, Benchmark, and Findings},
    author={Yang, Shujian and Cui, Shiyao and Hu, Chuanrui and Wang, Haicheng and Zhang, Tianwei and Huang, Minlie and Lu, Jialiang and Qiu, Han},
    journal={arXiv preprint arXiv:2505.24341},
    year={2025}
}
