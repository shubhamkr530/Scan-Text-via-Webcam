# Scan-Text-via-Webcam
Hello Everyone I have written this code in python.From this code we will be able to scan the text via our own webcam. Let's procced with the code below.



import cv2                   #pip install opencv-python

from PIL import Image        #pip install Pillow

from pytesseract import pytesseract  #pip install pytesseract

camera=cv2.VideoCapture(0)

while True:

    _,image=camera.read()
    
    cv2.imshow('Text detection',image)
    
    if cv2.waitKey(1)& 0xFF==ord('s'):
    
        cv2.imwrite('test1.jpg',image)
        
        break
        
camera.release()

cv2.destroyAllWindows()

def tesseract():

    path_to_terreract=r"C:\Program Files\Tesseract-OCR\tesseract.exe"
    
    image_path='test1.jpg'
    
    text=pytesseract.image_to_string(Image.open(image_path))
    
    print(text[:-1])
    
    tesseract

