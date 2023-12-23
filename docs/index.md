
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background-color: #f0f0f0; /* Adjust the background color as needed */
            margin: 0;
            font-family: Arial, sans-serif;
        }

        .chat-container {
            position: fixed;
            right: 20px; /* Adjust the right distance as needed */
            bottom: 20px;
            z-index: 999;
        }

        #chatBox {
            display: block; /* Make the chat box open by default */
            position: fixed;
            bottom: 80px;
            right: 30px;
            width: 350px; /* Adjust the width as needed */
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
            width: 90%; /* Adjust the width as needed */
            padding: 5px;
        }

        #agentImage {
            width: 50px;
            height: 50px;
            border-radius: 50%;
        }

        /* Additional styling for the welcome section */
        .welcome-section {
            text-align: center;
            margin-top: 20%;
            color: #333; /* Adjust the text color as needed */
        }

        h1 {
            font-size: 2em;
            margin-bottom: 10px;
        }

        p {
            font-size: 1.2em;
        }
    </style>
    <title>Welcome to erikadel.com!</title>
</head>
<body>

<!-- Welcome Section -->
<div class="welcome-section">
    <h1>Welcome to erikadel.com!</h1>
    <p>Get out while you still can!</p>
</div>

<!-- Chat box -->
<div class="chat-container">
    <div id="chatBox" class="chat-box">
        <img src="https://i.gyazo.com/96b0767f412e3323cad9517bae88c537.png" alt="Agent Image" id="agentImage">
        <div id="chatMessages" class="chat-messages"></div>
        <input type="text" id="userInput" placeholder="Type your message..." onkeydown="handleKeyDown(event)">
        <button onclick="sendMessage()">Send</button>
    </div>
</div>

<script>
    // Your existing scripts go here

    const chatBox = document.getElementById('chatBox');
    const chatMessages = document.getElementById('chatMessages');
    const userInput = document.getElementById('userInput');
    const agentImage = document.getElementById('agentImage');

    // Function to send a message
    function sendMessage() {
        const userMessage = userInput.value.trim();
        if (userMessage !== '') {
            appendMessage('user', `You: ${userMessage}`);
            // Determine the agent's response randomly
            const agentResponse = Math.random() < 0.50
                ? 'go away :('
                : 'i\'m such a snoozepilled sleepcel 😪';
            setTimeout(() => appendMessage('agent', `wapple: ${agentResponse}`), 1000);
            userInput.value = '';
        }
    }

    // Function to append a message to the chat box
    function appendMessage(sender, message) {
        const messageDiv = document.createElement('div');
        messageDiv.classList.add(sender);
        // If the sender is the agent, add the image
        if (sender === 'agent') {
            const agentImageClone = agentImage.cloneNode(true);
            messageDiv.appendChild(agentImageClone);
        }
        messageDiv.textContent = message;
        chatMessages.appendChild(messageDiv);
        chatMessages.scrollTop = chatMessages.scrollHeight;
    }

    // Greet the user with an initial message from the agent
    setTimeout(() => appendMessage('agent', 'Talk to me for help or support!'), 500);

    // Handle Enter key press to send message
    function handleKeyDown(event) {
        if (event.key === 'Enter') {
            sendMessage();
        }
    }
</script>

</body>
</html>
