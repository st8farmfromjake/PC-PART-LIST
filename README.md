#PC-PART-LIST
#Works like nzxts BLD and pc part picker in suggesting pc parts based on the wants of the user/customer.
#replicates pc part picker or nzxt's way of suggesting pc...
#parts based on factors such as...
#games they want to play, resolution, and the fps target...
#It will then give you feedback like price of parts(and the total)...
#It will also display what parts are included in that list
#NZXT's PC builder Link: https://nzxt.com/category/gaming-pcs/build
#PC PART PICKER's Link: https://pcpartpicker.com/list/
#to get accurate wattage numbers I used a realiable source of hardware testing from toms hardware and gamers nexus
import math

#Fornite-4/10graphic  
#Minecraft-5/10graphic
#COD-7/10graphic
#Cyberpunk-9/10graphic
#Valorant-3/10graphic

#end list will be something along the lines of [graphics card, CPU, RAM, Power supply, motherboard]

print("Welcome to the all new personalized PC part selector! Plz call the main() function for me plz and thx :)")
print("Legal Statement: This computer data information is corect at the time of writing so you cannot sue me if u blow up your computer because you used this code 10 years in the future >:(")
      
def main():
    '''the main customer experience'''
    customers_wanted_list=[]
    customers_chosen_game = get_customers_game_input()
    customers_chosen_resolution = get_customers_resolution()
    customers_chosen_fps_target = get_customers_fps_target()
    customers_wanted_list.append(customers_chosen_game)
    customers_wanted_list.append(customers_chosen_resolution)
    customers_wanted_list.append(customers_chosen_fps_target)
    print(customers_wanted_list)
    print("...Loading...So hows the weather?:)")
    card=graphics_card_needed(customers_wanted_list)
    print("got gc...")
    cpu=cpu_needed_for_customers_graphics_card(card)
    print("got cpu...")
    motherboard=motherboard_needed(cpu)
    print("got motherboard...")
    ram=ram_needed(customers_wanted_list)
    print("got ram...")
    completed_list_no_power=[card, cpu, motherboard, ram]
    power_supply=power_supply_needed(completed_list_no_power)
    print("got power supply...")
    customer_complete_returned_list=[card, cpu, motherboard, ram, power_supply]
    print("I suggest you get this list of parts:"+str(customer_complete_returned_list))

    

    
def get_customers_game_input():
    '''gets the customers first game'''
    possible_games_for_customer=["Fortnite", "Minecraft", "Call of Duty: Warzone", "Cyberpunk 2077", "Valorant"]
    game_1=input("What are your 3 favorite games?(Choices: Fortnite, Minecraft, Call of Duty: Warzone, Cyberpunk 2077, and Valorant.)")
    while not game_1 in possible_games_for_customer:
        print("I do not know of those games. Please pick different games(Choices: Fortnite, Minecraft, Call of Duty: Warzone, Cyberpunk 2077, and Valorant)")
        game_1=input("What are your 3 favorite games?(Choices: Fortnite, Minecraft, Call of Duty: Warzone, Cyberpunk 2077, and Valorant)")
    return game_1

def get_customers_resolution():
    '''customer selcects 1080, 2k, or 4k'''
    possible_resolutions_for_customer=["1080","2k","4k"]
    resolution_input=input("What resolution do you wish to game at?(Choices: 1080, 2k, 4k)")
    while not resolution_input in possible_resolutions_for_customer:
        print("I do not know of that resolution")
        resolution_input=input("What resolution do you wish to game at?(Choices: 1080, 2k, 4k)")
    return resolution_input

def get_customers_fps_target():
    '''gets customers frames per second target'''
    possible_fps_targets_for_customer=["60","100","144","200+"]
    fps_target_input=input("How many frames do you wish to be at?(Choices: 60, 100, 144, 200+)")
    while not fps_target_input in possible_fps_targets_for_customer:
        print("Please uses one of the specified choices :)")
        fps_target_input=input("How many frames do you wish to be at?(Choices: 60, 100, 144, 200+)")
    return fps_target_input

