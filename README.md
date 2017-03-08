# groovy-http-request
Simple examples for making HTTP requests with native Groovy code

```groovy
// GET
def get = new URL("https://httpbin.org/get")
  .openConnection();
def getRC = get.getResponseCode();
println(getRC);
if(getRC.equals(200)) {
    println(get.getInputStream().getText());
}

// POST
def post = new URL("https://httpbin.org/post")
  .openConnection();
def message = '{"message":"this is a message"}'
post.setRequestMethod("POST")
post.setDoOutput(true)
post.setRequestProperty("Content-Type", "application/json")
post.getOutputStream()
  .write(message.getBytes("UTF-8"));
def postRC = post.getResponseCode();
println(postRC);
if(postRC.equals(200)) {
    println(post.getInputStream().getText());
}
```
