# CodeAlpha_Stockportfoliotracker
A simple Stock Portfolio Tracker built with Python. It uses a predefined dictionary of stock prices, accepts stock names and quantities from the user, calculates the total investment value, and optionally saves the result to a text file. This project demonstrates dictionaries, arithmetic, input/output, and file handling.
# Stock Portfolio Tracker

# Hardcoded stock prices
stock_prices = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOGL": 150,
    "AMZN": 200,
    "MSFT": 400
}

print("===================================")
print("       STOCK PORTFOLIO TRACKER")
print("===================================")

print("\nAvailable Stocks:")
for stock in stock_prices:
    print(stock, "- $", stock_prices[stock])

# Get number of different stocks
number = int(input("\nHow many stocks do you want to buy? "))

total_investment = 0

# Take stock name and quantity from user
for i in range(number):

    stock_name = input("\nEnter stock name: ").upper()

    if stock_name in stock_prices:
        quantity = int(input("Enter quantity: "))

        price = stock_prices[stock_name]
        investment = price * quantity

        print("Price per share: $", price)
        print("Investment value: $", investment)

        total_investment = total_investment + investment

    else:
        print("Stock not available!")

# Display total investment
print("\n===================================")
print("Total Investment: $", total_investment)
print("===================================")

# Save result in a text file
save = input("\nDo you want to save the result? (yes/no): ").lower()

if save == "yes":
    with open("stock_portfolio.txt", "w") as file:
        file.write("Stock Portfolio Tracker\n")
        file.write("-----------------------\n")
        file.write("Total Investment: $" + str(total_investment))

    print("Result saved to stock_portfolio.txt")
else:
    print("Result was not saved.")

print("\nThank you for using Stock Portfolio Tracker!")
