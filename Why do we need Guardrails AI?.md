
# Guardrails AI

Guardrails AI is a framework and approach used in Generative AI to make AI applications safer, more reliable, and more controlled.

**In simple terms:**

Guardrails AI acts like a security checkpoint between an LLM and the user/application.

---

## 1. Why Do We Need Guardrails AI?

Suppose you develop a real-estate AI chatbot.

**Without Guardrails:**
- It may provide incorrect property prices.
- It may generate misleading information.
- It may reveal confidential customer information.
- It may respond to unrelated questions.
- It may generate harmful or inappropriate content.

**With Guardrails:**

You can validate and control the AI's responses.

---

## 2. How Guardrails AI Works

```text
User Input
    |
    v
What is the price of this property?
    |
    v
Input Guardrails
    |
    v
Check unsafe input, sensitive data and relevance
    |
    v
LLM (Gemini / GPT / Llama)
    |
    v
Generates an answer
    |
    v
Output Guardrails
    |
    v
Validate accuracy, format and sensitive information
    |
    v
Safe Response to User
```

---

## 3. Important Types of Guardrails

| Guardrail | Purpose |
|---|---|
| Input Validation | Check user input |
| Output Validation | Check AI responses |
| PII Detection | Protect personal information |
| Toxicity Detection | Prevent harmful content |
| Hallucination Checks | Identify unsupported answers |
| Format Validation | Ensure correct JSON or structured output |
| Topic Restriction | Keep chatbot within its purpose |

---

## 4. Practical Example Using Python

```python
from guardrails import Guard

guard = Guard()

result = guard.parse(
    llm_output='{"price": 5000000}',
    output_schema={
        "type": "object",
        "properties": {
            "price": {"type": "number"}
        },
        "required": ["price"]
    }
)

print(result)
```

**Note:** This illustrates the idea of validating structured output. Exact API usage depends on the Guardrails AI version.

---

## 5. Where Is Guardrails AI Useful?

- Real estate AI chatbots
- Healthcare assistants
- Banking chatbots
- Customer support agents
- RAG applications
- Agentic AI and multi-agent systems

---

## 6. Important Differences

| Technology | Purpose |
|---|---|
| LLM | Generates answers |
| Prompt Engineering | Guides the LLM |
| RAG | Retrieves relevant information |
| Guardrails AI | Validates and controls inputs and outputs |

### Remember

Guardrails AI helps make AI applications safer, more reliable and trustworthy.
