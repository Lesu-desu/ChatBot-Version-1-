CHATBOT-VERSION-1

This is a basic AI chatbot built with Java. It responds to user input and remembers past conversations, so it can learn and improve over time.

WHAT IT CAN DO?

Learns from your responses.

Remembers past conversations.

Provides a simple, text-based chat experience.


HOW IT WORKS?

1. You type a message.


2. If the chatbot knows the answer, it replies.


3. If it doesn’t, it asks you for the correct response and saves it for the future.


4. The next time you ask the same thing, it will remember and reply with what you taught it.


5. Type "exit" to end the chat.



JAVA CODE.

import java.util.HashMap;
import java.util.Scanner;

public class ChatBot {
    // Memory to store user inputs and their corresponding responses
    private HashMap<String, String> memory = new HashMap<>();
    private Scanner scanner = new Scanner(System.in);

    // Method to start the chatbot conversation
    public void startChat() {
        System.out.println("Hello! I'm your chatbot. Type 'exit' to end the chat.");

        while (true) {
            System.out.print("You: ");
            String userInput = scanner.nextLine().toLowerCase(); // Convert input to lowercase for consistency

            // Exit condition
            if (userInput.equals("exit")) {
                System.out.println("Chatbot: Goodbye!");
                break;
            }

            // Check if the chatbot has a saved response for this input
            if (memory.containsKey(userInput)) {
                System.out.println("Chatbot: " + memory.get(userInput));
            } else {
                // Ask the user for a response if the chatbot doesn't know the answer
                System.out.print("Chatbot: I don't know. How should I respond? ");
                String response = scanner.nextLine();

                // Store the new response in memory
                memory.put(userInput, response);
                System.out.println("Chatbot: Got it! I'll remember that.");
            }
        }
    }

    // Main method to run the chatbot
    public static void main(String[] args) {
        ChatBot bot = new ChatBot();
        bot.startChat();
    }
}

 HOW TO RUN?

1. Install Java (if not already installed).  
2. Copy the code into a file named `ChatBot.java`.  
3. Open a terminal and navigate to the file's location.  
4. Compile the program:  
   ```sh
   javac ChatBot.java





