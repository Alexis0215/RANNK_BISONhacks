# RANNK_BISONhacks
class bison_hack():
    def __init__(self,user = {},number = 0):
        self.user = user
        self.number = number
    def create_account(self):
        u = input("Username: ")
        p =input("Password: ")
        user = self.user
        user[u]=p
    def log_options(self):
        user = self.user
        user_i = input("Login or Create Account ?\n Type L for Login & C for Create Account")
        if user_i == "L":
            u = input("Login: ")
            if u in user.keys():
                p = input("Password: ")
                if p == user[u]:
                    print("Login successful")
                else:
                    while p != user[u]:
                        print("Password Not found try again")
                        p = input("Password: ")
            else:
                while u not in user.keys():
                    print("User not found try again")
                    u = input("Login: ")
        elif user_i == "C":
            b_hack.create_account()
            input("Account Created.")
        else:
            while user_i != "L" and user_i != "C":
                print("Option not available")
                user_i = input("Login or Create Account ?\n Type L for Login & C for Create Account")
    def welcome_screen(self):
       b_hack.log_options()
       b_hack.dashboard()
    def dashboard(self):
        print("Welcome.\n|Dashboard|| My day | Footprints log | me | social | eco map | about us |\n\nYour footprint score is:\n\n",self.number,"\n")
        choice = "r"
        while choice != "q":
            choice = user_choice= input("Please type a letter: M- My day, f- footprints, m- me, s- social, e- eco map, a-about us")
            if choice == "f":
                input("[w]alk\n[b]ike\n[c]arpool\n[m]etro\n[ec]onomic flight\n[el]ectric car\n[h]ybrid\n[r]ecycle")

        #if user_choice= "f":
        #    b_hack.points_tracker() #call points tracker function, goes to footprints log screen 
        #if user_choice="s":
        #    b_hack.leaderboard() #call leaderboard function
        
    

                

b_hack = bison_hack()
#b_hack.welcome_screen()
b_hack.dashboard()
print("hello")

