# OpenLKA: An Open Dataset for Lane Keeping Assist Systems

[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)  [![arXiv](https://img.shields.io/badge/arXiv-2505.09092-blue)](https://arxiv.org/abs/2505.09092)  [![Project Website](https://img.shields.io/badge/website-openlka.github.io-orange)](https://openlka.github.io)

OpenLKA is the **first large-scale, open, real-world dataset** focused on Lane Keeping Assist (LKA) performance. It pairs high-frequency CAN signals with synchronized front-camera video and rich scenario annotations across multiple modern production vehicles and diverse roadway conditions.

---

## 📦 What’s inside?

| Item                       | Description                                                               |
| -------------------------- | ------------------------------------------------------------------------- |
| **Raw & decoded CAN logs** | Steering torque, yaw rate, LKA status, lane-line bit-flags, etc. (100 Hz) |
| **Front-view video**       | 1080 p @ 20 fps (*qcamera*) aligned to CAN timestamps                     |
| **Scenario labels**        | Weather, lighting, curvature, pavement quality, road geometry, …          |
| **Edge-case clips**        | 4 h of lane departures, faded markings, heavy rain, glare, sharp turns    |
| **LKAlert subset**         | 35 k time steps with human ✓/✗ alerts + free-text reasoning               |

> **Testing fleet:** Volkswagen, Toyota, Tesla, Hyundai, Kia, Honda, Ford (2021–2024 MY)

---

## 📜 Related papers & key figures

### 1. OpenLKA Dataset

[**OpenLKA: An Open Dataset of Lane Keeping Assist from Recent Car Models under Real-world Driving Conditions**](https://arxiv.org/pdf/2505.09092)

![Dataset overview](https://github.com/OpenLKA/OpenLKA/blob/main/static/images/OpenLKA_view.png)

---

### 2. Empirical Performance Evaluation

[**Empirical Performance Evaluation of Lane Keeping Assist on Modern Production Vehicles**](https://arxiv.org/pdf/2505.11534)

![Per-vehicle performance example](https://github.com/OpenLKA/OpenLKA/blob/main/static/images/LKAnalysis_Perception.png)

---

### 3. Predictive Alerting with Vision-Language Models

[**Bridging Human Oversight and Black-box Driver Assistance: Vision-Language Models for Predictive Alerting in Lane Keeping Assist Systems**](https://arxiv.org/pdf/2505.11535)

<p align="center">
  <img src="https://github.com/OpenLKA/OpenLKA/blob/main/static/images/LKAlert_WordCloud.png" width="45%">
</p>

<p align="center">
  <img src="https://github.com/OpenLKA/OpenLKA/blob/main/static/images/LKAlert_ModelStructure.png" width="100%">
</p>

---

## 🔗 Dataset download

```text
🔋  OpenLKA-EV (part)
🌐  OpenLKA-Normal
❌  OpenLKA-Failure
⚠️  OpenLKA-Alert
```

Links are temporarily hosted on Dropbox during the pre-official phase:

* [EV subset](https://www.dropbox.com/scl/fo/z3iyagi4g04b1yn6pnylk/ALum3lMAZHpiJFNa7fxzfmM?rlkey=z3zdr7ohyanugctpoosmtwncl&dl=0)
* [Normal driving](https://www.dropbox.com/scl/fo/2xoy6kwb3byedk12phadm/AK6YtCpBc-C-eezVT2ZDbWc?rlkey=qbbfbwaqve0ymk90bu6e8kg4n&dl=0)
* [Failure scenarios](https://www.dropbox.com/scl/fo/ja3m1cdqd5kpm68kuarg4/AJJet0tCMThkzmmYwsIgpL4?rlkey=zkkb1zadhw9gr3ayz5a4wik67&dl=0)
* [Alert subset](https://www.dropbox.com/scl/fo/jv5aj0qb1w6qzrd3vum4w/ALa0HR32eQM0Bg--hDf-GzQ?rlkey=tey9v0k1r22xo5thrj7qb15qh&dl=0)

> ⚠️ **NOTE:** Large files (> 500 GB) — use the provided `download.sh` with `--partial` flags to fetch only required splits.

---

## 🚀 Quick start

```bash
# Install dependencies
pip install -r requirements.txt

# Decode raw CAN → CSV (Tesla example)
python tools/decode_can.py \
    --dbc dbcs/Tesla_Model3.dbc \
    --log data/raw/tesla_001.log \
    --out data/decoded/tesla_001.csv

# Visualize lane-keeping error
python notebooks/plot_lane_deviation.ipynb
```

---

## 🛠️ Roadmap

See **Issue #1 – Pre-Official Release Checklist** for detailed milestones (reverse-engineered DBCs, edge-case curation, LKAlert labels, etc.).

---

## 📣 Citation

If you use OpenLKA, please cite **all** three companion papers:

```bibtex
@misc{wang2025openlkaopendatasetlane,
      title={OpenLKA: an open dataset of lane keeping assist from market autonomous vehicles}, 
      author={Yuhang Wang and Abdulaziz Alhuraish and Shengming Yuan and Shuyi Wang and Hao Zhou},
      year={2025},
      eprint={2501.03287},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2501.03287}, 
}
```

(See `CITATION.bib` for the full list.)

---

## 🤝 Contributing

Pull requests are welcome! Please read `CONTRIBUTING.md` and open an issue to discuss larger changes.

---

## 📄 License

OpenLKA is released under the **MIT License**.

---

## ✉️ Contact

Questions? Create an issue or email **[openlka@googlegroups.com](mailto:openlka@googlegroups.com)**.
