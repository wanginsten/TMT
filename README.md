# TMT: Adapting CLIP to Infrared Imagery via Text-Derived Modality Knowledge Transfer

This repository accompanies the paper:

> **TMT: Adapting CLIP to Infrared Imagery via Text-Derived Modality Knowledge Transfer**
> Ruofan Wang, Puzuo Wang, Xin Chen, Zibo Yu, Jungang Yang, Yi Hou
> *Knowledge-Based Systems* (under review)

It currently hosts the **evaluation prompt files** used in the paper, together with the official download links for the ten evaluation benchmarks.

**Code status.** The training and evaluation code is being organized and will be released in this repository. The prompt files and the evaluation protocol described below are complete and can be used directly.

## Prompt files

Each dataset directory under `prompts/` contains `prompts1.json`, `prompts2.json`, and `prompts3.json`, corresponding to Prompt 1, Prompt 2, and Prompt 3 in the paper (Tables 1–2 and Tables S1–S2 of the Supplementary Material). All methods in the paper were compared under the same three files per dataset. Retrieval evaluation uses IR-TD captions and does not involve these class prompts.

| Directory | Classes | Prompts per class per group | JSON structure |
| --- | ---: | ---: | --- |
| `M3FD` | 6 | 10 | top-level `prompts` field |
| `SMOD` | 4 | 10 | top-level `prompts` field |
| `flirv1` | 4 | 10 | top-level `prompts` field |
| `flirv2` | 12 | 10 | top-level `prompts` field |
| `llvip` | 2 | 10 | top-level `prompts` field |
| `JU-VNT-T` | 20 | 10 | top-level `prompts` field |
| `MFNet` | 8 | 10 | class names as top-level keys |
| `PST900` | 4 | 10 | class names as top-level keys |
| `CART` | 10 | 50 | top-level `prompts` field |
| `SemanticRT` | 13 | 50 | top-level `prompts` field |

For MFNet, the prompt keys are `bike`, `bump`, `car`, `carstop`, `colorcone`, `curve`, `guardrail`, and `person`. For PST900, they are `backpack`, `fireextinguisher`, `handdrill`, and `rescuerandy`. These keys are evaluation class names under our protocol, not the original training labels; when using the files, keep the original keys and class order and verify them against the dataset annotation mapping. The original (Chinese) documentation of this prompt inventory is preserved in `prompts/README_zh.md`.

The three prompt groups within each dataset contain distinct texts produced with Kimi-K2.5. The JSON files do not record generation call parameters, seeds, or timestamps; the paper therefore treats the three groups as observations under different prompt sets and does not claim that all prompt randomness is excluded.

## Evaluation benchmarks

The datasets are the property of their respective owners. Please obtain them from the official sources below and comply with their licenses and terms of use.

| Benchmark | Task in the paper | Official source |
| --- | --- | --- |
| M3FD | classification | [TarDAL repository (M3FD section)](https://github.com/JinyuanLiu-CV/TarDAL) |
| SMOD | classification | [AMFD repository](https://github.com/bigD233/AMFD) |
| FLIRv1 | classification | [FLIR starter thermal dataset release](https://www.flir.com/news-center/press-releases/flir-releases-starter-thermal-imaging-dataset-for-machine-learning-advanced-driver-assistance-development/) |
| FLIRv2 | classification | [Teledyne FLIR expanded starter dataset release](https://oem.flir.com/en-150/about/news/expanded-teledyne-flir-starter-thermal-dataset-for-adas-and-autonomous-vehicle-testing/) |
| LLVIP | classification | [LLVIP repository](https://github.com/bupt-ai-cz/LLVIP) |
| JU-VNT (thermal subset, JU-VNT-T) | classification | [JU-VNT repository](https://github.com/DVLP-CMATERJU/JU-VNT) |
| MFNet | classification | [MFNet project page](https://www.mi.t.u-tokyo.ac.jp/static/projects/mil_multispectral/) |
| PST900 | classification | [PST900 repository](https://github.com/ShreyasSkandanS/pst900_thermal_rgb) |
| CART | segmentation | [CART repository](https://github.com/aerorobotics/caltech-aerial-rgbt-dataset) |
| SemanticRT | segmentation | [SemanticRT repository](https://github.com/jiwei0921/SemanticRT) |

Detection-style datasets were converted into classification benchmarks by cropping the annotated infrared bounding boxes and using the crop labels as class labels; for MFNet and PST900, labeled infrared regions were used to form classification examples from the available annotations. See Section 4 of the paper for the full evaluation protocol.

## License

The prompt files in `prompts/` are released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/); see `LICENSE`. This license covers only the prompt files produced in this study, not the third-party datasets linked above.

## Citation

If you use the prompt files in your research, please cite:

```bibtex
@article{wang2026tmt,
  title   = {TMT: Adapting CLIP to Infrared Imagery via Text-Derived Modality Knowledge Transfer},
  author  = {Wang, Ruofan and Wang, Puzuo and Chen, Xin and Yu, Zibo and Yang, Jungang and Hou, Yi},
  journal = {Knowledge-Based Systems},
  note    = {Under review},
  year    = {2026}
}
```
