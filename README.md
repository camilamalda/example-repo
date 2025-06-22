# Design a class called Album
# It shoould have the following instance variables:
# album_name, number_of_songs, album_artist

class Album:
    def __init__(self, album_name, number_of_songs, album_artist):
        self.album_name = album_name
        self.number_of_songs = number_of_songs
        self.album_artist = album_artist
# String method to return a string representation of the album
    def __str__(self):
        return f"Album: {self.album_name}, Artist: {self.album_artist}, Songs:{self.number_of_songs}"

    def get_album_info(self):
        return {
            "album_name": self.album_name,
            "number_of_songs": self.number_of_songs,
            "album_artist": self.album_artist
        }

# Create a list called albums1 with 5 Album objects
albums1 = [
    Album("Short n Sweet", 12, "Sabrina Carpenter"),
    Album("Future Nostalgia", 11, "Dua Lipa"),
    Album("Evermore", 15, "Taylor Swift"),
    Album("Kansas Anymore", 10, "ROLE MODEL"),
    Album("Something to Tell You", 10, "HAIM")
]

# Print out the albums1 list
print("Albums List:")
for album in albums1:
    print(album)

# Sort list by number of songs using sorted() function
sorted_albums = sorted(albums1, key=lambda album: album.number_of_songs)

# Print sorted albums
print("Sorted Albums List by Number of Songs:")
for album in sorted_albums:
    print(album)

# Swap elements at index 0 and index 1 
albums1[0], albums1[1] = albums1[1], albums1[0]
# Print the albums1 list after swapping
print("\nAlbums List after Swapping Index 0 and 1:")
for album in albums1:
    print(album)

# Create a second list called album2 with 5 Album objects
album2 = [
    Album("RENAISSANCE", 16, "Beyoncé"),
    Album("PATTERNS", 15, "Kelsea Ballerini"),
    Album("Mañana Será Bonito", 14, "Karol G"),
    Album("Deeper Well", 14, "Kacey Musgraves"),
    Album("Everything to Everyone", 7, "Renée Rapp")
]
# Print out the album2 list
print("\nAlbum2 List:")
for album in album2:
    print(album)

# Copy albums1 to albums2
albums2 = albums1.copy()

# Add two albums to albums2
albums2.append(Album("Dark Side of the Moon", 9, "Pink Floyd"))
albums2.append(Album("OOps!... I Did It Again", 16, "Britney Spears"))

# Sort the albums2 list alphabetically by album name
sorted_albums2 = sorted(albums2, key=lambda album: album.album_name)

# Print sorted albums2
print("\nSorted Albums2 List by Album Name:")
for album in sorted_albums2:
    print(album)


# Search for Dark Side of the Moon in albums2
def search_album(albums, album_name):
    for album in albums:
        if album.album_name == album_name:
            return album
    return None


# Search for the album and print out the index of the album if found
search_result = search_album(albums2, "Dark Side of the Moon")


if search_result:
    index = albums2.index(search_result)
    print(f"\nFound '{search_result.album_name}' at index {index} in albums2.")
else:
    print("\nAlbum not found in albums2.")
