# AI Inference Engineering Handbook

![Handbook](https://img.shields.io/badge/Handbook-AI%20Inference%20Engineering-teal?style=flat-square) ![Build](https://img.shields.io/badge/build-passing-success?style=flat-square) ![Coverage](https://img.shields.io/badge/coverage-100%25-success?style=flat-square)

**A comprehensive guide to AI inference engineering** — from models to silicon — for IT, Platform, and Infrastructure Engineers who need to deploy and optimize AI models in production.

> 🚀 [View Live Handbook →](https://saajunaid.github.io/ai-inference-engineering-handbook/)

---

## At a Glance 🔎

• **Comprehensive**: 31 topics across 7 parts covering fundamentals to advanced deployment.  
• **Practical**: Real-world examples for ASR (Whisper) and LLM deployments.  
• **Self-contained**: Single `index.html` file — no build tools, just open and learn.

---

## What You'll Learn 📚

**Part I: Fundamentals**  
Understanding AI models, weights, activations, and the training vs inference distinction.

**Part II: Computation Graphs**  
Static vs dynamic graphs, graph optimization, and why it matters for performance.

**Part III: Runtimes**  
PyTorch, OpenVINO (CPU), TensorRT (GPU), ONNX Runtime, and llama.cpp for LLMs.

**Part IV: Hardware**  
CPU vs GPU architecture, kernels, ISAs (x86-64, ARM), CUDA, and specialized accelerators.

**Part V: Optimization**  
RAM vs VRAM, quantization (INT8/INT4), calibration, KV-cache, and batching strategies.

**Part VI: Deployment**  
Production ASR and LLM deployment, benchmarking, monitoring, and observability.

**Part VII: Advanced Topics**  
Hyperparameter tuning, call center ASR optimization, failure modes, and troubleshooting.

---

## Key Features ✨

• **Single-file handbook**: Everything in one HTML file for easy deployment and sharing.  
• **Practical focus**: Built for IT/Platform engineers, not ML researchers.  
• **Real examples**: Concrete ASR and LLM deployment scenarios with code.  
• **Visual learning**: Diagrams, tables, and color-coded sections for each part.  
• **Responsive design**: Optimized for desktop and mobile reading.  
• **Dark/Light themes**: Toggle between modern clean themes for comfortable reading.

---

## Quick Start 🚀

**View Online:**  
👉 [saajunaid.github.io/ai-inference-engineering-handbook](https://saajunaid.github.io/ai-inference-engineering-handbook/)

**Run Locally:**
```bash
# Clone the repository
git clone https://github.com/saajunaid/ai-inference-engineering-handbook.git

# Open in browser (no build needed!)
open index.html
```

---

## Who This Is For 👥

✅ **Infrastructure Engineers** managing AI deployments  
✅ **Platform Engineers** building ML infrastructure  
✅ **DevOps/MLOps professionals** supporting AI applications  
✅ **IT Engineers** deploying ASR or LLM systems  

❌ **Not for:** ML researchers or data scientists (use ML courses instead)

**No machine learning background required** — just systems/IT experience!

---

## Topics Covered 📖

### Part I: Fundamentals (4 topics)
1. What Is an AI Model?
2. Weights and Parameters
3. Activations and Memory
4. Training vs Inference

### Part II: Computation Graphs (3 topics)
5. Understanding Computation Graphs
6. Static vs Dynamic Graphs
7. Graph Optimization

### Part III: Inference Runtimes (6 topics)
8. What Is an Inference Runtime?
9. PyTorch Runtime
10. OpenVINO (Intel CPU optimization)
11. TensorRT (NVIDIA GPU optimization)
12. ONNX Runtime (Cross-platform)
13. llama.cpp (LLM on CPU)

### Part IV: Hardware & Silicon (5 topics)
14. Kernels and Operations
15. CPU vs GPU Architecture
16. Instruction Set Architectures (ISA)
17. CUDA and Alternatives
18. Specialized AI Hardware

### Part V: Optimization (5 topics)
19. RAM vs VRAM
20. Quantization Techniques (INT8, INT4)
21. Calibration for Quantization
22. KV-Cache Optimization
23. Batching Strategies

### Part VI: Production Deployment (4 topics)
24. ASR Deployment Guide
25. LLM Deployment Guide
26. Benchmarking and Metrics
27. Production Monitoring

### Part VII: Advanced Topics (4 topics)
28. Hyperparameter Tuning
29. Call Center ASR Optimization
30. Common Failure Modes
31. Troubleshooting Guide

---

## Contributing 🛠️

Improvements and corrections are welcome! Small, focused pull requests are easiest to review.

**Ways to contribute:**
- Report issues or suggest improvements
- Fix typos or clarify explanations
- Add new examples or diagrams
- Improve code samples

If you prefer, open an issue describing the change and we can iterate together.

---

## Technology Stack 💻

- **React 18** (UMD build, no compilation)
- **TailwindCSS** (CDN)
- **Lucide React** (icons)
- **Babel Standalone** (in-browser JSX transformation)

**Fonts:**
- Inter (body text)
- Fira Code (code blocks)

---

## Changelog 📝

- **2026-01-26** — Initial release with all 31 topics, modern clean theme, dark/light mode toggle
- **2026-01-26** — Added comprehensive README, `.gitignore`, deployed to GitHub Pages

---

## Notes 🗒️

• This is an **educational resource**: examples use production-ready patterns but may simplify for clarity.  
• **Performance numbers** are approximations based on typical hardware configurations.  
• Always **test and benchmark** on your specific hardware and workloads.

---

## License 📄

This handbook is licensed under the **MIT License**.

You are free to:

• ✅ Use this handbook for personal or commercial purposes  
• ✅ Modify and adapt the content  
• ✅ Distribute copies  
• ✅ Use in educational settings  

**Attribution:** Please credit "AI Inference Engineering Handbook by Junaid Shaik" when redistributing or adapting this work.

### MIT License

```
Copyright (c) 2026 Junaid Shaik

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

---

**Built with ❤️ by [Junaid Shaik](https://github.com/saajunaid)**

*/>@junAiD*