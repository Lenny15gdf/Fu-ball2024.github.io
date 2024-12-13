<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fußball 2024 - Chat</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background: #004d00;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        .container {
            width: 80%;
            margin: 20px auto;
            background: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .chat-box {
            height: 300px;
            border: 1px solid #ccc;
            overflow-y: scroll;
            padding: 10px;
            margin-bottom: 20px;
            background: #e9e9e9;
        }
        .message {
            margin: 5px 0;
            padding: 10px;
            border-radius: 5px;
        }
        .message.user {
            background: #d4edda;
            text-align: right;
        }
        .message.bot {
            background: #f8d7da;
            text-align: left;
        }
        input[type="text"] {
            width: calc(100% - 22px);
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        input[type="submit"] {
            padding: 10px 15px;
            background: #004d00;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background: #003300;
        }
    </style>
</head>
<body>

<header>
    <h1>Willkommen im Fußball 2024 Chat!</h1>
</header>

<div class="container">
    <div class="chat-box" id="chatBox"></div>
    <form id="chatForm">
        <input type="text" id="messageInput" placeholder="Schreibe eine Nachricht..." required>
        <input type="submit" value="Senden">
    </form>
</div>

<script>
    const chatBox = document.getElementById('chatBox');
    const chatForm = document.getElementById('chatForm');
    const messageInput = document.getElementById('messageInput');

    chatForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const message = messageInput.value;
        if (message) {
            addMessage(message, 'user');
            messageInput.value = '';
            // Simulate a bot response
            setTimeout(() => {
                addMessage("Danke für deine Nachricht über Fußball!", 'bot');
            }, 1000);
        }
    });

    function addMessage(message, sender) {
        const messageDiv = document.createElement('div');
        messageDiv.classList.add('message', sender);
        messageDiv.textContent = message;
        chatBox.appendChild(messageDiv);
        chatBox.scrollTop = chatBox.scrollHeight; // Scroll to the bottom
    }
</script>

</body>
</html>
