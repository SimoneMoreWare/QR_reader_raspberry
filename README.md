# QR_reader_raspberry
Come realizzare un lettore di codici QR con Raspberry Pi

In questo articolo vedremo come realizzare un lettore di codici QR con Raspberry Pi.

Il QR Code è una versione bidimensionale del codice a barre, composto da pattern di pixel in bianco e nero. Denso Wave appartiene a Denso, una fornitrice di Toyota, e ha sviluppato i QR Code per l’identificazione dei componenti al fine di accelerare i processi logistici della sua produzione automobilistica. Ora, con l’uso diffuso degli smartphone, il QR Code ha trovato la sua strada nel mercato. “QR” sta per “Quick Response”, che si riferisce all’accesso istantaneo alle informazioni nascoste nel Code (codice).

Per chi vuole conoscere i fondamenti matematici dietro il QR Code può leggere questo articolo.

I materiali da utilizzare sono i seguenti:

Raspberry Pi
Pi camera (o webcam usb)
Tastiera
Mouse
Monitor

![alt text](https://i0.wp.com/www.moreware.org/wp/wp-content/uploads/2021/11/raspberry-pi-qr-code-reader-featured-image.jpg?w=820&ssl=1)

INSTALLAZIONI PRELIMINARI

Dobbiamo sapere che esiste un pacchetto chiamato “qrcode” che permette agli utenti di codificare rapidamente i dati all’interno di un QR code ed estrapolare ciò che è contenuto all’interno.

Apri il terminale.

Per sicurezza effettuiamo un update:

sudo apt-get update
1
sudo apt-get update
Digitiamo il seguente comando:

pip3 install qrcode[pil]
1
pip3 install qrcode[pil]
INSTALLAZIONE RASPBERRY PI CAMERA

Ho scritto una guida approfondita a riguardo, per leggerla potete utilizzare il seguente link: Come installare e configurare la Raspberry Pi Camera

Installiamo OpenCV

OpenCV è una libreria open-source, scritta in C, per lo streaming video real-time, ovvero la Computer Vision e gira sotto Windows, Linux e MacOS X.

La libreria permette una semplice gestione di immagini trattandole come “matrici di pixel“, alle quali è possibile accedervi in maniera molto semplice e rapida. Prima di cimentarci nella vera e propria Computer Vision, che è un ambito di una vastità non indifferente, diamo una sguardo a quella che si può definire l’Image Processing, cioè l’Elaborazione delle Immagini attraverso la libreria in questione.

`sudo apt-get install python3-opencv`

Poi digita:

`sudo apt-get install libqt4-test python3-sip python3-pyqt5 libqtgui4 libjasper-dev libatlas-base-dev -y`

Poi digita:

`pip3 install opencv-contrib-python==4.1.0.25`

Questo comando ti permette di utilizzare la picamera con OpenCV VideoCapture

`sudo modprobe bcm2835-v4l2`

Per verificare se l’installazione è andata a buon fine digita:

`python3
import cv2`

CODICE PYTHON

Il codice funziona nella seguente maniera:

Configura la fotocamera
rileva i codici qr
legge i codici qr ed estrapola ciò che è contenuto all’interno-
Se è presente qualcosa viene disegnato un riquadro attorno al codice QR e viene visualizzato ciò che è contenuto all’interno
Finchè non viene premuto il tasto ‘q’ lo script viene eseguito.
Il programma mostra anche il frame per secondo della camera mentre registra.

[Codice](https://github.com/SimoneMoreWare/QR_reader_raspberry/blob/main/qr.py)

Video

https://www.youtube.com/watch?v=i9yRnnJydQw
