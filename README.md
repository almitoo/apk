# Survive Game

The Survive Game application was built after reverse engineering the code found in the APK file to reach a state where the application works. 
I used all the relevant components (images, code, etc.) and made changes in the code to make it work.

## Changes Made
To make the game work, the following changes were made:
1. In `Activity_Game`, the line `iArr[i] = Integer.valueOf(String.valueOf(id.charAt(i))).intValue() % 4` was changed to `iArr[i] = Integer.parseInt(String.valueOf(id.charAt(i)))`.
2. In `Activity_Game`, the `Toast` message in the `finishGame()` function was changed from `1` to `Toast.LENGTH_SHORT`.
3. The URL in `res/values/strings.xml` was changed to:
    ```xml
    <string name="url">https://pastebin.com/raw/T67TVJG9</string>
    ```

## How to Play
1. Enter your ID in the provided text field on the menu screen.
2. Press the "Start" button.
3. Follow the sequence of arrow buttons displayed on the game screen:
    - 0: Left
    - 1: Right
    - 2: Up
    - 3: Down
4. If you follow the sequence correctly, you will see a "Survived" message.
5. If you make a mistake, you will see a "You Failed" message.

## Finding the Correct Sequence
To find the correct sequence of arrows based on your ID, follow these steps:
1. Take each digit of your ID.
2. Compute each digit modulo 4 to get a value between 0 and 3.
3. Map each resulting number to a corresponding direction:
    - 0: Left
    - 1: Right
    - 2: Up
    - 3: Down

### Example
If your ID is `322006032`, you should press the buttons in the following order to win:
- Down
- Up
- Up
- Left
- Left
- Up
- Left
- Down
- Up

Using this ID, the city you arrive at is New York.
