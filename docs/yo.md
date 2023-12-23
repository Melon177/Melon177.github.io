<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* Your existing styles go here */

        .chat-container {
            position: fixed;
            left: 20px;
            bottom: 20px;
            z-index: 999;
        }

        #chatBtn {
            background-color: #4CAF50;
            border: none;
            color: white;
            padding: 10px;
            border-radius: 50%;
            cursor: pointer;
        }

        #chatBox {
            display: none;
            position: fixed;
            bottom: 80px;
            left: 30px;
            width: 250px;
            background-color: #f1f1f1;
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
        }

        .chat-messages {
            max-height: 150px;
            overflow-y: auto;
        }

        #userInput {
            width: 80%;
            padding: 5px;
        }
    </style>
    <title>Your Website</title>
</head>
<body>

<!-- Your website content goes here -->

<!-- Chat button and box -->
<div class="chat-container">
    <button id="chatBtn">
        <img src="https://i.gyazo.com/96b0767f412e3323cad9517bae88c537.png" alt="Your Face">
    </button>
    <div id="chatBox" class="chat-box">
        <div id="chatMessages" class="chat-messages"></div>
        <input type="text" id="userInput" placeholder="Type your message...">
        <button onclick="sendMessage()">Send</button>
    </div>
</div>

<script>
    // Your existing scripts go here

    const chatBtn = document.getElementById('chatBtn');
    const chatBox = document.getElementById('chatBox');
    const chatMessages = document.getElementById('chatMessages');
    const userInput = document.getElementById('userInput');

    chatBtn.addEventListener('click', toggleChatBox);

    function toggleChatBox() {
        chatBox.style.display = chatBox.style.display === 'none' ? 'block' : 'none';
    }

    function sendMessage() {
        const userMessage = userInput.value.trim();
        if (userMessage !== '') {
            appendMessage('user', userMessage);
            setTimeout(() => appendMessage('agent', 'go away :('), 1000);
            userInput.value = '';
        }
    }

    function appendMessage(sender, message) {
        const messageDiv = document.createElement('div');
        messageDiv.classList.add(sender);
        messageDiv.textContent = message;
        chatMessages.appendChild(messageDiv);
        chatMessages.scrollTop = chatMessages.scrollHeight;
    }
</script>

</body>
</html>
