# Talk at Brighton Web Development MeetUp OCT2025

Make a `.env` copy of `,env.local` and add your keys there.

An OpenAI is needed. A free API KEY is available with Groq and one can use the same api call but with this code:

from openai import OpenAI

# Initialize Groq client using OpenAI library
client = OpenAI(
    api_key="your-groq-api-key",
    base_url="https://api.groq.com/openai/v1"
)

# Make a completion request
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",  # or other Groq models
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Hello, how are you?"}
    ],
    temperature=0.7,
    max_tokens=1000
)

print(response.choices[0].message.content)