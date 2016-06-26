#This code is to calculate the tax charged to the country.

print('What is your order total?')
orderTotal = input()
print('What country are you from?')
country = input().upper()
if country == 'CANADA' :
    print('And what province are you from?')
    province = input().upper()
#Alberta charge .05% General sales Tax
    if province == "ALBERTA" :
        taxedTotal = int(orderTotal) * 1.05
#Ontario, New Brunswich, Nova Scotia charge .13% Harmonized sales tax
    elif province == 'ONTARIO' or 'NEW BRUNSWICK' or 'NOVA SCOTIA' :
        taxedTotal = int(orderTotal) * 1.13
#All other provinces charge .06% provincial sales tax + .05% GST tax
    else : 
        taxedTotal = int(orderTotal) * (1.06 + .05)
elif country == 'USA' :
    print("And what state are you located in? (Currently only works for Califoria or New York because I'm lazy as shit.")
    state = input().upper()
    if state == 'CALIFORNIA' :
        taxedTotal = int(orderTotal) * 1.075
    elif state == 'NEW YORK' :
        taxedTotal = int(orderTotal) * 1.07
#Every other place will be tax free because as I stated -- I'm lazy as shit.
    else :
        taxedTotal = orderTotal 
else :
    print("Sorry, I am unable to calculate the sales tax for your country.")

print('Total cost for your purchase will be $' + str(int(taxedTotal)) + '.')
