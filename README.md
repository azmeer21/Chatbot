# Chatbot
import openai

openai.api_key = 

def chatbot(message):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",  # Use gpt-4 if you have access
        messages=[
            {"role": "system", "content": "You are a customer support and marketing assistant."},
            {"role": "user", "content": message},
        ]
    )
    return response['choices'][0]['message']['content']

# Example usage
user_input = input("You: ")
reply = chatbot(user_input)
print("Chatbot:", reply)
