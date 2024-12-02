# Spot the Difference Game
## Description
This is a **"Spot the Difference"** game built using **HTML**, **CSS**, and **JavaScript**. The game displays two images side-by-side, where players must identify differences between the two by clicking on them. Each difference is highlighted upon selection, and the game keeps track of the player's score and time.

### Features:
- **Dynamic Image Loading**: Images and their differences are configurable via a JSON file, making it easy to change the game content.
- **Difference Highlighting**: Players click on the areas with differences, which are visually marked when clicked.
- **Timer**: The game tracks the time taken to find all differences.
- **Responsive**: The game layout adapts to both desktop and mobile devices.
- **Score Tracking**: Players can see their progress in real-time as they find the differences.

---

## Approach

### 1. **JSON-Based Configuration**:
The core functionality of this game relies on a JSON file (`gameData.json`), which defines:
- Paths to the two images.
- Coordinates or bounding boxes for each difference.

This makes it easy to update or swap images, or add/remove differences without modifying the code.

### Example JSON Structure:
```json
{
  "gameTitle": "Spot the Difference - Animals",
  "images": {
    "image1": "path/to/image1.jpg",
    "image2": "path/to/image2.jpg"
  },
  "differences": [
    { "x": 100, "y": 200, "width": 50, "height": 50 },
    { "x": 300, "y": 150, "width": 40, "height": 40 },
    { "x": 500, "y": 300, "width": 30, "height": 30 }
  ]
}
```

- The `gameTitle` provides the game’s name.
- The `images` section holds the paths for both images.
- The `differences` section contains an array of objects that define each difference by its coordinates (`x`, `y`), width, and height.

### 2. **Game Logic**:
- **Image Rendering**: Two images are displayed side by side, and the differences are rendered as invisible clickable areas (bounding boxes) on both images.
- **Difference Checking**: When a player clicks a difference, the area turns green, indicating that it's been found. The player's score is updated, and once all differences are found, the game shows a success message.
- **Timer**: A timer tracks how long it takes for the player to find all the differences. The time is displayed in seconds.

### 3. **User Interaction**:
- Players click on highlighted areas on the images to spot the differences.
- Once all differences are identified, a success message is displayed, showing the player’s time.

### 4. **Responsive Design**:
The game layout adjusts to various screen sizes, ensuring a smooth experience on both desktop and mobile devices.

---

## Installation

### Prerequisites:
To run this game, you’ll need:
- A modern web browser (Chrome, Firefox, etc.)
- Local or remote server setup to serve the files if needed (for example, using Live Server in VSCode)

### Steps to Run Locally:

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/spot-the-difference-game.git
   ```
   
2. Navigate to the project folder:
   ```bash
   cd spot-the-difference-game
   ```

3. Open the `index.html` file in your browser to play the game.

   **Optional**: If you're using VSCode, you can install the "Live Server" extension to view the game dynamically.

## How to Update the Game

### 1. **Change the Images**:
Simply update the `image1` and `image2` fields in the `gameData.json` file with new paths to the images you want to use.

### 2. **Add or Remove Differences**:
To add or remove differences:
- Modify the `differences` array in the json file.
- Each difference should include its `x`, `y` position, as well as `width` and `height`.

For example:
```json
{
  "x": 200,
  "y": 300,
  "width": 40,
  "height": 40
}
```

### 3. **Game Title**:
You can change the title of the game by modifying the `gameTitle` field in the `gameData.json`.

---

## Bonus Features

- **Sound Effects**: Add sound effects for correct and incorrect clicks by modifying the JavaScript file (`script.js`).
- **Animations**: You can use CSS animations or JavaScript to enhance user interactions (e.g., adding a fade effect for found differences).

