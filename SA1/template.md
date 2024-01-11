Clone the Web Page
============================




In this activity, you will learn to clone a web page using CORS.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10985976/SA1.gif" width = "100%" height = "auto">




Follow the given steps to complete this activity:




1. Set the web page URL.




* Open the `proxy-server.py` file.




* Set the web page URL and enable CORS.
~~~python
CORS(app)
 
target_url = "https://www.netflix.com/Login"
~~~
2. Copy the web page.
* Copy the web page by defining a function to extract the content from the web page.
~~~python
@app.route('/proxy')
def proxy():
    response = requests.get(target_url)
    return Response(response.text,
                  status=response.status_code,
                  content_type=response.headers['content-type'])
~~~
3. Initialize the request.
* Open the `index.html` file.
* Initialize the request by including the jQuery library.
~~~html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
~~~
4. Retrieve the HTML content.
* Retrieve the HTML content of the web page by creating a jQuery function that executes when the HTML document is fully loaded and ready.
~~~html
<script>
        let html;
        $(document).ready(function () {
               });
~~~
* Extract the content of the web page by calling the proxy function on the server.
~~~sh
     $.ajax({
                url: 'http://127.0.0.1:5000/proxy',
                success: function (data) {
                  newhtml = data;
                    display_html();
                }
               });
~~~
5. Display the HTML page.
* CLoad the web page dynamically by appending the content stored in the html variable to the selected body element.
~~~sh
function display_html() {
        $("body").append(newhtml);
        }
~~~
* Save and run the code to check the output.
