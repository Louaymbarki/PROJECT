project/
│
├─ chrome-extension/
│   ├─ manifest.json
│   ├─ index.html
│   ├─ styles.css
│   └─ main.js
│       ├─ function captureAudio(): Captures audio from the online meeting.
│       ├─ function initWebSocket(): Initializes a WebSocket connection with the backend server.
│       ├─ function sendDataToServer(data): Sends captured audio data to the backend server.
│       ├─ function handleServerMessage(message): Handles messages received from the backend server.
│       └─ function updateUI(transcription, speaker, summary): Updates the extension's UI with received data.
│
└─ backend/
    ├─ package.json
    ├─ app.js
    │   ├─ function initExpress(): Sets up the Express server.
    │   ├─ function initWebSocket(): Sets up the WebSocket server.
    │   └─ function main(): Main entry point for the backend server.
    ├─ routes/
    │   └─ google_drive.js
    │       ├─ function authenticateUser(): Authenticates the user with Google Drive using OAuth2.
    │       ├─ function saveTranscriptionToDrive(user, transcription): Saves the transcription to the user's Google Drive.
    │       └─ function saveSummaryToDrive(user, summary): Saves the summary to the user's Google Drive.
    ├─ controllers/
    │   ├─ transcription_controller.js
    │   │   ├─ function transcribeAudio(audioData): Sends audio data to Whisper ASR API for transcription.
    │   │   └─ function storeTranscription(transcription, meetingId, speakerId): Stores the transcription in the database.
    │   ├─ speaker_identification_controller.js
    │   │   ├─ function identifySpeaker(audioData): Identifies the speaker using a machine learning model or third-party API.
    │   │   └─ function storeSpeaker(speaker, meetingId): Stores the speaker in the database.
    │   └─ summarization_controller.js
    │       ├─ function generateSummary(transcriptions): Generates a summary using the OpenAI GPT model.
    │       └─ function storeSummary(summary, meetingId): Stores the summary in the database.
    ├─ models/
    │   ├─ user.js
    │   │   ├─ function createUser(email, googleDriveToken): Creates a new user in the database.
    │   │   └─ function getUserById(id): Retrieves a user from the database by their ID.
    │   ├─ meeting.js
    │   │   ├─ function createMeeting(userId, platform, startTime, endTime): Creates a new meeting in the database.
    │   │   └─ function getMeetingById(id): Retrieves a meeting from the database by its ID.
    │   ├─ speaker.js
    │   │   ├─ function createSpeaker(name, meetingId): Creates a new speaker in the database.
    │   │   └─ function getSpeakerById(id): Retrieves a speaker from the database by their ID.
    │   ├─ transcription.js
    │   │   ├─ function createTranscription(text, startTime, endTime, meetingId, speakerId): Creates a new transcription in the database.
    │   │   └─ function getTranscriptionById(id): Retrieves a transcription from the database by its ID.
    │   └─ summary.js
    │       ├─ function createSummary(text, meetingId): Creates a new summary in the database.
    │       └─ function getSummaryById(id): Retrieves a summary from the database by its ID.
    ├─ config/
    │   └─ database.js
    │       ├─ function connectToDatabase(): Establishes a connection to the PostgreSQL database.
    │       └─ function disconnectFromDatabase(): Closes the connection to the PostgreSQL database.
    └─ utils/
        ├─ whisper_asr.js
        │   ├─ function sendAudioToWhisper(audioData): Sends audio data to the Whisper ASR API for transcription.
        │   └─ function processWhisperResponse(response): Processes the response from the Whisper ASR API.
        └─ openai_gpt.js
            ├─ function sendTranscriptionsToGPT(transcriptions): Sends transcriptions to the OpenAI GPT model for summarization.
            └─ function processGPTResponse(response): Processes the response from the OpenAI GPT model.
"# PROJECT" 
