import streamlit as st
import speech_recognition as sr
import pyttsx3
import datetime
import pyjokes
import os
import webbrowser

# Initialize the speech recognition engine
r = sr.Recognizer()

# Initialize the text-to-speech engine
engine = pyttsx3.init()

# Define a function to listen to voice input
def listen():
    with sr.Microphone() as source:
        print("Listening...")
        audio = r.listen(source)
        try:
            # Use Google's speech recognition API to transcribe the audio
            text = r.recognize_google(audio)
            print("You said:", text)
            return text
        except sr.UnknownValueError:
            print("Sorry, I didn't understand that.")
            return None

# Define a function to respond to voice input
def respond(text):
    if text is None:
        return
    # Add your custom responses here
    if "hello" in text.lower():
        engine.say("Hello! How can I assist you today?")
    elif "what is your name" in text.lower():
        engine.say("My name is AI Voice Bot.")
    elif "what is the time" in text.lower():
        now = datetime.datetime.now()
        engine.say("The current time is " + now.strftime("%H:%M:%S"))
    elif "tell me a joke" in text.lower():
        joke = pyjokes.get_joke()
        engine.say(joke)
    elif "exit" in text.lower():
        engine.say("Goodbye!")
        exit()
    elif "how are you" in text.lower():
        engine.say("I'm doing well, thank you for asking!")
    elif "what can you do" in text.lower():
        engine.say("I can perform various tasks, such as telling jokes, providing information, and more!")
    elif "open youtube" in text.lower():
        engine.say("Opening YouTube...")
        webbrowser.open("https://www.youtube.com")
    elif "open whatsapp" in text.lower():
        engine.say("Opening WhatsApp...")
        os.system("start whatsapp:")
    elif "open google chrome" in text.lower():
        engine.say("Opening Google Chrome...")
        os.system("start chrome")
    elif "open mozilla firefox" in text.lower():
        engine.say("Opening Mozilla Firefox...")
        os.system("start firefox")
    else:
        engine.say("Sorry, I didn't understand that.")
    engine.runAndWait()

# Main loop
while True:
    text = listen()
    respond(text)