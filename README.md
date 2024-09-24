# Tic Tac Toe Web Application

This is a simple web-based Tic Tac Toe game that allows users to play in either light or dark theme mode. The application includes an iOS-like theme switcher that saves the user's theme preference (light or dark) across sessions using browser `localStorage`.

## Features

- Classic Tic Tac Toe gameplay.
- Light and dark theme modes, easily switchable with an iOS-style slider located at the top-right of the screen.
- Theme preference is remembered between sessions.
- Responsive design with rounded corners for the board and individual cells.
- Flask server included to host the application locally.

## Technologies Used

- **HTML/CSS/JavaScript**: Front-end and game logic.
- **Flask (Python)**: Backend to serve the static files.

## File Structure

```
tic-tac-toe-web-app/
│
├── index.html      # Main HTML file for the Tic Tac Toe game
├── styles.css      # CSS file containing styles
├── script.js       # JavaScript file with game logic and theme switcher
├── app.py          # Flask-based Python server
└── README.md       # Project README
```

## Installation

### Prerequisites

- Python 3.x
- Flask library (You can install Flask using pip):

  ```bash
  pip install flask
  ```

### Running the Project

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/mqyeung/tictactoe.git
   cd tictactoe
   ```

2. Run the Python Flask server:

   ```bash
   python app.py
   ```

3. Open your browser and navigate to:

   ```
   http://localhost:5000
   ```

   The Tic Tac Toe web application will now be running, and you can play the game.

## Customization

You can customize the appearance or behavior of the game by editing the following files:

- **Game Logic**: Modify `script.js` to adjust game mechanics or add new features.
- **Styling**: Modify `styles.css` to change the layout, colors, or overall appearance.

## Flask Server Configuration

The project includes a basic Flask server (`app.py`) that serves the Tic Tac Toe game. The server will run on `localhost` by default, but you can change the host and port in the `app.py` file as needed.

- **app.py** content:

  ```python
  from flask import Flask

  app = Flask(__name__, static_folder='.', static_url_path='')

  @app.route('/')
  def index():
      return app.send_static_file('index.html')

  if __name__ == '__main__':
      app.run(debug=True, host='0.0.0.0', port=5000)
  ```

### Explanation:

- The Flask app serves the `index.html` file and other static assets (CSS, JS).
- The app runs in debug mode on port `5000`. You can access it at `http://localhost:5000`.

### Port Forwarding (Optional)

If you want to make your application accessible from outside your local network, configure port forwarding on your router for port `5000` to point to your machine’s IP.

## License

This project is licensed under the MIT License - see the LICENSE file for details.