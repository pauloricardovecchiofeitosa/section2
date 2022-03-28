import time

# functions
def space():
    print("")
    print("")

# main program // call to function
print("")
print("{:^50}".format("\033[4:36m Welcome to trip calculator \033[m"))
space()

totaltopaythebill = float(input("What was the total bill? $"))
serviceadditionpercentage = 8

while serviceadditionpercentage != 10 or 12 or 15:
    serviceadditionpercentage = int(input("What percentage tip would you like to give? [10, 12, or 15?] "))

    if serviceadditionpercentage == 10 or serviceadditionpercentage == 12 or serviceadditionpercentage == 15:
        amountofpeople = int(input("How many people to split the bill? "))

        totalamountwithoutfees = totaltopaythebill * (serviceadditionpercentage / 100)
        totaltopaythebill += totalamountwithoutfees
        totalamountwithoutfees = totaltopaythebill / amountofpeople
        space()

        processing = "P", "R", "O", "C", "E", "S", "S", "I", "N", "G", ".", ".", "."

        for loading in processing:
            print(f'\033[1:32m{loading}\033[m', end=" ", flush=True)
            time.sleep(0.5)

        space()
        print(f'\033[1:32m → Each person should pay: ${totalamountwithoutfees:.2f} ←\033[m')
        space()
        break

    elif serviceadditionpercentage != 10 or serviceadditionpercentage != 12 or serviceadditionpercentage != 15:
        print("")
        print("\033[1:31m Could not understand your answer \033[m")

print("\033[7:31m< FINISHED SYSTEM >\033[m ")
