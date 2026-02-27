# Zen Eco 4B Instruct

Efficient instruction-following model. Part of the Zen Eco family.

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Overview

Zen Eco 4B Instruct is the instruction-tuned variant of Zen Eco 4B. Fine-tuned for following complex instructions with high accuracy while maintaining the compact efficiency of the Eco architecture.

| Property | Value |
|----------|-------|
| Parameters | 4B |
| Context | 32K |
| License | Apache 2.0 |

## Usage

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model = AutoModelForCausalLM.from_pretrained("zenlm/zen-eco-instruct")
tokenizer = AutoTokenizer.from_pretrained("zenlm/zen-eco-instruct")

messages = [{"role": "user", "content": "Explain quantum computing in simple terms."}]
inputs = tokenizer.apply_chat_template(messages, return_tensors="pt")
output = model.generate(inputs, max_new_tokens=512)
print(tokenizer.decode(output[0], skip_special_tokens=True))
```

## Related

- [zen-eco](https://huggingface.co/zenlm/zen-eco) — Base 4B model
- [zen-eco-thinking](https://huggingface.co/zenlm/zen-eco-thinking) — Chain-of-thought variant
- [zen-eco-coder](https://huggingface.co/zenlm/zen-eco-coder) — Code variant
- [Zen LM](https://github.com/zenlm) — Full model family

Apache 2.0 · [Zen LM](https://zenlm.org) · [Hanzo AI](https://hanzo.ai)
