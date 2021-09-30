# EC-601-Google-NLP-Sentimental-Analysis-TASK1(b)
from google.cloud import language
import os

def analyze_text_sentiment (text):
  person = language.Languageserviceclient()
  document = language. Language.document(content=text,text_=language.Document.Type.PLAIN_TEXT)
  reply = person.analyze_sentiment(document=document)

  sentiment = reply.document_sentiment
  results =dict(
      text = text,
      score=f"{sentiment.score:.1%}",
      magnitude =f"{sentiment.magnitude:.1%}",
  )
  for k, v in results.items():
    print(f"{k:10}:{v}")

    def analyze_text_entities(text):
      person=language.LanguageServiceClient()
      document= language.Document(content=text, type_=language.Document.Type.PLAIN_TEXT)
      reply = person.analyze_entities(document=document)
      
      for entity in responce.entities:
        print("="*90)
        results = dict(name=entity.name,
                       type=entity.type_.name,
                       salience =f"{entity.salience:.1%}"
        )
        for k,v in results.items():
          print(f"{k:15}:{v}")
  text="Ariana Grande Is a popstar!"
  print(analyze_text_sentiment(text))
  print(analyze_text_entities(text))


