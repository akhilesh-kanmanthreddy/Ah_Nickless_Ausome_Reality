#code input
import pyttsx3
import speech_recognition as sr


r = sr.Recognizer()

print(sr.Microphone.list_microphone_names())

with sr.Microphone() as source2:
  print("quiet")
  r.adjust_for_ambient_noise(source2, duration=2)
  print("speak now")

  audio2 = r.listen(source2)
  MyText = r.recognize_google(audio2)
  MyText = MyText.lower()

  print(MyText)

#code for chatbot
import openai
openai.api_key = "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"
response = openai.Completion.create(
    model="text-davinci-003",
    prompt= "pretend we are in a conversation and you just got hurt by falling down" + MyText,
    temperature=0.3,
    max_tokens=1000,
    top_p=1.0,
    frequency_penalty=0,
    presence_penalty=0,
)

response1 = response['choices'][0]['text']


#for for ai output
#text to speech function
def SpeakText(command):
  engine = pyttsx3.init()
  engine.say(command)
  engine.runAndWait()

SpeakText(response1)
