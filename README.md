import random
# Simple memory
memory = {}

def remember(key, value):
    memory[key] = value
    return f"Okay bro, I will remember your {key}!"

def recall(key):
    return memory.get(key, "I don't remember that yet bro!")

def get_response(user_input):
    user_input = user_input.lower()

    def get_response(user_input):
    user_input = user_input.lower()

    # Memory feature
    if "my name is" in user_input:
        name = user_input.replace("my name is", "").strip()
        return remember("name", name)

    if "what is my name" in user_input:
        return recall("name")

    # Keyword responses
    keywords = {
        "hello": ["Hey! How can I help you today?", "Hello! What's up?", "Hi there!"],
        "love": ["Love is beautiful bro!", "Treat people with kindness!"],
        "job": ["Keep learning bro, internship is coming!", "You will succeed soon!"],
        "bye": ["Take care!", "Goodbye!", "Catch you soon!"]
    }

    for key in keywords:
        if key in user_input:
            return random.choice(keywords[key])

    return random.choice([
        "That's interesting! Tell me more.",
        "Hmm… I'm still learning bro!",
        "Nice! What else do you want to talk about?"
    ])
print("🤖 Bharath AI Chatbot (type 'exit' to stop')")
while True:
    user_message = input("You: ")
    if user_message.lower() == "exit":
        break
    print("AI:", get_response(user_message))
