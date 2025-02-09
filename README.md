import tkinter as tk
from tkinter import filedialog
from PIL import Image, ImageTk

def open_image():
    file_path = filedialog.askopenfilename(filetypes=[("Image Files", ".png;.jpg;.jpeg;.gif;*.bmp")])
    if file_path:
        img = Image.open(file_path)
        img = img.resize((400, 400), Image.LANCZOS)
        img_tk = ImageTk.PhotoImage(img)
        label.config(image=img_tk)
        label.image = img_tk

# Create the main window
root = tk.Tk()
root.title("Image Viewer")
root.geometry("500x500")

# Create a button to open images
btn = tk.Button(root, text="Open Image", command=open_image)
btn.pack(pady=20)

# Create a label to display images
label = tk.Label(root)
label.pack()

# Run the application
root.mainloop()# iamge-viewer-using-tkinter
