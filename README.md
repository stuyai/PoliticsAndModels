# Politics and Models

This project demonstrates the use of various open-source models from Hugging Face to generate text based on different prompts. The models used include Llama, GPT-2, and Deepseek.

## Installation

To install the necessary dependencies, run the following command:

```bash
!pip install bitsandbytes
```

## Usage

### Logging into Hugging Face

First, log in to Hugging Face using your token:

```bash
!huggingface-cli login
```

### Llama Model

To use the Llama model for text generation:

```python
from transformers import pipeline
pipe = pipeline("text-generation", model="meta-llama/Llama-3.2-1B")
prompt = "Once upon a time:"
output = pipe(prompt, max_length=300, num_return_sequences=1)
print(output[0]['generated_text'])
```

### GPT-2 Model

To use the GPT-2 model for text generation:

```python
from transformers import pipeline
generator = pipeline("text-generation", model="gpt2")
prompt = "Once upon a time:"
output = generator(prompt, max_length=300, num_return_sequences=1)
print(output[0]['generated_text'])
```

### Deepseek Model

To use the Deepseek model for text generation:

```python
from transformers import pipeline
pipe = pipeline("text-generation", model="deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B", max_length=150, num_return_sequences=1)
messages = [{"role": "user", "content": "Once upon a time:"}]
output = pipe(messages)
print(output[0]["generated_text"][1]["content"])
```

## Goals

- Try some new models and some new prompts
- Explore Llama, GPT, and Deepseek open-source models

## License

This project is licensed under the MIT License.