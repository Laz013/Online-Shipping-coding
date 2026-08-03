# Online-Shipping-coding
Bringing the idea of Tax / GST into an online store. 
# The Challenge
You running a global company which is legally registered to collect Tax / GST in different buyer's countries. 
Look at adding Tax / GST from the selected countries of your choice and include it into the total order.
Research the Tax / GST of current countries
Communicate clearly to the client as to what they will be being charged with. 
Display the total with Tax/ GST / Vat

# Countries I have selected - South Africa / Australia / Mexico /  England

country=""

orderTotal=0
totalWithTax=0

#Captured July 2026
# South Africa has a tax rate of 15% 
# Australia has a unified national Goods and Services Tax of 10% GST
# Mexico has a tax rate of 20% 
# England has a tax rate of 16%

stax=.15
gst=.10
mtax=.20
etax=.16

print("Please see the below available countries that you may choose from. ") 

countries = ["South Africa", "Australia","Mexico" ,"England"]
print(countries)

country = input("Please type in the country that you are ordering from," + " from the list available. :")

#Placing a while loop so the user cannot place an order amount in a negative.

orderTotal = float(input("Please enter the total order amount: "))

while orderTotal < 0:
    print("Order total cannot be negative.")
    orderTotal = float(input("Please enter the total order amount: "))

#  we have to change the calculation based on the Country they specified

country = country.strip().lower()

if country == "south africa":
    totalWithTax = orderTotal + (orderTotal * stax)
    print("You will be charged an additional 15% Tax")
    print(f"Total amount: R{totalWithTax:.2f}")

elif country == "australia":
    totalWithTax = orderTotal + (orderTotal * gst)
    print("You will be charged an additional 10% GST")
    print(f"Total amount: ${totalWithTax:.2f}")

elif country == "mexico":
    totalWithTax = orderTotal + (orderTotal * mtax)
    print("You will be charged an additional 20% Tax")
    print(f"Total amount: ${totalWithTax:.2f}")

elif country == "england":
    totalWithTax = orderTotal + (orderTotal * etax)
    print("You will be charged an additional 16% Tax")
    print(f"Total amount: £{totalWithTax:.2f}")

else:
    print("Country not found.")
    
#Smaller coding for the same code above:
#taxRates = {
#     "south africa": 0.15,
#     "australia": 0.10,
#     "mexico": 0.20,
#     "england": 0.16
# }
# country = country.strip().lower()
# if country in taxRates:
#     taxRate = taxRates[country]
#     taxAmount = orderTotal * taxRate
#     totalWithTax = orderTotal + taxAmount
#     print(f"Tax Amount: {taxAmount:.2f}")
#     print(f"Total Due: {totalWithTax:.2f}")
# else:
#     print("Country not found.")
