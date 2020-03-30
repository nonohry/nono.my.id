---
title: Aplikasi Sederhana Speech to Text menggunakan Speech Recognition pada Python
key: 20200330
tags: Python
---
Ini merupakan tutorial singkat bagaimana caranya membuat aplikasi sederhana *speech to text* menggunakan Python[^1].
<!--more-->

![Image STT](/assets/images/posts/stt.png)

langsung saja, berikut kodenya:
```python
import speech_recognition as sr

r = sr.Recognizer() 

with sr.Microphone() as source:
    print('Speak Anything : ')
    audio = r.listen(source)

    try:
        text = r.recognize_google(audio)
        print('You said: {}'.format(text))
    except:
        print('Sorry could not hear')
```

Penjelasan: 
- Line 1: Kita mengimpor module speech_recognition sebagai sr
- Line 3: Kita asumsikan objek Recognizer ke r
- Line 5-7: Kita gunakan objek Mikrofon untuk mendengarkan audio
- Line 9-13: Kita gunakan try-catch untuk mengubah audio menjadi teks

Referensi:
- [^1]: Yadav, A. (n.d.). Simple Speech to Text Converter Using Speech Recognization in Python. Retrieved from https://www.codementor.io/@avnishyadav/simple-speech-to-text-converter-using-speech-recognization-in-python-14th9dd04k