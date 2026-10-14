# Marcella: A Python Chatbot

A lightweight, conversational chatbot built with Python and the [ChatterBot](https://github.com/gunthercox/ChatterBot) library. Marcella greets users, answers basic questions, and tells jokes through a simple command-line interface.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Customizing the Chatbot](#customizing-the-chatbot)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Marcella is a beginner-friendly chatbot designed to demonstrate how conversational agents can be trained and run with minimal setup. It combines ChatterBot's pre-built English language corpus with custom training dialogues, giving it a friendly personality and a sense of humor.

This is an actively evolving project. The current version covers the core conversational experience, with more features planned.

## Features

- **User Greetings**: Welcomes users with friendly, natural responses.
- **Joke Telling**: Lightens the conversation with jokes on request.
- **General Conversation**: Handles common small talk using ChatterBot's English corpus (greetings and conversations).
- **Custom Training**: Includes hand-written question-and-answer pairs that are easy to extend.
- **Clean Exit**: Ends the session gracefully with `:q`, `quit`, `exit`, or `bye`.

## Tech Stack

| Component | Details |
|-----------|---------|
| Language  | Python 3 |
| Library   | ChatterBot |
| Trainers  | `ChatterBotCorpusTrainer`, `ListTrainer` |
| Interface | Command line (CLI) |

## Getting Started

### Prerequisites

- Python 3.x
- `pip` package manager

> **Note:** ChatterBot has dependencies that may not work with the newest Python releases. If installation fails, try a virtual environment with an older, supported Python version (for example, Python 3.8 to 3.10) and check the ChatterBot documentation for current compatibility.

### Installation

1. **Clone the repository**

   ```bash
   git clone  https://github.com/wRawaan/chatbot.git
   cd chatbot
   ```

2. **(Recommended) Create a virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install chatterbot chatterbot-corpus
   ```

## Usage

Start the chatbot with:

```bash
python chatbot.py
```

On the first run, Marcella trains on the English corpus, which may take a moment. Once ready, you will see a `>` prompt. Type a message and press Enter.

### Example Session

```text
> Hi
Marcella: Welcome, friend 🤗
> tell me another joke
Marcella: Why don't scientists trust atoms? Because they make up everything!
> What is chatbot used for?
Marcella: A chatbot is used for automated conversation and assistance.
> bye
```

### Exit Commands

Type any of the following to end the session: `:q`, `quit`, `exit`, `bye`

## How It Works

1. **Initialization**: A `ChatBot` instance named "Marcella" is created.
2. **Corpus Training**: `ChatterBotCorpusTrainer` loads the built-in English corpus, including the greetings and conversations datasets.
3. **Custom Training**: `ListTrainer` adds custom dialogues for greetings, a description of what a chatbot is used for, and jokes.
4. **Interaction Loop**: The program reads user input, generates a response with `get_response()`, and prints it until an exit command is entered.

## Customizing the Chatbot

You can teach Marcella new responses by adding conversation pairs with `ListTrainer`:

```python
trainer = ListTrainer(chatbot)

trainer.train([
    "What is your favorite color?",
    "I'm partial to blue!"
])
```

Each list is treated as a conversation: the first item is the prompt, and the following item is the response.

## Roadmap

- [ ] Expand the joke library
- [ ] Add more conversation topics
- [ ] Persist user context across sessions
- [ ] Build a web or GUI interface
- [ ] Add unit tests

## Contributing

Contributions are welcome and appreciated.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a pull request

For bugs or feature ideas, please open an issue.

## License

This project is licensed under the [MIT License](LICENSE). 

---

Thank you for checking out Marcella! Enjoy the chat. 😊