def graphics_card_needed(customers_wanted_list):
    '''finds what graphics card is needed for certain games, resolution, and fps target'''
    #the graphics card is the most expensive piece of hardware in a gaming computer since many games will not run on some cpus integrated graphics
    #yes mom you can run solitare on ur 20 year old computer but you cannot expect 4k solitare
    possible_games_for_customer=["Fortnite", "Minecraft", "Call of Duty: Warzone", "Cyberpunk 2077", "Valorant"]
    possible_resolutions_for_customer=["1080","2k","4k"]
    possible_fps_targets_for_customer=["60","100","144","200+"]
    graphics_points=0
    customers_returned_completed_computer_list=[]
    if customers_wanted_list[0]=="Fortnite":
        if customers_wanted_list[1]=="1080":
            if customers_wanted_list[2]=="60":
                return "3060"

            elif customers_wanted_list[2]=="100":
                return"3060"

            elif customers_wanted_list[2]=="144":
                return "3060 ti"

            elif customers_wanted_list[2]=="200+":
                return "3060 ti"

        elif customers_wanted_list[1]=="2k":
            if customers_wanted_list[2]=="60":
                return "3060ti"

            elif customers_wanted_list[2]=="100":
                return "3070"

            elif customers_wanted_list[2]=="144":
                return "3070"

            elif customers_wanted_list[2]=="200+":
                return "3070 ti"

        elif customers_wanted_list[1]=="4k":
            if customers_wanted_list[2]=="60":
                return "3070 ti"

            elif customers_wanted_list[2]=="100":
                return "3070 ti"

            elif customers_wanted_list[2]=="144":
                return "3080"

            elif customers_wanted_list[2]=="200+":
                return "3080 ti"

    elif customers_wanted_list[0]=="Minecraft":
    #will need 32GB of RAM if doing 4k
        if customers_wanted_list[1]=="1080":
            if customers_wanted_list[2]=="60":
                return "3060"

            elif customers_wanted_list[2]=="100":
                return "3060"

            elif customers_wanted_list[2]=="144":
                return "3070"

            elif customers_wanted_list[2]=="200+":
                return "3070"

        elif customers_wanted_list[1]=="2k":
            if customers_wanted_list[2]=="60":
                return "3060 ti"

            elif customers_wanted_list[2]=="100":
                return "3070"

            elif customers_wanted_list[2]=="144":
                return "3070 ti"

            elif customers_wanted_list[2]=="200+":
                return "3080 ti"

        elif customers_wanted_list[1]=="4k":
            if customers_wanted_list[2]=="60":
                return "3070ti"

            elif customers_wanted_list[2]=="100":
                return "3080"

            elif customers_wanted_list[2]=="144":
                return "3080 ti"

            elif customers_wanted_list[2]=="200+":
                return "3090 ti"

    elif customers_wanted_list[0]=="Call of Duty: Warzone":
        if customers_wanted_list[1]=="1080":
            if customers_wanted_list[2]=="60":
                return "3060"

            elif customers_wanted_list[2]=="100":
                return "3060 ti"

            elif customers_wanted_list[2]=="144":
                return "3070"

            elif customers_wanted_list[2]=="200+":
                return "3070 ti"

        elif customers_wanted_list[1]=="2k":
            if customers_wanted_list[2]=="60":
                return "3060 ti"

            elif customers_wanted_list[2]=="100":
                return "3070"

            elif customers_wanted_list[2]=="144":
                return "3070 ti"

            elif customers_wanted_list[2]=="200+":
                return "3080 ti"

        elif customers_wanted_list[1]=="4k":
            if customers_wanted_list[2]=="60":
                return "3070 ti"

            elif customers_wanted_list[2]=="100":
                return "3080 ti"

            elif customers_wanted_list[2]=="144":
                return "3080 ti"

            elif customers_wanted_list[2]=="200+":
                return "3090 ti"

    elif customers_wanted_list[0]=="Cyberpunk 2077":
        if customers_wanted_list[1]=="1080":
            if customers_wanted_list[2]=="60":
                return "3070"

            elif customers_wanted_list[2]=="100":
                return "3070"

            elif customers_wanted_list[2]=="144":
                return "3070 ti"

            elif customers_wanted_list[2]=="200+":
                return "3080 ti"

        elif customers_wanted_list[1]=="2k":
            if customers_wanted_list[2]=="60":
                return "3070 ti"

            elif customers_wanted_list[2]=="100":
                return "3080 ti"

            elif customers_wanted_list[2]=="144":
                return "3090 ti"

            elif customers_wanted_list[2]=="200+":
                return "4080"

        elif customers_wanted_list[1]=="4k":
            if customers_wanted_list[2]=="60":
                return "3090"

            elif customers_wanted_list[2]=="100":
                return "3090 ti"

            elif customers_wanted_list[2]=="144":
                return "4090"

            elif customers_wanted_list[2]=="200+":
                return "4090"

    elif customers_wanted_list[0]=="Valorant":
        if customers_wanted_list[1]=="1080":
            if customers_wanted_list[2]=="60":
                return "3060"

            elif customers_wanted_list[2]=="100":
                return "3060"

            elif customers_wanted_list[2]=="144":
                return "3060"

            elif customers_wanted_list[2]=="200+":
                return "3060 ti"

        elif customers_wanted_list[1]=="2k":
            if customers_wanted_list[2]=="60":
                return "3060"

            elif customers_wanted_list[2]=="100":
                return "3060"

            elif customers_wanted_list[2]=="144":
                return "3060 ti"

            elif customers_wanted_list[2]=="200+":
                return "3060 ti"

        elif customers_wanted_list[1]=="4k":
            if customers_wanted_list[2]=="60":
                return "3070"

            elif customers_wanted_list[2]=="100":
                return "3070"

            elif customers_wanted_list[2]=="144":
                return "3070 ti"

            elif customers_wanted_list[2]=="200+":
                return "3070 ti"

