import speech_recognition as sr

r = sr.Recognizer()

with sr.Microphone() as source:
    print("Speak Anything...")
    r.adjust_for_ambient_noise(source)
    audio = r.listen(source)

try:
    text = r.recognize_google(audio)
except sr.UnknownValueError:
    print("I don't Understand!..")
except sr.RequestError:
    print("Network issue please Resolve it!..")
