# Mini AI Chatbot Simulator
import random

responses = [
    "Hello! How can I help you today?",
    "Nice to meet you!",
    "I can chat about anything you like.",
    "Tell me more!"
]

while True:
    user_input = input("You: ")
    if user_input.lower() in ["exit", "quit"]:
        print("Chatbot: Goodbye!")
        break
    print("Chatbot:", random.choice(responses))
