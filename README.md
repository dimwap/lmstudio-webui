⚠️ This is an **unofficial** project and is **not affiliated with or endorsed by LM Studio**.

# LM Studio Chat WebUI(unofficial)

This is a simple, browser-based chat interface for interacting with your LM Studio server. It allows you to connect to your locally hosted LM Studio model and chat with it from any device with a web browser, including mobile phones.

## Features

- Dark mode interface
- Connect to any LM Studio server
- Chat with your LM Studio model
- LaTeX Math Rendering and Markdown Rendering
- Mobile-friendly design
- Super Cool new Purple theme **NEW**
- Chats **NEW**
- Vision Model Support **NEW**
- Choose your model **NEW**
- Delete Chats **NEW**


![image](https://github.com/user-attachments/assets/d7cba468-166b-4d74-a98a-37ca72093b83)




## Setup Instructions

### For Desktop Users

1. Download the `lmstudiowebui.html` file from this repository.
2. Save it to a location on your computer that you can easily access.

### For Mobile Users
This works out of the box on Android devices. For iOS you need to open the file in Microsoft Edge or another browser. Safari/Chrome do not work. 
There are several ways to get the `lmstudiowebui.html` file on your mobile device:

1. **Direct Download**: 
   - Open this repository on your mobile device's web browser.
   - Find the `lmstudiowebui.html` file and download it directly to your device.

2. **Email to Yourself**:
   - Download the `lmstudiowebui.html` file on your computer.
   - Email it to yourself as an attachment.
   - Open the email on your mobile device and download the attachment.

3. **Cloud Storage**:
   - Upload the `lmstudiowebui.html` file to a cloud storage service like Google Drive, Dropbox, or iCloud.
   - Access the file from your mobile device using the respective cloud storage app.

4. **File Transfer Apps**:
   - Use apps like AirDrop (for iOS devices) or nearby sharing (for Android devices) to transfer the file from your computer to your mobile device.

## Usage Instructions

1. **Start LM Studio Server**:
   - Open LM Studio on your computer.
   - Go to the "Server" tab (In 0.3.x -> Developer -> Local Server).
   - Ensure that CORS is enabled and Serve on Local Network is enabled.
   - Click "Start Server" and note down the server address.

2. **Open the Chat Interface**:
   - On desktop: Double-click the `lmstudiowebui.html` file to open it in your default web browser.
   - On mobile: Use a file manager app to locate the downloaded `lmstudiowebui.html` file and open it with your web browser.

3. **Connect to LM Studio Server**:
   - In the chat interface, enter the LM Studio server address in the input field at the top. 
   - Click the "Connect" button.

4. **Start Chatting**:
   - Once connected, you can start typing messages in the input field at the bottom of the screen.
   - Press Enter or tap Send to send your message.
   - The model's responses will appear in the chat window.

## Troubleshooting

- **Can't connect to server**: 
  - Ensure LM Studio Server is running on your computer.
  - Check that you're using the correct server address.
  - If accessing from another device, make sure both devices are on the same network.

- **Slow responses**: 
  - LM Studio processing speed depends on your computer's capabilities. Larger models may take longer to respond.

- **Interface not loading**: 
  - Try opening the `lmstudiowebui.html` file with a different web browser.

## Security Note

This interface is designed for local use only. Do not expose your LM Studio server to the public internet without proper security measures in place.

## Feedback and Contributions

This is a personal project. While the code is public for anyone to use and learn from, I am **not accepting pull requests** for new features or bug fixes. If you find an issue or have a suggestion, please open an issue to discuss it.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=YorkieDev/LMStudioWebUI&type=Date)](https://star-history.com/#YorkieDev/LMStudioWebUI&Date)

---

## 📝 Fixes Applied (2026-06-24)

### OpenAI Compatibility API Fixes

This repository has been updated to fix compatibility issues with modern versions of LM Studio. The following changes were made to `index.html`:

1. **Removed deprecated model ejection API**
   - Deleted the `ejectCurrentModel()` function that called `/v1/model/eject`
   - Modern LM Studio handles model ejection automatically via `/v1/chat/completions`

2. **Fixed model list parsing**
   - Changed from expecting `{ data: [{ id }] }` format
   - Now correctly parses modern LM Studio's response: `{ models: [{ id }] }`
   - Fallback to `data.data` for legacy servers still works

3. **Added robust error handling**
   - Improved JSON parsing in streaming responses
   - Better error messages for connection failures

### How to Use the Fixed Version

1. **Download the fixed file**:
   ```bash
   # Clone this repository
   git clone <repo-url>
   cd lmstudiowebui-main
   
   # Download the fixed version (index.html is modified)
   ```

2. **Open directly**:
   - Desktop: Double-click `index.html` or open via browser
   - Mobile: Transfer to device and open with Edge (iOS) or any browser (Android)

### Verification

Test the fixed version with a local LM Studio instance:

```bash
# Start LM Studio server
lmstudio --server

# Test the connection
curl http://localhost:1234/v1/models
```

The fixed web UI should now correctly list available models without errors.

