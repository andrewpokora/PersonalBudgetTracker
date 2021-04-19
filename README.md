# Read Me first

19 April 2021 Revision: 1.0

## Overview

PersonalBudgetTracker is a simple personal budget tracker to track your finances. To work with it, you need FileMaker version 14 or higher.

Please keep in mind that I started out making this tracker as a pet project, for my own pleasure and my personal goals. Perhaps my perspective on how to account for personal finances is different from yours. This is normal. 

Also, I wanted to keep the application as simple as possible. Therefore, it lacks some functions (complex, relatively laborious, but rarely used by me) that are in other systems. I have not tried to make the best product of all time, suitable for everyone. I did it primarily for myself - on my weekends and in my free time. Perhaps in the future, I will add some new features to this project. This is all the more likely the more good responses I get. So, follow my profiles on social networks for news.

Please note that the main reporting period is the month. This is not always the case in the real world, and it is not always convenient - but, again, this is a SIMPLE tracker. Perhaps later, in the future, I will add the ability to build reports for an arbitrary period. Perhaps it will be a very distant future.

## Content

- Credentials
- Getting Started
- Settings
- Accounts
- Categories
- Currencies
- Rates
- Transactions
- Budget
- Planner
- Reports
- Other things
- Contacts

## Credentials

Login = Admin
Password = 12345

After you open the file firstly, you will be prompted to change your password.

## Getting Started

The file contains several test transactions, accounts, categories, and the like. This allows you to quickly familiarize yourself with how it works and understand if it is right for you. Also, you may find it easier to change existing categories and accounts than to create new ones. After reviewing, you can delete all test data and add your own from scratch.

However, to enter transactions and receive reports, you must have specified the following entities:
- Currencies - account currency. In my case, I account for multiple currencies. You can only work with one currency - but it must be created.
- Accounts - eg bank account, credit card, just money in your pocket.
- Categories - categories of expenses and income. For example - food, or salary.

It is preferable to create them in that order.

Once opened, the file always opens the Dashboard layout. This is a simple layout that contains only two charts - how much income the user has in the current month and how much they spend.

## Settings

In this layout, you see only four buttons. Below is a description of each of them.

### Get ReadMe
Get this ReadMe.md file. It will be exported to your desktop. You can open it in any text editor, but it's better to use a markdown-enabled editor.

### Profile of developer
Open developer profile in a browser. This will help you contact me.

### Delete Sample Data w / o Categories
Delete all sample data excluding categories. Categories will not be deleted! This procedure has no rollback! After the test data is deleted, the button will no longer be active.

### Delete All Data with Categories
Remove everything including categories. This procedure has no rollback! After the test data is deleted, the button will no longer be active.

### Why I have 2 buttons for deleting sample data instead of 1?
I did this because adding categories personally seems to me quite boring and annoying - therefore, it always seemed easier to me to slightly edit existing ones than to introduce them completely from scratch. Therefore, the user might want to delete all test data - but leave the categories.

## Accounts

To make transactions, you need accounts. Money does not exist on its own - it can be in your pocket, on your card, on your account, and so on. Note that the invoice has the attribute Currency.

You cannot delete an account if there are transactions for it.

## Categories

Here you can enter categories for both expenses and income. Also, you can set the so-called. Parent category. For example, you created a Hobby category, type - expenses, and did not select anything for it as a parent. In this case, this is the parent category. Then, you created the Steam Games category, the type is expenses and selected Hobbies as the parent category for it. Thus, you have the following hierarchy:

Expenses
 Hobby
  Steam Games

You cannot delete a category if transactions exist for it. First, you need to delete or modify these transactions.


## Currencies

You can use multiple currencies for your budget. For example, pocket money in dollars, an account or a card in euros. Each account or transaction can be attributed to one, and only one, currency. However, you can set one currency as Primary. In this case, if you have set currency rates, you can see all transactions and all account balances in this currency. They will be recalculated automatically.

You cannot delete the currency associated with an account for which transactions have already been created.

## Rates

Someday I will make automatic retrieval of currency rates using the REST API. Someday - but not today. Today, if you use several currencies, you need to set the rate of the second currency in relation to the main one to display the data correctly.

## Transactions

Shows transactions on your accounts. Allows you to add, edit or delete transactions.

### Create a transaction

Click the New Transaction button.

The date and time of the transaction will be set automatically and are subject to change. Please note - if you click on the calendar symbol on the left, the date will be set to the current one.

Select the type of transaction - Income, Expenses, Transfer (between your accounts)

Select the account for which the transaction will be created. After the account is selected, the balance of funds on this account in its currency will be displayed next to it.

If we are talking about a Transfer, you will need to select your account to which you are making the transfer. For example - transfer from the left pocket to the right one. Internal transactions do not appear in expenses and income, because they are not in fact. Orthodox accountants will disagree with me - so please don't show them this document.

Enter the amount. If you make expenses, there is no need to put a minus, it will be indicated automatically later.

