# Adventure Capitalist Automation Bot

This project automates the popular strategy game *Adventure Capitalist* by using image recognition and input automation to manage your investments, upgrades, and resets efficiently.

## Features

- Automatically identifies and buys the best investments, upgrades, and managers.
- Manages cash upgrades, angel upgrades, and investor resets.
- Uses `pyautogui` for GUI automation, `pytesseract` for OCR (optical character recognition), and `OpenCV` for image processing.
- Recommends optimal upgrades based on real-time game state.
- Efficiently handles various game mechanics including discounts from managers.

## Prerequisites

Ensure that you have the following libraries installed:

```bash
pip install pyautogui pytesseract opencv-python keyboard imutils numpy
```

Additionally, download and install [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) and ensure it is properly configured on your machine.

## Setup

1. Install Tesseract and set up the correct path in the script by modifying the line:

```python
pytesseract.pytesseract.tesseract_cmd = r'C:\Program Files\Tesseract-OCR\tesseract'
```

2. Run the script using Python.

```bash
python adventure_capitalist_bot.py
```

## How It Works

1. **Image Recognition**: The bot uses screenshots of the game to detect in-game elements such as money, investments, and upgrades. `pytesseract` is used to extract numerical values, and `OpenCV` is used to process images.
  
2. **Automation**: The bot clicks on the appropriate areas on the screen using `pyautogui` to make upgrades, buy managers, and reset investors.

3. **Investment Strategy**: The bot calculates the most efficient upgrade or purchase based on the current game state, considering profit, speed, and angel investors.

4. **Angel Management**: Automatically calculates the best time to reset and collects angels.

## Configuration

- The script is pre-configured to run on **Earth** in *Adventure Capitalist*.
- You can tweak the following parameters:
  - `has1n10`: A flag to check if a specific purchase strategy is active.
  - `cash`: Toggles cash upgrades.
  - `quikBuy`: Enables quicker purchases.

## Usage

1. Start the game and run the bot.
2. Press `p` to print the current cursor location (useful for tweaking the bot's interaction with the game UI).
3. The bot will automatically detect and recommend upgrades and investments.

## Key Functions

- **`checkCurrentState()`**: Captures the current state of the game by taking a screenshot and analyzing the investments and money.
- **`buyUpgrade()`**: Buys upgrades for specific investments.
- **`restart()`**: Resets the game, collects angels, and starts from the beginning with a higher angel bonus.
- **`calcRecomendations()`**: Calculates the best investment strategy at any given moment.
- **`buySafeAngel()`**: Purchases angel upgrades safely without overspending angels.

## Future Enhancements

- Expand support for other planets in the game.
- Add more dynamic decision-making strategies based on changing game conditions.

## Contributing

Feel free to contribute to this project! Fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License.

---

Enjoy automating your Adventure Capitalist journey!