def cpu_needed_for_customers_graphics_card(card):
    '''adds cpu needed to handle customers GPU'''
    #the better the graphics card the better cpu the customer will need to keep computer from bottlenecking
    customers_returned_completed_computer_list=[card]
    if card=="3060":
        return "11th gen intel i5"
        
    elif card=="3060ti":
        return "11th gen intel i5"

    elif card=="3070":
        return"12th gen intel i5"

    elif card=="3070 ti":
        return "12th gen intel i7"

    elif card=="3080":
        return "12th gen intel i7"

    elif card=="3080 ti":
        return "12th gen intel i7"

    elif card=="3090":
        return "12th gen intel i9"

    elif card=="3090 ti":
        return "12th gen intel i9"

    elif card=="4080":
        return "13th gen intel i9"

    elif card=="4090":
        return "13th gen intel i9"



def motherboard_needed(cpu):
    '''finds the optimal motherbaord for cpu'''
    #10th gen is Z590
    #11th gen is Z690
    #12th gen is Z790
    #the motherboards have to be compatable with the chip givin or else the computer will simply not work
    if cpu=="11th gen intel i5":
        return "Z590"

    elif cpu=="12th gen intel i5":
        return "Z690"

    elif cpu=="12th gen intel i7":
        return "Z690"

    elif cpu=="12th gen intel i9":
        return "Z690"

    elif cpu=="13th gen intel i9":
        return "Z790"
        

def ram_needed(customers_wanted_list):
    '''based on the game how much ram does the customer need'''
    #the customer needs more ram when running certain games if the games needs more memory in random generation suc as minecraft
    #It also needs more ram in graphically intense games such as cyberpunk 2077 (great game btw)
    if customers_wanted_list[0]=="Fornite":
        return "16 GB"

    elif customers_wanted_list[0]=="Minecraft":
        if customers_wanted_list[1]=="2k" or "4k":
            return "32 GB"
        else:
            return "16 GB"

    elif customers_wanted_list[0]=="Call of Duty: Warzone":
        return "16 GB"

    elif customers_wanted_list[0]=="Cyberpunk 2077":
        return "32 GB"

    elif customers_wanted_list[0]=="Valorant":
        return "16 GB"


def power_supply_needed(completed_list_no_power):
    '''adds power supply to list based on givin components list'''
    es=80
    card=completed_list_no_power[0]
    cpu=completed_list_no_power[1]
    motherboard=completed_list_no_power[2]
    ram=completed_list_no_power[3]
    #will add scores from components and round up(already calculated motherboard:80)

    #calculating card wattage
    if card=="3060":
        es+=170
    elif card=="3060 ti":
        es+=200
    elif card=="3070":
        es+=220
    elif card=="3070 ti":
        es+=290
    elif card=="3080":
        es+=320
    elif card=="3080 ti":
        es+=350
    elif card=="3090":
        es+=350
    elif card=="3090 ti":
        es+=450
    elif card== "4080":
        es+=320
    elif card=="4090":
        es+=450
    #calculating cpu power draw
    if cpu=="11th gen intel i5":
        es+=224
    elif cpu=="11th gen intel i7":
        es+=224
    elif cpu=="11th gen intel i9":
        es+=224
    elif cpu=="12th gen intel i5":
        es+=150
    elif cpu=="12th gen intel i7":
        es+=190
    elif cpu=="12th gen intel i9":
        es+=240
    elif cpu=="13th gen intel i5":
        es+=180
    elif cpu=="13th gen intel i7":
        es+=253
    elif cpu=="13th gen intel i9":
        es+=253
    #calculating ram
    if ram=="16 GB":
        es+=6
    elif ram=="32 GB":
        es+12
    #finishing power supply
    if es<=450:
        return "650 watt psu"
    elif es<=550 and es>=451:
        return "750 watt psu"
    elif es<=600 and es>=551:
        return "850 watt psu"
    elif es>=601:
        return "1000+ watt power supply"
    
        
        
    
    

    
        
        
    
        
