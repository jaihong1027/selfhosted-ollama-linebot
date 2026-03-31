# selfhosted-ollama-linebot
A LINE-integrated AI agent powered by a locally deployed LLM using Ollama.

## Project Background / 專案背景
This project was inspired by the concept of AI Agents—autonomous tools capable of handling tasks on behalf of users. To explore this technology while prioritizing data privacy and system security, I utilized a dedicated older PC to host the OpenClaw framework, as it requires extensive system permissions.

這個專案的靈感來自 AI Agent 的概念。為了在研究這項技術的同時確保資訊安全，我找了一台閒置的舊電腦來安裝 OpenClaw，避免將主要設備的權限直接開放給自動化工具。

## Key Milestones / 實作歷程
* **Cross-Platform Integration**: Researched and implemented LINE Messaging API integration to enable remote control of the AI Agent via smartphone.
  * **跨平台整合**：研究並實作 LINE Messaging API 串接，實現透過手機即可遠端操控 AI Agent。
* **From Cloud to Local**: After reaching the usage limits of cloud-based APIs (Google Gemini), I transitioned to a self-hosted AI architecture to ensure continuous availability.
  * **從雲端轉成本地端**：在達到雲端 API (Google Gemini) 的使用額度限制後，我切換到本地端 AI 架構以確保系統能持續運作。
* **Local Deployment**: Successfully configured Ollama and deployed language models directly on local hardware to bypass cloud quotas, maintain offline functionality, and ensure operational security.
  * **本地端部署**：成功配置 Ollama 並將語言模型直接部署在本地硬體，繞過雲端配額限制並維持離線運作功能，也確保運作時的安全。

## Performance Challenges and Analysis / 效能挑戰與分析
During testing, I observed significant response latency. My analysis identified two primary bottlenecks:

在實際測試中，我發現回覆速度較慢，分析後認為有兩個主因：

* **Hardware Limitations**: The system runs on an Intel i3-4150 CPU, which faces computational constraints during large language model (LLM) inference.
  * **硬體限制**：系統運行於 Intel i3-4150 CPU，在大型語言模型 (LLM) 推論時面臨運算效能瓶頸。
* **Model Size**: Larger models impose a heavy load on the system's memory and processing power.
  * **模型規模**：較大的語言模型會對系統記憶體與運算能力造成沈重負擔。

**Solution**: I optimized the configuration by selecting a smaller model (qwen2.5:0.5b), effectively balancing model functionality with the available hardware resources.

**解決方案**：我透過選擇 **qwen2.5:0.5b** 這個較小的模型以優化配置，有效在模型功能與現有硬體資源之間取得平衡。

## File Structure / 檔案說明
* **openclaw.json**: Main configuration and LINE API integration (Sensitive tokens are masked).
  * **openclaw.json**：主要系統配置與 LINE API 串接設定（API/Token已遮蔽）。
* **models.json**: Local Ollama model configurations and inference parameters.
  * **models.json**：本地端 Ollama 模型配置與推論參數定義。
* **agents/**: AI persona definitions and custom system instructions.
  * **agents/**：AI 角色定位與自定義系統指令。
