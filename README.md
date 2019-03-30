class bison_hack():
    def __init__(self,user = {},number = 0.0,store = {}):
        self.user = user
        self.number = number
        self.store = store
    def create_account(self):
        u = input("Username: ")
        p =input("Password: ")
        user = self.user
        user[u]=p
    def log_options(self):
        user = self.user
        user_i = input("Login or Create Account ?\n Type L for Login & C for Create Account\n")
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
        stored = self.store
        choice = "r"
        w_m = 0 #walk value
        b_m = 0 #bike value 
        r_v = 0 #recycle value
        p_v = 0 #public transp. value
        e_v = 0 #eat beef value
        c_v = 0 #carpool value
        sh_v = 0 #shower value

        while choice != "q":
            print("Welcome.\n| My day | My log | me | social | eco map | Leaderboard | about us | Logout |\n\nYour footprint score is:\n\n",self.number,"\n")
            choice = input("Please type a letter: 1- My day, 2- footprints, 3- me, 4- social, 5- eco map, 6- Leaderboard 7-about us, L- Logout\n")
            if choice == "2":
                choice2 = "x"
                while choice2 != "d":
                    choice2 = input("[r]ecycle\n[w]alk\[b]ike\n[m]etro\n[c]arpool\n[5]minute showers\n[N/D]No Beef/Dairy Day\n[d]one\n")
                    stored[choice2] = 0
                    if choice2 == "w":
                        w_miles = input("How many miles: ")
                        w_m += float(w_miles)
                        stored[choice2] = w_m
                        w_value = float(w_miles)/0.5
                        self.number += (5.0 * w_value)
                        print("New footprint is: ", self.number)
                    elif choice2 == "b":
                        b_miles = input("How many miles: ")
                        b_m += float(b_miles)
                        stored[choice2] = b_m
                        b_value = float(b_miles)/0.5
                        self.number += (5.0 * b_value)
                        print("New footprint is: ", self.number)
                    elif choice2 == "c":
                        self.number += 3.0
                        c_v += 1
                        stored[choice2] = c_v
                        print("New footprint is: ", self.number)
                    elif choice2 == "m":
                        self.number += 7.0
                        p_v += 1
                        stored[choice2] = p_v
                        print("New footprint is: ", self.number)
                    elif choice2 == "5":
                        self.number += 10.0
                        sh_v += 1
                        stored[choice2] = sh_v
                        print("New footprint is: ", self.number)
                    elif choice2 == "N/D":
                        self.number += 15.0
                        e_v += 1
                        stored[choice2] = e_v
                        print("New footprint is: ", self.number)
                    elif choice2 == "r":
                        self.number += 0.5
                        r_v += 1
                        stored[choice2] = r_v 
                        print("New footprint is: ", self.number)
                
            elif choice == "1":
                for x in stored.keys():
                    if x == "w":
                        print("You walked ",w_m," miles today\n")
                    elif x == "b":
                        print("You biked ",b_m," miles today\n")
                    elif x == "c":
                        print("You carpooled ",stored["c"]," times today\n")
                    elif x == "m":
                        print("You rode public transportation ",stored["m"]," times today\n")
                    elif x == "5":
                        print("You saved water taking a shower  ",stored["5"]," times today\n")
                    elif x == "N/D":
                        print("You didn't eat beef/dairy  ",stored["N/D"]," times today\n")
                    elif x == "r":
                        print("You recycled  ",stored["r"]," times today\n")
                if stored == {}:
                    print("You have done nothing today\n")
            if choice == "L":
                print("Logged Out\n\n")
                b_hack.welcome_screen()
            if choice == "6":
                leaderboard()

                
                

                


        #if user_choice= "f":
        #    b_hack.points_tracker() #call points tracker function, goes to footprints log screen 
        #if user_choice="s":
        #    b_hack.leaderboard() #call leaderboard function
def leaderboard():
        print("           --Leaderboard: Global--")
        print(" 1)  funny_bunny  17,987 pts.        USA \n 2)  beyonce1     16,010 pts.        Germany \n 3)  apple_657    15,555 pts.        Kenya")
        print(" 4)  gam_kay5     15,103 pts.        Japan\n 5)  0ferari0     14,400 pts.        Mexico  ")
        print("\n\n          --Leaderboard: Your Friends--")
        print(" 1)  Matt     130 pts. \n 2)  Lauren   125 pts. \n 3)  YOU      100 pts. \n 4)  William  69 pts. \n 5)  Phoeby   50 pts.")          


b_hack = bison_hack({"Nazareth":"Camaro2012","Naja":"Apple","Alexis":"funnybunny"})
b_hack.welcome_screen()


