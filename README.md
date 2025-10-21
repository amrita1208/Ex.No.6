# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date:
# Register no.25011865
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

#AI Tools Required:
Chat gpt and hugging face

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 

SAMPLE PYTHON CODE:

import openai
from transformers import pipeline

# Initialize APIs
openai.api_key = "YOUR_OPENAI_API_KEY"
summarizer = pipeline("summarization", model="facebook/bart-large-cnn")

# Input text
text = """Artificial Intelligence (AI) is transforming industries through automation,
predictive analytics, and intelligent systems. It enhances productivity and enables
data-driven decision-making in healthcare, education, and finance."""

# ChatGPT summarization (OpenAI API)
response_chatgpt = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": f"Summarize this text: {text}"}]
)
summary_chatgpt = response_chatgpt['choices'][0]['message']['content']

# Hugging Face summarization
summary_hf = summarizer(text, max_length=50, min_length=25, do_sample=False)[0]['summary_text']

# Display comparison
print("=== ChatGPT Summary ===")
print(summary_chatgpt)
print("\n=== Hugging Face Summary ===")
print(summary_hf)

# Simple analysis
print("\nComparison Analysis:")
if len(summary_chatgpt) > len(summary_hf):
    print("ChatGPT produced a more detailed summary.")
else:
    print("Hugging Face summary is more concise.")

Generated Output (Example):

ChatGPT Output:

“AI is revolutionizing industries by automating tasks, improving efficiency, and supporting decision-making in healthcare, finance, and education.”

Hugging Face Output:

“AI automates processes and aids data-based decisions in key sectors like health and finance.”

Analysis:

ChatGPT provided a more elaborate and contextual summary.

Hugging Face focused on brevity and keyword extraction.

ChatGPT displayed stronger comprehension and coherence, while Hugging Face performed faster and with concise phrasing.

# Conclusion:

The experiment successfully demonstrated the integration of multiple AI tools using Python. By applying the persona pattern as a programmer, it was shown that AI tools differ in tone, accuracy, and context handling. Using such integration allows developers to leverage the strengths of multiple AI systems for better decision-making and analysis.

# Result: The corresponding Prompt is executed successfully.