Select a category. You can use the filter at the top left of the window to quickly find the category you want. Just click on the selected category - it will change its colour - and confirm your choice.

You can add a payer or notes if needed.

Select the status of the transaction - confirmed, pre-authorization, planned.

Confirm the details and close the window.

### Duplicate a transaction

Click the button on the right side of the line to duplicate the transaction. A new window will open to confirm or edit the data.

### Edit a transaction

Click the button on the left side of the row to open the window and change the transaction data.

### Send the transaction to budget.

If this transaction is repeated regularly - you can click this button and it will be taken into account in your planned budget.

### Delete transaction

Just delete this entry. In the case of a Transfer, both related transactions will be deleted.

### Filters

Click the button and select the criteria by which you want to display your transactions. For example - select account, transaction type and period. Also, you can choose whether to show all transactions in the main currency or in different ones (if you have more than one currency). Also, you can choose whether to display domestic transfers or not.

### Reconciliation

Click the button and select the required function from the drop-down list. Verification is done manually - just put a checkbox in the transaction that is verified.

### Quick filters.

Just select This year, last month or this month to see transactions for that period. Please note - the Previous Month means LITERALLY the previous month, that is, the month that was BEFORE the current one. If you need to view transactions, for example, two months ago, just use the Filter. 

Alternatively, you can do a quick search using the box at the top left of the layout.

## Budget

These are slightly modified categories. For example, you have a Steam Games category. You can set its type - expenses (if you just play in the evenings), or income (if you are a developer and receive money from the sale of this game). You can set a goal for this category - for example, $ 100. That way, you'll see how much more you can spend - or how much more you need to earn this month.

To the right of the category, you can see a simple progress bar that shows how much more you can spend - or how much more you need to earn if it's in the Income category.

To add a category to the budget, you need to click the Select Categories button. After that, you can check the categories you need with a check-box.

Please note - as soon as you put the check-box, the Repeat and from what time fields will be automatically filled in. They are needed for the correct calculation of the Forecast.

To remove a category from the budget, you need to click the Select categories button again and uncheck the checkbox.

## Planner

Allows you to make entries in Transactions that will not be taken into account in transaction statistics, but will be taken into account in the forecast. For example, you plan to buy a new motorcycle by the end of the year and want to estimate in advance the size of the hole this purchase will cut in your budget. Since this is an irregular purchase (you probably don't buy a bike every month, although who knows), it shouldn't be budgeted (but expenses for gasoline and service are regular and they definitely have a place in the budget). So what do you do with the bike? You know the amount, you know approximately the date of purchase. You enter this transaction into Planner. It will not appear on expense reports or your balance sheet - because you haven't bought anything yet. But it will be taken into account in the planner - and you can then see how it affects your cash holdings.

You can edit this transaction and change its type - for example, to Confirmed. After that, you will see it in Transactions, and it will be displayed in reports as real.

## Reports

Just a set of graphs that allow you to visualize some data. I know FileMaker's built-in charts are terrible - and you know that. Someday in the future, I will make beautiful interactive graphics in the web viewer. When realties - but not today. Today it was interesting for me to do everything with regular means.

### Income

Shows how much funds were received in a specific month. Select the year and month using the buttons on the left.

### Top 3 Income

Identifies the top 3 earning categories and shows the change in your income for those categories for last year.

### Expense

Shows how much money was spent in a specific month. Select the year and month using the buttons on the left.

### Top 10 Expense

Identifies the top 10 expense categories and shows the change in expenses for these categories for last year.

### Budget Chart

Simple chart for your budget.

### Budget Control

Compares your budget plans to ruthless reality. On the left - how much more you can spend if you stick to the budget, on the right - how much you have already spent. Only the current month is displayed.

### Accounts

A list of your accounts with an indication of the balance on each in the BASIC currency. Allows you to quickly estimate how much money you have in general and whether you can order yourself a pizza today - or do you still need to stop programming and find yourself, finally, a normal job.

### Balance

Compares your income and expenses monthly.

### Forecast

To be honest, it was all for the sake of this, but the implementation was not as impressive as I had hoped. Let's say you have some amount in your accounts. Let's also assume that you have planned your budget in terms of expenses and income. Let's say that you have planned your large (or not so) purchases and entered them into the Planner. Thus, you can get a forecast for each of the next 12 months, based on this data:

The balance on your accounts at the end of the previous month + your income for the current month (budget and planned) - your expenses for the current month (budget and planned).

And so starting from this month for a year ahead.

This way, you can see how your spending or income plans affect your account balances and better plan for your future.

## Contacts

You can express your gratitude, indignation or constructive wishes to me using the following contacts:

Email: ap@custom-apps.pro

My profiles:
Linkedin: https://www.linkedin.com/in/andrewpokora/
Github: https://github.com/andrewpokora
Twitter: https://twitter.com/andrewpokora

Also, you can say nothing, but just buy me a coffee :) 
https://www.buymeacoffee.com/andriipokora
