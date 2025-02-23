# cybersecurity.project
   SECURE DATA HIDING IN IMAGES USING STEGANOGRAPHY{SECURE THE DATA TO PREVENT HACKERS.]
import cv2# download pip install opencv-python using cmd
import os
import string

img = cv2.imread("C:/Users/admin/Downloads/projjj/mypic.jpg.jpeg") # Replaced with the correct image path and use this / only 

msg = input("Enter secret message:")
password = input("Enter a passcode:")

d = {}
c = {}

for i in range(255):
    d[chr(i)] = i
    c[i] = chr(i)

m = 0
n = 0
z = 0

for i in range(len(msg)):
    img[n, m, z] = d[msg[i]]
    n = n + 1
    m = m + 1
    z = (z + 1) % 3

cv2.imwrite("encryptedImage.jpg", img)
os.system("start encryptedImage.jpg")  # Use 'start' to open the image on Windows

message = ""
n = 0
m = 0
z = 0

pas = input("Enter passcode for Decryption")
if password == pas:
    for i in range(len(msg)):
        message = message + c[img[n, m, z]]
        n = n + 1
        m = m + 1
        z = (z + 1) % 3
    print("Decryption message:", message)
else:
    print("YOU ARE NOT auth")
![encryptedImage](https://github.com/user-attachments/assets/f5ee5c2c-ac39-417b-b7ae-0d8be0c3045d)
![mypic jpg](https://github.com/user-attachments/assets/7b6e76d4-8132-43ce-a5a5-5f2de03f4285)
