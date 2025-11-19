🤖 GPT-2 Chatbot (Streamlit + Hugging Face)

This project is a simple, local chatbot built with Streamlit and the Hugging Face Transformers library.
It uses the openai-community/gpt2 text-generation model to simulate a conversational assistant focused on software engineering help.

You can easily replace GPT-2 with a stronger instruction-tuned model for better quality responses.

🚀 Features

🧠 Local GPT-2 text-generation chatbot

💬 Maintains chat history within the session

⚙️ Sidebar controls for:

Maximum new tokens

Temperature

Top-p sampling

Repetition penalty

🧹 Clear chat history button

📜 System prompt to guide model behavior

🖥️ Streamlit UI with chat bubbles (st.chat_message)

📦 Installation
1. Clone the repository
git clone https://github.com/yourusername/gpt2-chatbot.git
cd gpt2-chatbot

2. Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

3. Install dependencies
pip install streamlit transformers torch

▶️ Run the App
streamlit run app.py


Then open the URL displayed in the terminal (usually http://localhost:8501).

📁 Project Structure
.
├── app.py              # Main Streamlit chatbot application
├── README.md           # Project documentation
└── requirements.txt    # Optional: List of dependencies

🧠 How It Works
1. Model Loading

The GPT-2 text-generation pipeline is loaded once using @st.cache_resource for efficiency.

2. Instruction Prompting

A system instruction guides the model to behave like a concise software engineering assistant.

3. Conversation Builder

Chat history is formatted into a custom prompt:

Question: <previous question>
Answer: <previous answer>

4. Model Generation

GPT-2 generates new text based on:

max_new_tokens

temperature

top_p

repetition_penalty

Then the answer is extracted from "Answer:" onward.

5. UI

Streamlit’s st.chat_message() renders user and model messages in chat format.

🔧 Customization
Swap GPT-2 for a better model

For significantly better results, use a small, instruction-tuned model like:

google/gemma-2b-it

mistralai/Mistral-7B-Instruct-v0.2

tiiuae/falcon-7b-instruct

Example change:

pipeline("text-generation", model="google/gemma-2b-it")

⚠️ Limitations

GPT-2 is not instruction-tuned, so answers may be inconsistent.

No GPU acceleration unless manually configured.

Not suitable for production without enhancements.

📜 License

This project is open-source under the MIT License.
Feel free to modify and improve it!
