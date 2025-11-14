import random

def get_response(user_input):
    user_input = user_input.lower()

    keywords = {
        "hello": ["Hey! How can I help you today?", "Hello! What's up?", "Hi there!"],
        "name": ["I'm a mini AI chatbot created by Bharath!", "You can call me Bharath-AI."],
        "love": ["Love is beautiful, bro!", "Treat people with kindness!"],
        "job": ["Keep learning, bro. You will get an internship soon!", "Your future is bright!"],
        "bye": ["Take care!", "Goodbye!", "See you soon!"]
    }

    for key in keywords:
        if key in user_input:
            return random.choice(keywords[key])

    return random.choice([
        "That's interesting! Tell me more.",
        "I’m not sure, but I’m learning every day!",
        "Nice! What else do you want to talk about?"
    ])

print("🤖 Bharath AI Chatbot (type 'exit' to stop)")
while True:
    user_message = input("You: ")
    if user_message.lower() == "exit":
        break
    print("AI:", get_response(user_message))
