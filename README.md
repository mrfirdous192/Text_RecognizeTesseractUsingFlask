# Text_RecognizeTesseract
Image to text Recognization using of Tesseract library
What we'll Use
For this OCR project, we will use the Python-Tesseract, or simply PyTesseract, library which is a wrapper for Google's Tesseract-OCR Engine.

I chose this because it is completely open-source and being developed and maintained by the giant that is Google. Follow these instructions to install Tesseract on your machine, since PyTesseract depends on it.

We will also use the Flask web framework to create our simple OCR server where we can take pictures via the webcam or upload photos for character recognition purposes.

We are also going to use Pipenv since it also handles the virtual-environment setup and requirements management.

Besides those, we'll also use the Pillow library which is a fork of the Python Imaging Library (PIL) to handle the opening and manipulation of images in many formats in Python.

In this post, we'll concentrate on PyTesseract although there are other Python libraries that can help you extract text from images such as:

Textract: which can extract data from PDFs but is a heavy package.
Pyocr: offers more detection options such as sentences, digits, or words.
Setup
Start by installing Pipenv using the following command via Pip (In case you need to set it up, refer to this).

$ pip install pipenv
Create the project directory and initiate the project by running the following command:

$ mkdir ocr_server && cd ocr_server && pipenv install --three
We can now activate our virtual environment and start installing our dependencies:

$ pipenv shell
$ pipenv install pytesseract Pillow 
In case you'll not be using Pipenv, you can always use the Pip and Virtual Environment approach. Follow the official documentation to help you get started with Pip and Virtual Environment:

Note: In that case, instead of pipenv install Pillow, the command will be pip install Pillow.


Flask Web Interface
Our script can be used via the command line, but a Flask application would make it more user-friendly and versatile. For instance, we can upload photos via the website and get the extracted text displayed on the website or we can capture photos via the web camera and perform character recognition on them.

If you are unfamiliar with the Flask framework, this is a good tutorial to get you up to speed and going.

Let's start by installing the Flask package:

$ pipenv install Flask
Now, let's define a basic route:

from flask import Flask
app = Flask(__name__)

@app.route('/')
def home_page():
    return "Hello World!"

if __name__ == '__main__':
    app.run()
