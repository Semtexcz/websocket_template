# WebSocket Chat Application

This project demonstrates a simple WebSocket-based chat application using a FastAPI backend and a Vue 3 frontend with Composition API and `script setup` syntax.

## Features

- **Backend**: FastAPI provides WebSocket endpoints for real-time communication.
- **Frontend**: Vue 3 with Composition API for a reactive user interface.
- **Real-time Messaging**: Send and receive messages in real-time through WebSockets.

## Requirements

### Backend Requirements
- Python 3.9+
- `fastapi`
- `uvicorn`

Install dependencies with:
```bash
pip install fastapi uvicorn
```

### Frontend Requirements
- Node.js 14+
- `npm` or `yarn`

Install Vue CLI globally (if not already installed):
```bash
npm install -g @vue/cli
```

## Setup Instructions

### Backend Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Semtexcz/websocket_template
   cd websocket-chat/backend
   ```

2. Start the FastAPI server:
   ```bash
   uvicorn main:app --reload
   ```

3. The backend should now be running at `http://localhost:8000`.

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd ../frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run serve
   ```

4. The frontend should now be running at `http://localhost:8080`.

## How It Works

1. The FastAPI backend hosts a WebSocket endpoint (`/ws`) that handles real-time communication.
2. The Vue 3 frontend connects to the WebSocket endpoint and allows users to send and receive messages in real-time.
3. Messages are displayed in a scrollable container, and users can type new messages into an input field.

## Project Structure

### Backend
- `main.py`: Contains the FastAPI application and WebSocket logic.
- `ConnectionManager`: Manages active WebSocket connections and broadcasting messages.

### Frontend
- `App.vue`: The main Vue component for the application.
- `Composition API`: Used to manage state and lifecycle hooks for WebSocket connections.

## Example Usage

1. Open the application in your browser at `http://localhost:8080`.
2. Type a message in the input box and press Enter or click the "Send" button.
3. Messages will appear in the chat area in real-time.

## Future Enhancements

- User authentication for WebSocket connections.
- Persistent message storage.
- Enhanced UI with additional features like typing indicators and message timestamps.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Enjoy building your real-time WebSocket applications!
