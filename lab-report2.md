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


For this instance, the method called is handleRequest. Here, it is important to notice that the entire URL matters. First, the path must be "add-message." Otherwise, we get a 404 error. Once the method confirms that the path is "add-message," it moves on to find the query. Note, the query part of the if statement is activated if and only if the url contains a "?". Once it finds the query, the query is split by a equals sign. The left of the equals sign (parameters[0]), must be "s" and whatever is on the right side will be printed on the page essentially. In this case, the arguments needed to get the method to work require "/add-message?s=" and then whatever value you want to print. In this case, the value is "hi." In this case it is important to note that the value can be anything. It doesn't need to only be a string. Because the entire url is a string, anything put into the url is just considered a string and can be input regardless of the characters it contains. When it comes to values of fields, there isn't much that would be changed. There aren't many fields to begin with, and the only ones that are there are strings, meaning that changing a string would simply just slightly affect what is displayed on the screen.



![image](https://user-images.githubusercontent.com/97927174/233862894-70665729-1021-4c8e-b2a6-2869f36b41a9.png)

For this instance, the same thing is happening. However, this time the answer string gets another request sent into it, making the string longer. In this case, the string now holds "hi \n hacker \n" and this is what it would return. Everything that applies to the case above applies to this case as well. The arguments must be the same. In this case, however, the value on the right side of the equals sign is different, therefore leading to a different value to be printed on the page. Once again, everything also applies here meaning that we could've used other characters that aren't strings. Values of fields also don't really have much of an effect here as well. Changing values to certain fields wouldn't really cause any crashing, just slight variation as to what is being displayed. The only major value change that could break the code is if the port number is too high or too low. Other than that, values of fields don't really have too much of an effect.

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

Now that we have identified the bugs and systems, it is time to change the code. In order to get it to work, we need to change a bit. Here are the before and after of the code to show just how I fixed it. Here is the before:

```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
  ```
  
  Here is the after:
  
  ```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
       sum += num;
    }
    return (sum - lowest) / (arr.length - 1);
  }
  ```
The reason the code works now is that it distinguishes a lowest value. In the original code, we found a lowest num within in an array. However, if every number was the lowest, it wasn't counted towards the total sum. Hence, averageWithoutLowest. However, when calculating average, we just want to remove ONE value that is the lowest, not every value. This is why the array { 3, 3, 3 } returned 0, not 3. When run through the original code, every 3 in the array was considered the lowest, therefore not counting it towards the total sum. In the fixed code, I added every number in the array, giving me a total sum. Because the first for loop found the lowest value, I calculated the average by just getting the total and subtracting the lowest value, then dividing it by the length of the array minus one since we are essentially removing the lowest value in the array. This is why the new code works.

# Part 3
In the past 2 labs, I have learned a lot of things that I never knew. However, the one that stood out to me the most was probably the process to start a server. It's cool to see the code I make in an IDE translate to a real URL I can type into my web browser. I know this is super bare bones stuff, but I am interested in learning how this is blown up to create real working websites that can handle user traffic and can stay up for an infinite amount of time. I found it really interesting.
  
  
