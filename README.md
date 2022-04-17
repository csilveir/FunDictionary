# Fun Dictionary
#### Video Demo:  https://www.youtube.com/watch?v=yCetOMSFvGQ
#### Description:

This app is a website that searches an English dictionary for words contained in images. After sending an image with a word, the system will identify the letters contained in that image and look up the meaning
of this word in the dictionary.
After consulting the meaning of that word in the dictionary, the system will give the user the option of playing an audio with the meaning of the searched word, as well as viewing some images related to the word itself.
In addition to searching a page, there are APIs for reading the camera image by the mobile device, where it is also possible to interact with the meaning of the word, audios and images.
In this project we used the Flask for Python, gTTS - Google Text-to-Speech libraries for audio to text conversion, pytesseract for optical character recognition (OCR) and reading of texts within the image, PIL
for image manipulation, icrawler for searching google images, requests library for searching online dictionary API's, sqlite for persistence of dictionary searches.
In the application there is the audio folder, where the .mp3 files with the meaning of the searched word are saved, as well as in the images folder, a folder with the name of the word is created and inside that all the images corresponding
to that word are created. the next searches having a local cache of the contents and optimizing the performance.

Project structure

dicionario-controller.py - It contains the APIs to POST the form with the images, as well as the api's to recover the audio and video files after a search has been carried out and the files have been saved in the application.It contains the APIs to POST the form with the images, as well as the APIs to retrieve the audio and video files after performing a search and the persistence of the files in the application.
Acts as a proxy pattern in the database component for word search and persistence,
It acts as a proxy pattern in the database component of sqllite for word lookups and persistence by the database.py component as well as for online dictionary lookups using HTTP requests through the dicionario.py component
Image searches are also orchestrated by this controller through the image_search.py component as well as the interaction
with the audio files generated through the audio.py component.

audio.py - Component that has an interface to Google Translates text-to-speech API, after generating the audio file it is persisted in a directory with the name of the search word.

config.py - Component that has application variables, as well as reading environment variables.

database.py - Orchestrates the search and insert calls to the sqlite database that is in the dicionarios.db file

dicionario.py - Uses the requests library to make HTTP/JSON calls in external API's of online dictionaries.

dicionario.sql - Database Object Creation DDL.

image_to_text.py - It uses the library and core of pytesseract to read OCR the texts inside the image.

image_search.py - It uses the crawler library to search images on Google's domain and after finding the images, save them in the application for later cache and increased performance.

palavra.py - Represents the Word class with its meaning attributes and links to the audio and image file.