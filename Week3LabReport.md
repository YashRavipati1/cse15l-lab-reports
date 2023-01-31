# Week 3 Lab Report

# Part 1 - String Server

String Server Code:

    import java.io.IOException;
    import java.net.URI;

      class Handler implements URLHandler {
        // The one bit of state on the server: a number that will be manipulated by
        // various requests.
        String str = "";

        public String handleRequest(URI url) {
            if (url.getPath().equals("/")) {
                return str;
            } else {
                System.out.println("Path: " + url.getPath());
                if (url.getPath().contains("/add-message")) {
                    String[] parameters = url.getQuery().split("=");
                    if (parameters[0].equals("s")) {
                        str += "\n"+ parameters[1];
                        return str;
                    }
                }
                return "404 Not Found!";
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


![image](https://user-images.githubusercontent.com/63521936/215462925-2928b79e-1bab-4b62-9cfc-f1883de5c840.png)

Methods Called:
- Main - Called when the program runs and takes in the argument args from the terminal input to be used as the port for the web server; This changes the class field "port" which is where the server runs.
- HandleRequest - Takes in the argument URL, which is what is used in the browser. The URL is used to identify if there is a message to add, and what the message is. When this function is called, the message is added on a new line to the variable str, which is the field that stores the string to be printed on the website.


# Part 2 - Testing

Failure Inducing Input:

    @Test
    public void testFilter(){
        List<String> input1 = new ArrayList<>();
        input1.add(0, "hello");
        input1.add(0, "hi");
        input1.add(0, "welcome");
        input1.add("add");
        input1.add("am");

        List<String> result = ListExamples.filter(input1, new aChecker());
        List<String> expected = new ArrayList<>();
        expected.add("add");
        expected.add("am");
        assertEquals(expected, result);
    }
    
Non Failure Inducing Input

    @Test
    public void testFilter(){
        List<String> input1 = new ArrayList<>();
        input1.add("am");

        List<String> result = ListExamples.filter(input1, new aChecker());
        List<String> expected = new ArrayList<>();
        expected.add("am");
        assertEquals(expected, result);
    }
    
## Symptom:

![image](https://user-images.githubusercontent.com/63521936/215640945-c35fc38c-d921-4707-a5da-691f9c9e6855.png)

## Bug:

Before:

      static List<String> filter(List<String> list, StringChecker sc) {
        List<String> result = new ArrayList<>();
        for(String s: list) {
          if(sc.checkString(s)) {
            result.add(0, s);
          }
        }
        return result;
      }
      
After:

      static List<String> filter(List<String> list, StringChecker sc) {
        List<String> result = new ArrayList<>();
        for(String s: list) {
          if(sc.checkString(s)) {
            result.add(s);
          }
        }
        return result;
      }

The fix ensures that the words that pass the filter are added at the end of the List instead of the start. This is by changing result.add(0, s) to result.add(s).

# Part 3

I learned how to build and run a web server. This includes how to start a server on a specific port and how to open the server on a browser using localhost. I also learned how to manipulate what the web server does using the URL path and search queries using URI objects. I was then able to start the web servers I made on a remote computer, a skill I didn't have before.
