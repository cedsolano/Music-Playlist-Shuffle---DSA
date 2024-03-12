Music Playlist Shuffle:

● Create a playlist of songs using arrays or lists.

● Implement a random shuffle algorithm to reorder the playlist.

● Use a counter to track the number of shuffles and displays it upon request.

import random

import os

import time

class MusicPlaylist:
def __init__(self):
# Initialize an instance of the MusicPlaylist class with an empty playlist,
# shuffle counter set to zero, and a flag to indicate if the playlist is shuffled.
self.playlist = []

self.shuffle_counter = 0

self.is_shuffled = False

def add_song(self, song):
# to add a song to the playlist

if song.strip(): # Check if the song name is not blank

self.playlist.append(song)

else:

print("Invalid Input!")

def delete_song(self, song):

# to delete a song from the playlist

if song in self.playlist:

# If the song is found in the playlist, remove it and display a message.

self.playlist.remove(song)
print(f"{song} has been removed from the playlist.")

else:

# If the song is not in the playlist, display a message.

print(f"{song} is not in the playlist.")

time.sleep(2.5) # Introduce a 2.5-second delay

clear_terminal() # Clear the terminal screen after deletion.

def shuffle_playlist(self):

# to shuffle the playlist

if not self.playlist:

# If the playlist is empty, inform the user and clear the terminal.

print("Cannot shuffle an empty playlist. Add songs first.")

time.sleep(2.5) # Introduce a 2.5-second delay

clear_terminal()

else:

# If the playlist is not empty, shuffle it using

random.shuffle.

random.shuffle(self.playlist)

self.shuffle_counter += 1

self.is_shuffled = True

# Display a success message, introduce a delay, and clear the terminal.

print("The playlist has been successfully shuffled!")

time.sleep(2.5) # Introduce a 2.5-second delay

clear_terminal()

def display_playlist(self):

# to display the current playlist

if not self.playlist:

# If the playlist is empty, inform the user, introduce adelay, and clear the terminal.

print("The playlist is empty.")

time.sleep(2.5) # Introduce a 2.5-second delay

clear_terminal()

else:

# If the playlist is not empty, display each song with its index.

print("Current Playlist:")

for i, song in enumerate(self.playlist, start=1):

print(f"{i}. {song}")

print() # Print an extra line for better readability.

def display_shuffle_counter(self):

# to display the number of shuffles

print(f"Number of shuffles: {self.shuffle_counter}")

def clear_terminal():

# Function to clear the terminal screen based on the operating system.

if os.name == 'nt': # For Windows

os.system('cls')

else: # For Unix-like systems (Linux, macOS)

os.system('clear')

if __name__ == "__main__":

# Instantiate the MusicPlaylist class

playlist = MusicPlaylist()

while True:

# Display the menu options to the user

print("|----------------------------|")

print("| 1. Add Song |")

print("| 2. Delete Song |")

print("| 3. Shuffle Playlist |")

print("| 4. Display Playlist |")

print("| 5. Display Shuffle Counter |")

print("| 6. Exit |")

print("|----------------------------|")

# Prompt the user for their choice

choice = input("Enter your choice: ")

print("__________________________________________")

# Process the user's choice

if choice == "1":

# Allow the user to add songs until they enter '0' to stop

while True:

song_name = input("Enter the song name type 0 to stop: ")

if song_name.lower() == "0":

break

playlist.add_song(song_name)

# Display a message and clear the terminal after adding songs.

print("Songs have been added to the playlist.")

time.sleep(2.5) # Introduce a 2.5-second delay

clear_terminal()

elif choice == "2":

# Prompt the user to enter the song name to delete and perform the deletion.

song_to_delete = input("Enter the song name to delete: ")

playlist.delete_song(song_to_delete)

elif choice == "3":

# Shuffle the playlist, display it if not empty, and clear the terminal.

playlist.shuffle_playlist()

if playlist.playlist:

playlist.display_playlist()

elif choice == "4":

# Display the current playlist.

playlist.display_playlist()

elif choice == "5":

# Display the number of shuffles.

playlist.display_shuffle_counter()

elif choice == "6":

# Exit the program.

break

else:

# Inform the user if an invalid choice is entered.

print("Invalid choice")
