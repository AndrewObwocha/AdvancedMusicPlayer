# Advanced Music Queue CLI (Doubly Linked List Implementation)

## Overview

This Python project implements a command-line interface (CLI) for managing a music queue, simulating functionalities like adding songs, navigating back and forth, and removing the current song. It uses the `ytmusicapi` library to search for songs on YouTube Music.

The key feature of this "advanced" version is its use of a custom **Doubly Linked List (`DLinkedList`)** data structure (defined in `structures.py`) to manage the queue. This allows for more flexible operations compared to a standard queue, such as bidirectional navigation (previous/next) and efficient insertion/removal at the current position.

## Features

*   **Song Search:** Search for songs on YouTube Music via `ytmusicapi`.
*   **Add Songs:**
    *   Add a song immediately *after* the currently playing song (`Add Next`).
    *   Add a song to the very *end* of the queue (`Add to the End`).
*   **Navigation:**
    *   Move to the *next* song in the queue (`Next Song`).
    *   Move to the *previous* song in the queue (`Previous Song`).
*   **Remove Current:** Remove the currently selected song from the queue.
*   **Display Queue:** Show the current list of songs, total duration, and highlight the currently playing song.
*   **Clear Queue:** Empty the entire music queue.
*   **Command-Line Interface:** Simple menu-driven interaction.
*   **Data Structures:** Implements `Song`, `DLinkedListNode`, and `DLinkedList` classes.

## How it Works

The `DLinkedList` manages the queue. Each song is stored in a `DLinkedListNode`, which holds pointers to both the `next` and `previous` nodes in the list. A `__current` pointer tracks the currently selected/playing song.

*   **Navigation (Prev/Next):** Simply moves the `__current` pointer along the `next` or `previous` links.
*   **Add Next:** Creates a new node and inserts it between the `__current` node and `__current.next`, updating pointers accordingly.
*   **Add Last:** Appends a new node to the end (`__tail`) of the list.
*   **Remove Current:** Updates the `next` pointer of the previous node and the `previous` pointer of the next node to bypass the `__current` node, effectively removing it. Handles edge cases (removing head/tail/only element).

## Requirements

*   Python 3.x
*   `ytmusicapi` library (`pip install ytmusicapi`)
*   The `structures.py` file must be in the same directory as `advanced_music_queue.py`.

## Usage

1.  **Install Library:** If you haven't already, install `ytmusicapi`:
    ```bash
    pip install ytmusicapi
    # or pip3 install ytmusicapi
    ```
2.  **Ensure files are together:** Place `advanced_music_queue.py` and `structures.py` in the same directory.
3.  **Navigate:** Open your terminal or command prompt and navigate to that directory.
4.  **Run the script:**
    ```bash
    python advanced_music_queue.py
    # or python3 advanced_music_queue.py
    ```
5.  **Interact:** Follow the on-screen prompts using the menu:
    *   `1. Add Song`: Search and add songs (choose 'Add Next' or 'Add to the End').
    *   `2. Next Song`: Move to the next song.
    *   `3. Previous Song`: Move to the previous song.
    *   `4. Remove Current Song`: Delete the currently highlighted song.
    *   `5. Show Queue`: Display the list of songs.
    *   `6. Clear Queue`: Remove all songs.
    *   `7. Quit`: Exit the application.

## File Structure

*   `advanced_music_queue.py`: Contains the main application logic, user interface, and interaction with `ytmusicapi`.
*   `structures.py`: Defines the `Song`, `DLinkedListNode`, and `DLinkedList` classes, plus time conversion helpers.

## License

MIT License

## Author

Andrew Obwocha
