# Drawdown Close

Drawdown Close is a custom indicator developed by the Forex Robot Easy Team. Its main purpose is to monitor the drawdown of a trading account and automatically close open orders when the drawdown exceeds a predetermined percentage limit.

## Input Parameters

- **Balance**: The current account balance in USD.
- **DrawdownPercent**: The predetermined percentage limit for drawdown against the balance.
- **FloatingPL**: The floating Profit & Loss.

## Global Variables

- **g_CloseOpenOrders**: A boolean flag to indicate if open orders should be closed.

## Custom Indicator Initialization Function

The `OnInit()` function is called when the indicator is initialized. It subscribes to the necessary events, such as the timer event and the custom event for order closure.

## Custom Indicator Deinitialization Function

The `OnDeinit(const int reason)` function is called when the indicator is deinitialized. It unsubscribes from the events to prevent any unwanted actions.

## Timer Event Function

The `OnTimer()` function is triggered every second by the timer event. It calculates the drawdown against the balance by subtracting the balance from the current equity and dividing it by the balance, then multiplying by 100. If the drawdown exceeds the specified limit, it sets the `g_CloseOpenOrders` flag to true and triggers the custom event for order closure.

## Custom Event Function for Order Closure

The `OnCustom(const int eventId)` function is called when the custom event for order closure is triggered. If the `g_CloseOpenOrders` flag is true, it loops through all open orders and closes the ones that match the current symbol and magic number. Finally, it resets the `g_CloseOpenOrders` flag.

## Product Description

Drawdown Close is a powerful tool for trade management that helps traders protect their accounts from excessive drawdown. With its automated order closure feature, it allows traders to define a drawdown percentage limit, and when that limit is exceeded, all open orders are closed to prevent further losses.

This code serves as a sample implementation of the Drawdown Close functionality. It can be used as a reference to understand how the indicator works. However, please note that Forex Robot Easy is not the official developer of this product. To find the official developer and obtain the complete product, please visit the official MQL5 website.

For detailed reviews and trading results of the Drawdown Close indicator, please visit [Forex Robot Easy](https://forexroboteasy.com/forex-robot-review/drawdown-close-review-smart-forex-ea-for-trade-management/).
