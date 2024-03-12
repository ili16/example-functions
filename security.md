# Security

A secure function in itself can turn bad 

```
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

```
import java.io.*;

public class Serialization {
    public static void main(String[] args) {
        try {
            Player player = new Player("Alice", "password123");

            FileOutputStream fileOut = new FileOutputStream("player.ser");
            ObjectOutputStream out = new ObjectOutputStream(fileOut);
            out.writeObject(player);
            out.close();
            fileOut.close();

            FileInputStream fileIn = new FileInputStream("player.ser");
            ObjectInputStream in = new ObjectInputStream(fileIn);
            Player deserializedPlayer = (Player) in.readObject();
            in.close();
            fileIn.close();

            System.out.println("Player's password: " + deserializedPlayer.getPassword());
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}

class Player implements Serializable {
    private String username;
    private String password;

    public Player(String username, String password) {
        this.username = username;
        this.password = password;
    }

    public String getPassword() {
        return password;
    }
}
```

```

import hashlib

def hash_password(password):
    # Insecure hashing algorithm (MD5)
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