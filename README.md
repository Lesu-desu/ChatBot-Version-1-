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
