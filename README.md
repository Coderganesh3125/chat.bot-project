# chat.bot-project#training a chat bot model
#importing necessary modules
import random
from nltk.chat.util import Chat,reflections

#define patterns and responses for chatbot.....
patterns=[
    (r'hi|hello|hii|hai',['hello there!..','hay there what can i do for you..','hello','hii how can i assist you']),
    (r'who are you|tell me about you|you?',['i am chat bot crated by siet engineering student','i will be give some info try...to type something',
                                            'i can giveany kind of information']),
    (r'what is python?|python?|tell me about python',['it is a general purpose programming language','it is dynamic language','it is high level language']),
    (r'(.*)',['I\'m unable to understand..','please rephrase that..','sorry..i didn\t']),
]
#train the model with patterns and reflections
chatbot=Chat(patterns,reflections)

#creat a function to interact with chat bot
def chat():
  print('welcome to chatbot..type quit to exit...')
  while True:
    user_input=input('you:')
    if user_input.lower()=='quit':
      print('good bye...')
      break
    else:
      response=chatbot.respond(user_input)
      print('chat bot',response)
chat()


