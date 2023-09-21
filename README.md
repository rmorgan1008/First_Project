# First_Project
Username and password Generator
"""
copy

Description:
"""

"""
Lists
Student Project
Project Title:
"""

##LIBRARY###
import random
import tsapp
##LISTS##

usernames =['sweet_kristy','kristy_honey','bubbly_snowflake','angelic.princess.kristy','fairy.princess.kristy','baby_kristy_butterfly','aphobia','Facebookaphobia','Xboxaphobia','Facebookaphobia']
passwords = ['1234','1235','1236','1237','1238','1239','12310','12311','12313','12314']

##questions##
window = tsapp.GraphicsWindow(1018, 573, tsapp.WHITE)
background = tsapp.Sprite("CodeUI.jpg", 0, 0, 1)
text = tsapp.TextLabel("Modak-Regular.ttf", 20, 100, 200, 500, "Username:", tsapp.BLUE)
text.center = background.center
text2 = tsapp.TextLabel("Modak-Regular.ttf", 20, 100, 200, 500, "Password:", tsapp.BLUE)
text2.center = background.center
text2.y += 50

##Main Program##

users_usernames = []
users_passwords = []
while window.is_running:
    window.add_object(background)
    window.add_object(text)
    window.add_object(text2)
    window.finish_frame()
    
    new_username = input("Choose which username you would like, than enter it below to recieve your password. Than click enter to log in\n(Click Enter To Continue)")
    print(usernames)
    enter_username = ''
    while enter_username not in usernames:
        enter_username = input("enter your username:")
        username_text = tsapp.TextLabel("Modak-Regular.ttf", 20, 100, 200, 500,enter_username, tsapp.RED)
        username_text.center = background.center
        username_text.x += 110
        window.add_object(username_text)
        window.finish_frame()
    else:
        index = usernames.index(enter_username)
        users_usernames.append(enter_username)
    print(users_usernames)     
##GET PASSWORD ##

    users_passwords.append(passwords[index])
    
##See Password##
    see_password = input("Click enter to see your password:")
    print("Your password is:" + str(users_passwords))


##Type username AND password##

##USERNAME##
    while True:
        
        username_final = input("Please enter your username:")
        
##PASSWORD##
        password_final = input("Please enter your password:")
        if password_final in passwords:
            index_password_final = passwords.index(password_final)
        
##CHECK##
        ##Username Check##
        if username_final in usernames:
            ##Password Check##
            if password_final in passwords:
                password_list = ''
                password_text = tsapp.TextLabel("Modak-Regular.ttf", 20, 100, 200, 500,password_final, tsapp.RED)
                window.add_object(password_text)
                password_text.center = background.center
                censored_password = ''
                for letter in password_text.text:
                    censored_password = censored_password + '*'
                password_text.text = censored_password
                password_text.x += 110
                password_text.y += 50
                
                index_username_final = usernames.index(username_final)
                index_password_final = passwords.index(password_final)
            ##if good##
                if index_username_final == index_password_final:
                    print('works')
                    break
            ##if blank##
            if index_username_final == '' or index_password_final == '':
                print("Username or password was incorrect")
        ## if wrong ##
        else:
            print("Username or password was incorrect")
    
##Log In## 

    log_in = tsapp.TextLabel("Modak-Regular.ttf", 20, 100, 200, 500,"PRESS ENTER TO LOG IN", tsapp.RED)
    window.add_object(log_in)
    log_in.center = background.center
    log_in.y += 100
    log_in.x += 150
    window.finish_frame()
    log_in_input = input('')
    window = tsapp.GraphicsWindow(1019, 573, tsapp.WHITE)
    background = tsapp.Sprite("AirCityEdge.jpg", 0, 0, 1)

    window.add_object(background)
    window.finish_frame()
##THE GAME##############
    KIGDOM_GATES = tsapp.TextLabel("PrincessSofia-Regular.ttf", 80, 50, 90, 500,"KIGDOM GATES", tsapp.WHITE)
    log_in = tsapp.TextLabel("Modak-Regular.ttf", 30, 330, 486, 500,"PRESS ENTER TO LOG IN", tsapp.WHITE)
    window.add_object(log_in)
    window.add_object(KIGDOM_GATES)
    window.finish_frame()
    stop = input("")
##FINISH##

    window.finish_frame()
