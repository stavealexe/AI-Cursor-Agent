# AI-Cursor-Agent 🤖🖱️

An advanced AI-powered desktop automation tool that controls your cursor and keyboard using multiple LLM providers. The AI "sees" your screen and intelligently navigates your desktop like a human would.

## 🎯 Features

- **Multi-LLM Support**: OpenAI (GPT-4 Vision), Claude, Ollama (local), Groq, and more
- **Cross-Platform**: Windows & Linux (Arch, Ubuntu, Fedora)
- **Vision-Based Navigation**: AI sees your screen and makes intelligent decisions
- **Human-Like Cursor Movement**: Natural curves, randomized delays, realistic behavior
- **Keyboard & Mouse Control**: Full desktop automation capabilities
- **GUI Control Panel**: Real-time monitoring and task input
- **Flexible Architecture**: Easy to add new LLM providers
- **Logging & Debugging**: Comprehensive logs for troubleshooting

## 📋 Project Structure

AI-Cursor-Agent/ 
├── README.md 
├── requirements.txt 
├── setup.py 
├── config/ 
│ ├── config.yaml 
│ └── llm_config.json 
├── src/ 
│ ├── init.py 
│ ├── main.py 
│ ├── agent/ 
│ │ ├── init.py 
│ │ ├── ai_agent.py 
│ │ ├── cursor_controller.py 
│ │ ├── screenshot_capture.py 
│ │ └── keyboard_controller.py 
│ ├── llm/ 
│ │ ├── init.py 
│ │ ├── base_llm.py 
│ │ ├── openai_provider.py 
│ │ ├── claude_provider.py 
│ │ ├── ollama_provider.py 
│ │ ├── groq_provider.py 
│ │ └── llm_factory.py 
│ ├── ui/ 
│ │ ├── init.py 
│ │ ├── main_window.py 
│ │ ├── styles.py 
│ │ └── widgets.py 
│ └── utils/ 
│ ├── init.py 
│ ├── logger.py 
│ ├── config_loader.py 
│ └── helpers.py 
├── tests/ 
│ ├── init.py 
│ ├── test_cursor.py 
│ ├── test_llm.py 
│ └── test_agent.py 
└── docs/ 
├── INSTALLATION.md 
├── CONFIGURATION.md 
├── USAGE.md 
└── LLM_SETUP.md

Code

## 🚀 Quick Start

### Prerequisites
- Python 3.9+
- pip / pipenv
- An LLM API key (OpenAI, Claude, Groq, etc.) OR local Ollama setup

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/stavealexe/AI-Cursor-Agent.git
cd AI-Cursor-Agent
Install dependencies
bash
pip install -r requirements.txt
Configure your LLM

Copy config/llm_config.json.example to config/llm_config.json
Add your API keys (see LLM_SETUP.md)
Run the application

bash
python src/main.py
🎮 Usage
Via GUI
bash
python src/main.py --gui
Via Command Line
bash
python src/main.py --task "Open Chrome and navigate to github.com"
Programmatically
Python
from src.agent.ai_agent import AIAgent

agent = AIAgent(llm_provider="openai")
agent.execute_task("Take a screenshot and describe what you see")
🔧 Configuration
Edit config/config.yaml:

YAML
agent:
  llm_provider: "openai"  # openai, claude, ollama, groq
  vision_enabled: true
  cursor_speed: 0.5
  natural_movement: true
  debug_mode: false

cursor:
  smoothing: true
  curve_intensity: 0.7
  random_delays: true
  min_delay: 0.1
  max_delay: 0.5

screen:
  capture_interval: 1.0
  resolution: "auto"
🧠 Supported LLMs
Provider	Type	Vision	Cost	Setup
OpenAI GPT-4 Vision	API	✅	Paid	Easy
Anthropic Claude 3	API	✅	Paid	Easy
Ollama (LLaMA 2/Mistral)	Local	❌	Free	Medium
Groq LPU	API	✅	Free Tier	Easy
Google Gemini	API	✅	Paid	Easy
See LLM_SETUP.md for detailed configuration.

🎨 GUI Features
Live Desktop Feed: Real-time screenshot with cursor overlay
Task Input: Enter natural language tasks
Execution Logs: See what the AI is doing step-by-step
Settings Panel: Adjust cursor speed, delays, and behavior
Emergency Stop: Kill button for safety
🛡️ Safety Features
Pause/Resume functionality
Screen region limiting (stay within specified area)
Action confirmation (optional)
Timeout limits on tasks
Detailed logging of all actions
📚 Documentation
Installation Guide - Detailed setup for Windows & Linux
Configuration Guide - All configuration options
Usage Guide - Examples and workflows
LLM Setup - API key setup for each provider
🔄 How It Works
Code
┌─────────────────────────────────────────┐
│   User Input / Task                     │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│   Screenshot Capture                    │
│   (Send to AI for Vision)               │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│   LLM Analysis & Decision                │
│   (What to do next?)                     │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│   Action Execution                       │
│   • Move cursor (natural curve)          │
│   • Click / Type / Scroll               │
└────────────────┬────────────────────────┘
                 │
                 └──→ Loop until task complete
⚙️ System Requirements
Windows
Windows 10 / 11
Python 3.9+
No additional system libraries required
Linux (Arch)
bash
sudo pacman -S python python-pip xdotool wmctrl
Linux (Ubuntu/Debian)
bash
sudo apt install python3 python3-pip xdotool wmctrl
🤝 Contributing
Contributions welcome! Areas to help:

New LLM providers
Improved cursor algorithms
Better vision processing
UI enhancements
Platform-specific optimizations
📝 License
MIT License - See LICENSE file

⚠️ Disclaimer
This tool is for automation and testing purposes. Use responsibly:

Obtain proper authorization before automating any system
Be aware of terms of service violations
Test thoroughly in safe environments
Use appropriate delays to avoid detection/blocking
🆘 Troubleshooting
See docs/TROUBLESHOOTING.md for common issues.

💬 Support
Issues: GitHub Issues
Discussions: GitHub Discussions
Made with ❤️ for automation enthusiasts

Code
Please confirm you want Copilot to make this change in the stavealexe/AI-Cursor-Agent repository on the default branch.

Make these code changes?
requirements.txt

txt
# Core Dependencies
python-dotenv==1.0.0
PyYAML==6.0

# LLM & API
openai==1.3.0
anthropic==0.7.0
requests==2.31.0
aiohttp==3.9.0

# Local LLM Support
ollama==0.0.48
groq==0.4.0

# Screenshot & Vision
Pillow==10.0.0
opencv-python==4.8.1
numpy==1.24.3

# Cursor & Keyboard Control
pynput==1.7.6
pyautogui==0.9.53

# Linux-specific (xdotool support)
python-xlib==0.33

# GUI
PyQt6==6.6.1
PyQt6-sip==13.6.0

# Utilities
colorama==0.4.6
tqdm==4.66.1
tenacity==8.2.3

# Development & Testing
pytest==7.4.0
pytest-cov==4.1.0
black==23.9.1
flake8==6.1.0
mypy==1.5.1

# Logging
loguru==0.7.2

# Task Scheduling
schedule==1.2.0

# Config Management
pydantic==2.4.0

Please confirm you want Copilot to make this change in the stavealexe/AI-Cursor-Agent repository on the default branch.
