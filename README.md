# my-dados-privacy

Create a table in the database that will store messages posted on the firewall. The table can be created with the following structure:

CREATE TABLE `fire_wall` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user_name` varchar(255) NOT NULL,
  `message` text NOT NULL,
  `post_date` datetime NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

<--! use of html Create an HTML page that allows users to post messages to the firewall. The page might have the following code:-->

<!DOCTYPE html>
<html>
<head>
	<title>FIRE WALL</title>
</head>
<body>
	<h1>Fire Wall</h1>
	<form action="post_message.php" method="post">
		<label for="user_name">Your Name:</label>
		<input type="text" name="user_name" id="user_name"><br>
		<label for="message">Your Message:</label>
		<textarea name="message" id="message"></textarea><br>
		<input type="submit" value="Post Message">
	</form>
</body>
</html>

<--!Create a PHP file that processes the sending of the message and saves the data in the database table. The file may have the following code:-->

<?php
// Conexão com o banco de dados
$host = "localhost";
$username = "username";
$password = "password";
$dbname = "database_name";
$conn = mysqli_connect($host, $username, $password, $dbname);
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}

// Obter os dados do formulário
$user_name = $_POST['user_name'];
$message = $_POST['message'];
$post_date = date('Y-m-d H:i:s');

// Inserir os dados na tabela do banco de dados
$sql = "INSERT INTO wall_fire (user_name, message, post_date) VALUES ('$user_name', '$message', '$post_date')";
if (mysqli_query($conn, $sql)) {
    echo "Message posted successfully.";
} else {
    echo "Error: " . $sql . "<br>" . mysqli_error($conn);
}

// Fechar a conexão com o banco de dados
mysqli_close($conn);
?>

<--!Create an HTML page that displays the messages posted on the firewall. The page might have the following code:-->

<!DOCTYPE html>
<html>
<head>
	<title>Fire Wall</title>
</head>
<body>
	<h1>Fire Wall</h1>
	<?php
	// Conexão com o banco de dados
	$host = "localhost";
	$username = "username";
	$password = "password";
	$dbname = "database_name";
	$conn = mysqli_connect($host, $username, $password, $dbname);
	if (!$conn) {
	    die("Connection failed: " . mysqli_connect_error());
	}

	// Obter as mensagens da tabela do banco de dados
	$sql = "SELECT user_name, message, post_date FROM wall_fire ORDER BY post_date DESC";
	$result = mysqli_query($conn, $sql);

	// Exibir as mensagens na página
	if (mysqli_num_rows($result) > 0) {
	    while($row = mysqli


{...}

<!DOCTYPE html>
<html>
<head>
	<title>Fire Wall</title>
	<style>
		body {
			background-image: url('https://png.pngtree.com/background/20210715/original/pngtree-abstract-painting-blots-background-marble-texture-gold-alcohol-ink-pink-blue-picture-image_1266892.jpg');
			background-size: cover;
		}
		form, .messages {
			background-color: rgba(255, 255, 255, 0.8);
			padding: 20px;
			margin-bottom: 20px;
		}
		form input[type=text], form textarea {
			width: 100%;
			padding: 10px;
			margin-bottom: 10px;
			border-radius: 5px;
			border: none;
			box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
		}
		form textarea {
			height: 100px;
		}
		form input[type=submit] {
			background-color: #4CAF50;
			color: white;
			border: none;
			padding: 10px 20px;
			cursor: pointer;
			border-radius: 5px;
			box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
		}
		.messages {
			border-radius: 5px;
			box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
		}
		.message {
			padding: 10px;
			margin-bottom: 10px;
			border-bottom: 1px solid rgba(0, 0, 0, 0.2);
		}
		.message h3 {
			margin-top: 0;
			margin-bottom: 5px;
			color: #6c757d;
		}
		.message p {
			margin-top: 0;
			margin-bottom: 0;
		}
	</style>
</head>
<body>
	<h1>Fire Wall</h1>
	<form action="post_message.php" method="post">
		<label for="user_name">Your Name:</label>
		<input type="text" name="user_name" id="user_name">
		<label for="message">Your Message:</label>
		<textarea name="message" id="message"></textarea>
		<input type="submit" value="Post Message">
	</form>
	<div class="messages">
		<?php
		// Conexão com o banco de dados
		$host = "localhost";
		$username = "username";
		$password = "password";
		$dbname = "database_name";
		$conn = mysqli_connect($host, $username, $password, $dbname);
		if (!$conn) {
		    die("Connection

	h1 {
		font-size: 3rem;
		margin-bottom: 30px;
	}

	form {
		display: inline-block;
		margin-bottom: 50px;
	}

	form input[type="text"], form textarea {
		display: block;
		margin: 10px auto;
		padding: 10px;
		width: 70%;
		border-radius: 5px;
		border: none;
		background-color: rgba(255, 255, 255, 0.9);
		color: #000000;
		font-size: 1.2rem;
		font-weight: bold;
	}

	form input[type="submit"] {
		display: block;
		margin: 10px auto;
		padding: 10px;
		width: 30%;
		border-radius: 5px;
		border: none;
		background-color: #663399;
		color: #ffffff;
		font-size: 1.2rem;
		font-weight: bold;
		cursor: pointer;
	}

	.messages {
		display: inline-block;
		text-align: left;
		padding-left: 5%;
		padding-right: 5%;
		margin-bottom: 50px;
		max-width: 700px;
		border-radius: 5px;
		background-color: rgba(255, 255, 255, 0.9);
	}

	.messages h2 {
		font-size: 1.5rem;
		margin-bottom: 20px;
	}

	.messages p {
		margin-top: 5px;
		margin-bottom: 5px;
		font-size: 1.2rem;
	}

	.messages .message {
		border-bottom: 1px solid #cccccc;
		padding-bottom: 10px;
		margin-bottom: 10px;
	}

	@media screen and (max-width: 767px) {
		form input[type="text"], form textarea, form input[type="submit"] {
			width: 90%;
		}
	}
</style>
</head>
<body>
	<h1>Fire Wall</h1>
	<form action="post_message.php" method="post">
		<label for="user_name">Your Name:</label>
		<input type="text" name="user_name" id="user_name" required><br>
		<label for="message">Your Message:</label>
		<textarea name
    
    <!DOCTYPE html>
<html>
<head>
	<title>Fire Wall</title>
	<style>
		body {
			background-color: #6C5B7B;
			color: #fff;
			font-family: Arial, sans-serif;
		}
		h1 {
			text-align: center;
			font-size: 3em;
			margin: 0;
			padding: 1em 0;
			color: #fff;
		}
		.message {
			background-color: #fff;
			margin: 1em;
			padding: 1em;
			border-radius: 10px;
			box-shadow: 0 0 10px #000;
		}
		.message h2 {
			font-size: 1.5em;
			margin: 0;
			padding: 0;
		}
		.message p {
			font-size: 1em;
			margin: 0;
			padding: 0;
		}
	</style>
</head>
<body>
	<h1>Fire Wall</h1>
	<div id="messages">
		<!-- As mensagens postadas serão exibidas aqui -->
	</div>
	<form action="post_message.php" method="post">
		<label for="user_name">Seu nome:</label>
		<input type="text" name="user_name" id="user_name"><br>
		<label for="message">Sua mensagem:</label>
		<textarea name="message" id="message"></textarea><br>
		<input type="submit" value="Postar Mensagem">
	</form>
	<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
	<script>
		// Use jQuery para obter as mensagens postadas e exibi-las na página
		$(document).ready(function() {
			$.get('get_messages.php', function(data) {
				$('#messages').html(data);
			});
		});
	</script>
</body>
</html>
