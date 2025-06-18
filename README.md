import tkinter as tk
from tkinter import filedialog
from tkinter import messagebox

# Function to open file dialog
def open_file():
    file_path = filedialog.askopenfilename(title="Select a File")
    if file_path:
        label.config(text=f"Selected File: {file_path}")

# Function to open folder dialog
def open_folder():
    folder_path = filedialog.askdirectory(title="Select a Folder")
    if folder_path:
        label.config(text=f"Selected Folder: {folder_path}")

# Function to display message
def show_info():
    messagebox.showinfo("File Explorer", "Explore and select files or folders!")

# Setting up main window
root = tk.Tk()
root.title("File Explorer")
root.geometry("500x300")

# Title Label
title_label = tk.Label(root, text="File Explorer", font=("Helvetica", 16, "bold"))
title_label.pack(pady=10)

# Info Button
info_button = tk.Button(root, text="Info", command=show_info)
info_button.pack(pady=5)

# Buttons for File and Folder Explorer
file_button = tk.Button(root, text="Open File", command=open_file)
file_button.pack(pady=5)

folder_button = tk.Button(root, text="Open Folder", command=open_folder)
folder_button.pack(pady=5)

# Label to show the selected path
label = tk.Label(root, text="No file or folder selected.", wraplength=450)
label.pack(pady=20)

# Run the application
root.mainloop()# File-explorer-gui-
