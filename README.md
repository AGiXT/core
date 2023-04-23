# Agent-LLM

Agent-LLM is an Artificial Intelligence Automation Platform designed for efficient AI instruction management across multiple providers. Equipped with adaptive memory, this versatile solution offers a powerful plugin system that supports a wide range of commands, including web browsing. With growing support for numerous AI providers and models, Agent-LLM is constantly evolving to cater to diverse applications.

[<img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/636e0a6a49cf127bf92de1e2_icon_clyde_blurple_RGB.png" height="70" style="margin: 0 10px">](https://discord.gg/vfXjyuKZ)[<img src="https://img.freepik.com/free-icon/twitter_318-674515.jpg" height="70" style="margin: 0 10px">](https://twitter.com/Josh_XT)[<img src="https://qph.cf2.quoracdn.net/main-qimg-729a22aba98d1235fdce4883accaf81e" height="70" style="margin: 0 10px">](https://github.com/Josh-XT/Agent-LLM)

⚠️ **Please note that using some AI providers, such as OpenAI's API, can be expensive. Monitor your usage carefully to avoid incurring unexpected costs.  We're NOT responsible for your usage under any circumstance.**

![image](https://user-images.githubusercontent.com/102809327/233758245-94535c01-d4e8-4f9c-9b1c-244873361c85.png)

⚠️ **This project is under active development and may still have issues.** We appreciate your understanding and patience. If you encounter any problems, please first check the open issues. If your issue is not listed, kindly create a new issue detailing the error or problem you experienced. Thank you for your support!

## Table of Contents

- [Agent-LLM](#agent-llm)
  - [Table of Contents](#table-of-contents)
  - [Key Features](#key-features)
  - [Web Application Features](#web-application-features)
  - [Quick Start](#quick-start)
    - [Not using OpenAI? No problem!](#not-using-openai-no-problem)
  - [Development Environment Installation and Setup](#development-environment-installation-and-setup)
  - [Configuration](#configuration)
    - [Local Setup (Alternative)](#local-setup-alternative)
  - [API Endpoints](#api-endpoints)
  - [Extending Functionality](#extending-functionality)
    - [Commands](#commands)
    - [AI Providers](#ai-providers)
  - [Acknowledgments](#acknowledgments)
  - [Contributing](#contributing)
  - [Donations and Sponsorships](#donations-and-sponsorships)
  - [Usage](#usage)

## Key Features

- Adaptive long-term and short-term memory management

- Versatile plugin system with extensible commands for various AI models

- Wide compatibility with multiple AI providers, including:

  - OpenAI GPT-3.5, GPT-4

  - Oobabooga Text Generation Web UI

  - Kobold

  - llama.cpp

  - FastChat

  - Google Bard

  - And More!

- Web browsing and command execution capabilities

- Code evaluation support

- Seamless Docker deployment

- Integration with Huggingface for audio-to-text conversion

- Interoperability with platforms like Twitter, GitHub, Google, DALL-E, and more

- Text-to-speech options featuring Brian TTS, Mac OS TTS, and ElevenLabs

- Continuously expanding support for new AI providers and services

## Web Application Features

The frontend web application of Agent-LLM provides an intuitive and interactive user interface for users to:

- Manage agents: View the list of available agents, add new agents, delete agents, and switch between agents.
- Set objectives: Input objectives for the selected agent to accomplish.
- Start tasks: Initiate the task manager to execute tasks based on the set objective.
- Instruct agents: Interact with agents by sending instructions and receiving responses in a chat-like interface.
- Available commands: View the list of available commands and click on a command to insert it into the objective or instruction input boxes.
- Dark mode: Toggle between light and dark themes for the frontend.
- Built using NextJS and Material-UI
- Communicates with the backend through API endpoints

## Quick Start

1. Obtain an OpenAI API key from [OpenAI](https://platform.openai.com) and add it to your `.env` file.
2. Set the `OPENAI_API_KEY` in your `.env` file using the provided [.env.example](https://github.com/Josh-XT/Agent-LLM/blob/main/.env.example) as a template.

```
wget https://raw.githubusercontent.com/Josh-XT/Agent-LLM/main/docker-compose.yml
wget https://raw.githubusercontent.com/Josh-XT/Agent-LLM/main/.env.example
mv .env.example .env
```

3. Run the following Docker command in the folder with your `.env` file:

```
docker compose up -d
```

4. Access the web interface at http://localhost

### Not using OpenAI? No problem!
We are constantly trying to expand our AI provider support.  Take a look at our Jupyter Notebooks for Quick starts for these:

1. [OpenAI](https://github.com/Josh-XT/Agent-LLM/blob/main/notebooks/openai.ipynb)
2. [llamacpp](https://github.com/Josh-XT/Agent-LLM/blob/main/notebooks/llamacpp.ipynb)
3. [Oobabooga Text Generation Web UI](https://github.com/Josh-XT/Agent-LLM/blob/main/notebooks/oobabooga.ipynb)

For more detailed setup and configuration instructions, refer to the sections below.

## Development Environment Installation and Setup

1. Clone the repository.
```
git clone https://github.com/Josh-XT/Agent-LLM
```
2. Install the required Python packages:
```
pip install -r requirements.txt
```
3. Configure the necessary environment variables in the `.env` file using `.env.example` as a template.
4. Launch Agent-LLM using Docker (recommended) or by following the steps in the "Local Setup (Alternative)" section to set up the frontend and run the `app.py` script.

## Configuration

Agent-LLM utilizes a `.env` configuration file to store AI language model settings, API keys, and other options. Use the supplied `.env.example` as a template to create your personalized `.env` file. Configuration settings include:

- **INSTANCE CONFIG**: Set the agent name, objective, and initial task.
- **AI_PROVIDER**: Choose between OpenAI, llama.cpp, or Oobabooga for your AI provider.
- **AI_PROVIDER_URI**: Set the URI for custom AI providers such as Oobabooga Text Generation Web UI (default is http://127.0.0.1:7860).
- **MODEL_PATH**: Set the path to the AI model if using llama.cpp or other custom providers.
- **COMMANDS_ENABLED**: Enable or disable command extensions.
- **MEMORY SETTINGS**: Configure short-term and long-term memory settings.
- **AI_MODEL**: Specify the AI model to be used (e.g., gpt-3.5-turbo, gpt-4, text-davinci-003, Vicuna, etc.).
- **AI_TEMPERATURE**: Set the AI temperature (leave default if unsure).
- **MAX_TOKENS**: Set the maximum number of tokens for AI responses (default is 2000).
- **WORKING_DIRECTORY**: Set the agent's working directory.
- **EXTENSIONS_SETTINGS**: Configure settings for OpenAI, Huggingface, Selenium, Twitter, and GitHub.
- **VOICE_OPTIONS**: Choose between Brian TTS, Mac OS TTS, or ElevenLabs for text-to-speech.

For a detailed explanation of each setting, refer to the `.env.example` file provided in the repository.

### Local Setup (Alternative)

To run Agent-LLM without Docker:

1. Open two separate terminals, one for the backend and one for the front end. Navigate to the Agent-LLM folder in both.
2. Install dependencies and run the backend:
   ```
   pip install -r requirements.txt
   python app.py
   ```

3. Install dependencies and run the frontend:
   ```
   cd frontend
   npm install
   npm run build
   npm start
   ```

Access the Agent-LLM web interface at http://localhost:3000.

## API Endpoints

Agent-LLM provides several API endpoints for managing agents, managing tasks, and managing chains.

To learn more about the API endpoints and their usage, visit the API documentation at http://localhost:5000/docs (swagger) or http://localhost:5000/redoc (Redoc).

## Extending Functionality

### Commands

To introduce new commands, generate a new Python file in the `commands` folder and define a class inheriting from the `Commands` class. Implement the desired functionality as methods within the class and incorporate them into the `commands` dictionary.

### AI Providers

To switch AI providers, adjust the `AI_PROVIDER` setting in the `.env` file. The application is compatible with OpenAI, Oobabooga Text Generation Web UI, and llama.cpp. To support additional providers, create a new Python file in the `provider` folder and implement the required functionality.

## Acknowledgments

This project was inspired by and utilizes code from the following repositories:

- [babyagi](https://github.com/yoheinakajima/babyagi)
- [Auto-GPT](https://github.com/Significant-Gravitas/Auto-GPT)

Please consider exploring and contributing to these projects as well.

## Contributing

We welcome contributions to Agent-LLM! If you're interested in contributing, please check out the open issues, submit pull requests, or suggest new features. To stay updated on the project's progress, follow [@Josh_XT](https://twitter.com/Josh_XT) on Twitter.

## Donations and Sponsorships
We appreciate any support for Agent-LLM's development, including donations, sponsorships, and any other kind of assistance. If you would like to support us, please contact us through our [Discord server](https://discord.gg/Na8M7mTayp) or Twitter [@Josh_XT](https://twitter.com/Josh_XT).

We're always looking for ways to improve Agent-LLM and make it more useful for our users. Your support will help us continue to develop and enhance the application. Thank you for considering to support us!

## Usage

Run Agent-LLM using Docker (recommended) or by running the `app.py` script. The application will load the initial task and objective from the configuration file and begin task execution. As tasks are completed, Agent-LLM will generate new tasks, prioritize them, and continue working through the task list.
