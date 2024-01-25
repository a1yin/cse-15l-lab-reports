ChatServer Code
```
import java.io.IOException;
import java.net.URI;
import java.util.HashMap;

class Handler implements URLHandler {
    HashMap<String, String> userMessageMap = new HashMap<String, String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");
            String userMessage = parameters[0].split("=")[1];
            String user = parameters[1].split("=")[1];

            userMessageMap.put(user, userMessage);

            String messages = "";
            for (String u : userMessageMap.keySet()) {
                messages += u + ": " + userMessageMap.get(u) + "\n";
            }
            return messages;

        } else {
            return "404 Not Found!";
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```


