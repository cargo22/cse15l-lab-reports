# Part 1
When it came to making StringServer, I followed a similar approach as to what we did in Lab 2.
Therefore, I used the code given to us there as a template and went from there. Here is how I did it.

```
class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```

This code was purely to start the server, now this is how I implemented it.

```
class Handler implements URLHandler {
    String answer = "";

    public String handleRequest(URI url) {
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                answer += parameters[1] + "\n";
                return String.format("%s",answer);
            }
        }
        return "404 Not Found!";
    }    
}
```

This was the code that updated the webpage every time a new request was made.
Here's how it works: 

![image](https://user-images.githubusercontent.com/97927174/233862864-575ef6e3-0c29-4f2f-a709-5b415ca25fce.png)

![image](https://user-images.githubusercontent.com/97927174/233862894-70665729-1021-4c8e-b2a6-2869f36b41a9.png)

# Part 2
In lab 3, one of the many methods that produced errors was the averageWithoutLowest method. Here is one failure-inducing input:

```
  @Test
  public void testAverageWithoutLowest() {
    double[] input4 = { 3 , 3 , 3 };
    assertEquals(3, ArrayExamples.averageWithoutLowest(input4), 0.0);
  }
  ```
  
 This test resulted in an error. The expected average of the array {3,3,3} should be 3, but JUnit indicated that the expected output did not match the actual input.
 However, not all tests resulted in an error. Here is an example of a test that did work:
 
 ```  @Test
  public void testAverageWithoutLowest() {
    double[] input4 = { 1 , 3 , 3 , 3 };
    assertEquals(3, ArrayExamples.averageWithoutLowest(input4), 0.0);
  }
  ```
This test passed according to JUnit. In this case, when we drop the lowest, the average should be 3, and that is what the actual value is.
Now, here are the symptoms given by JUnit. This is the first test:

![image](https://user-images.githubusercontent.com/97927174/233864686-f53692eb-8427-4967-93ef-fb108bac1443.png)

This is the second test:

![image](https://user-images.githubusercontent.com/97927174/233864755-87d3fcde-84a6-482d-a04d-deb6e76a69b7.png)

