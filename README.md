# form

#HTML code

<!DOCTYPE html>
<html lang=" en">
<head>
    <meta charset = UTF-8>
    <title> SendEmail</title>
    <link rel = "stylesheet" type = "text/css" href = style.css>
</head>
<body>
    <form action = "process_form.php" method = "POST">
        <div>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
        </div>
        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
        </div>
        <div>
            <label for="message">Message:</label>
            <textarea id="message" name="message" required></textarea>
        </div>
        <button type="submit" id="submit-button">Submit</button>
    </form>
    
    
</body>

#css code

form {
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
label, input, textarea {
    display: block;
    margin-bottom: 10px;
}
label {
    font-weight: bold;
}
input[type="text"],
input[type="email"],
textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
button {
    padding: 10px;
    background-color: #4CAF50;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
button:hover {
    background-color: #3e8e41;
}

php code

<?php
$name = $_POST['name'];
$email = $_POST['email'];
$message = $_POST['message'];
 
if (!empty($name) && !empty($email) && !empty($message)) {
    $to = 'your-email@example.com';
    $subject = 'Новое сообщение';
    $message = $_POST["message"];
 
    if (mail($to, $subject, $message)) {
        echo 'Ваше сообщение успешно отправленно';
    } else {
        echo 'Ошибка при отправке';
    }
} 
?>
