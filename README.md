# selfhosted-ollama-linebot
A LINE-integrated AI agent powered by a locally deployed LLM using Ollama.

# LINE AI Agent - Local LLM Implementation and Hardware Optimization

### Project Background / 專案背景
This project was inspired by the concept of AI Agents—autonomous tools capable of handling tasks on behalf of users. To explore this technology while prioritizing data privacy and system security, I utilized a dedicated older PC to host the OpenClaw framework, as it requires extensive system permissions.

這個專案的靈感來自 AI Agent 的概念。為了在研究這項技術的同時確保資訊安全，我找了一台閒置的舊電腦來安裝 OpenClaw，避免將主要設備的權限直接開放給自動化工具。

### Key Milestones / 實作歷程
* **Cross-Platform Integration**: Researched and implemented LINE Messaging API integration to enable remote control of the AI Agent via smartphone.
* **From Cloud to Local**: After reaching the usage limits of cloud-based APIs (Google Gemini), I transitioned to a self-hosted AI architecture to ensure continuous availability.
* **Local Deployment**: Successfully configured Ollama and deployed language models directly on local hardware to bypass cloud quotas and maintain offline functionality.

### Performance Challenges and Analysis / 效能挑戰與分析
During testing, I observed significant response latency. My analysis identified two primary bottlenecks:
在實際測試中，我發現回覆速度較慢，分析後認為有兩個主因：

* **Hardware Limitations**: The system runs on an Intel i3-4150 CPU, which faces computational constraints during large language model (LLM) inference.
* **Model Size**: Larger models impose a heavy load on the system's memory and processing power.

**Solution**: I optimized the configuration by selecting the **qwen2.5:0.5b** model, effectively balancing model functionality with the available hardware resources.

### File Structure / 檔案說明
* **openclaw.json**: Main configuration and LINE API integration (Sensitive tokens are masked).
* **models.json**: Local Ollama model configurations and inference parameters.
* **agents/**: AI persona definitions and custom system instructions.
