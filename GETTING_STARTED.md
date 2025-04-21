# Getting Started with DuckDB-DOOM

This guide will help you get up and running with DuckDB-DOOM.

## Prerequisites

You only need a modern web browser that supports WebAssembly, such as:

- Chrome/Chromium (version 74+)
- Firefox (version 67+)
- Safari (version 14.1+)
- Edge (version 79+)

No server, compiler, or additional dependencies are required!

## Running the Game

### Option 1: Run Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/patricktrainer/duckdb-doom.git
   ```

2. Navigate to the project directory:
   ```bash
   cd duckdb-doom
   ```

3. Open `index.html` in your web browser:
   - Drag and drop the file into your browser
   - Or use the "File > Open File" menu in your browser
   - Or double-click the file in your file explorer

### Option 2: Using a Local Server (optional, but recommended)

If you experience any issues with WebAssembly loading, you might need to serve the files from a local HTTP server:

#### Using Python (if installed)

```bash
# Python 3
python -m http.server

# Python 2
python -m SimpleHTTPServer
```

Then open http://localhost:8000 in your browser.

#### Using Node.js (if installed)

```bash
# Install http-server globally if you haven't already
npm install -g http-server

# Run the server
http-server
```

Then open http://localhost:8080 in your browser.

## Game Controls

- **W**: Move forward
- **S**: Move backward
- **A**: Turn left
- **D**: Turn right
- **Spacebar**: Shoot
- **L**: Toggle verbose logging (to browser console)

## Tips for Playing

1. **Performance**: The game uses SQL for all logic, so it may run slowly on some devices. If performance is poor, try:
   - Reducing the browser window size
   - Closing other tabs and applications
   - Using Chrome or Firefox for best WebAssembly performance

2. **Debugging**: If you encounter any issues:
   - Press L to enable verbose logging
   - Open your browser's developer console (F12 or Ctrl+Shift+I) to see logs
   - Check if there are any error messages

3. **Gameplay**: Hunt down all the enemies (marked as 'E' on the minimap) to clear the level!

## Next Steps

After you've played the game, consider:

- Exploring the SQL code to understand how it works
- Modifying the map layout in the `initSql` variable
- Adding new features or enhancing existing ones
- Contributing to the project (see [CONTRIBUTING.md](CONTRIBUTING.md))

Enjoy playing and experimenting with DuckDB-DOOM!