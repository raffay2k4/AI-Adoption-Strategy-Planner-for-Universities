# AI Adoption Strategy Planner for Universities  

This project is an **Agentic AI system** designed to help universities adopt AI effectively.  
By taking a university’s objective (e.g., *“mental health of students”*) and a time duration, the agent autonomously:  

- Researches how AI is being used in that domain  
- Analyzes adoption in multiple regions  
- Identifies gaps and risks  
- Generates a **structured pilot plan in PDF form** tailored for the specified duration  

---

## Key Features
- **Autonomous Web Search & Research** → Finds credible, recent sources and extracts relevant information.  
- **Summarization & Insight Extraction** → Converts raw content into factual bullet points and key takeaways.  
- **Statistical Extraction** → Identifies numeric values (percentages, counts, costs) with contextual meaning.  
- **Citation Management** → Tracks and logs citations for transparency.  
- **PDF Strategy Report Generation** → Produces a pilot plan document for university decision-making.  

---

## Technologies & Frameworks Used  

### **LangChain Experimental (Plan-and-Execute Framework)**  
- Implemented the **Planner-Executor design pattern**  
  - **Planner** → `deepseek-r1-distill-llama-70b` (breaks down objectives into steps)  
  - **Executor** → `moonshotai/kimi-k2-instruct` (executes steps using registered tools)  

### **Custom Tools**  
- `web_search_tool` → Built with **Tavily API** for advanced, date-filtered academic/industry searches  
- `summarize_tool` → LLM-powered summarization into bullets & insights  
- `extract_stats_tool` → Regex + contextual extraction of percentages, monetary values, and counts  
- `generate_pdf_tool` → Built with **ReportLab**, generates structured, downloadable pilot plans  

### **LLMs via Groq API**  
- Used **ChatGroq wrappers** to call multiple LLMs for planning, execution, and summarization  
- Integrated **tiktoken** for token truncation → ensures efficiency & stability  

### **Orchestration & Transparency**  
- Custom **ReasoningCapture Callback Handler** logs:  
  - LLM prompts & outputs  
  - Tool usage  
  - Chain execution steps  
- Ensures the agent’s reasoning process is **auditable and transparent**  

### **User Interface**  
- Built an interactive **Gradio UI**:  
  - Input objective + timeframe  
  - Run the agent & view detailed reasoning logs  
  - Download the generated **PDF Pilot Plan**

![image alt](https://github.com/raffay2k4/AI-Adoption-Strategy-Planner-for-Universities/blob/79311f71c812bd68f8e79f18f82bd366683c2bea/Interface.jpg)
