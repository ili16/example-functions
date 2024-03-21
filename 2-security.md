# Security

Maintaining and updating code is essential for ensuring the security of modern software systems. However, when code becomes unmaintainable, such as through complex or outdated practices, updating it becomes challenging. For instance, outdated security practices like using insecure hashing algorithms can compromise system security. Consequently, failure to modernize code can lead to vulnerabilities, making systems more susceptible to exploitation and compromising sensitive data.

#### Task 1: Select one these functions and ask a security related question

select code -> right click -> Modernizer -> Generate custom Prompt -> enter your question or instruct

#### Task 2: Select another function and use a pre-defined security question

select code -> right click -> Modernizer -> Generate Prompt By List -> select security -> select an instruct

```PHP
<?php
session_start();

if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_POST['login'])) {
    $username = $_POST['username'];
    $password = $_POST['password'];

    if ($valid_credentials) {
        $_SESSION['user_id'] = $user_id;

        header('Location: dashboard.php');
        exit;
    } else {
        $error_message = "Invalid username or password.";
    }
}

if ($_SERVER['REQUEST_METHOD'] === 'GET' && isset($_GET['logout'])) {
    session_destroy();

    header('Location: index.php');
    exit;
}
?>

```

```C#
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;
using System.Security.Cryptography;

namespace Serialization
{
    [Serializable]
    public class Player
    {
        public string Username { get; set; }
        public string Password { get; set; }

        public Player(string username, string password)
        {
            Username = username;
            Password = password;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                Player player = new Player("Bob", "password123");

                BinaryFormatter formatter = new BinaryFormatter();
                using (MemoryStream ms = new MemoryStream())
                {
                    formatter.Serialize(ms, player);
                    byte[] serializedPlayer = ms.ToArray();

                    Player deserializedPlayer = (Player)formatter.Deserialize(new MemoryStream(serializedPlayer));

                    Console.WriteLine("Player's password: " + deserializedPlayer.Password);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine("Exception: " + ex.Message);
            }
        }
    }
}

```

```Python

import hashlib

def hash_password(password):
    hashed_password = hashlib.md5(password.encode()).hexdigest()
    return hashed_password

def login(username, password):
    stored_password = get_stored_password(username)
    if stored_password:
        hashed_password = hash_password(password)
        if hashed_password == stored_password:
            print("Login successful!")
        else:
            print("Incorrect password!")
    else:
        print("User not found!")

def get_stored_password(username):
    # In a real-world scenario, this function would retrieve the stored password from a database
    if username == "admin":
        return "21232f297a57a5a743894a0e4a801fc3"  # MD5 hash of "admin" (insecure)

if __name__ == "__main__":
    username = input("Enter username: ")
    password = input("Enter password: ")
    login(username, password)

```