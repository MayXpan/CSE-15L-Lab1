# Lab Report 2

## Part 1
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    private ArrayList<String> list = new ArrayList<>();
    private String undo;
    private String to_return = "";
    private int sequence_num = 1;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return to_return;
        }
        else if (url.getPath().equals("/clear")) {
            sequence_num = 1;
            list = new ArrayList<>();
            to_return = "";
            return String.format("Everything has been cleared!");
        }
        else if (url.getPath().equals("/undo")) {
            to_return = undo;
            sequence_num--;
            return to_return;
        }
        else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    undo = to_return;
                    list.add(parameters[1]);
                    to_return += String.format("%d. %s%n", sequence_num, list.get(list.size() - 1));
                    sequence_num++;
                    return to_return;
                }
            }
            return "404 Not Found";
        } 
    }
}

class StringServer {
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
![image](<StringServer sc1.png>)
---
![image](<StringServer sc2.png>)

In both of the screenshots they're using the same methods. They both use the handleRequest method as well as the StringServer method, which is to establish a server for what's going on in the handleRequest method.  For the handleRequest method, there are 4 potential things that could happen based off of the argument.  One, if the user does not add a path and it is just the home directory, then I have made it so that it prints out what has been added so far.  There are two other options, clear and undo that I made just for my own sake for when testing so I didn't have to reset the server which do exactly what they are named to be. And there's the part that adds strings, even if the value given after the s= is a string, character, numeric, or an URL, it reads it in as a string and appends it to what has already been added to the server.  And if there's nothing after the s= or if the path is one not defined in the method, then it will return "404 Not Found".

## Part 2
![image](<Path priv key.png>)
---
![image](<Path pub key.png>)
---
![image](<ssh login np.png>)

## Part 3
Everything in week 2 and 3 are completely new to me, so it was definitely interesting to learn all of the content in these two weeks' labs.  Of all of the content from both weeks, I found that how to remotely access a computer and how to build and run a server were the more interesting parts of week 2's lab.  And from week 3, I thought that learning how to set up ssh keys was most interesting due to it making it much easier to login.
