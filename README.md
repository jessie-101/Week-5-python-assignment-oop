# Week-5-python-assignment-oop

Activity 1:

# Base class
class BankAccount:
    def __init__(self, account_number, balance):
        self.account_number = account_number
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        return f"Deposited {amount}. New balance: {self.balance} 💰"

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            return f"Withdrew {amount}. New balance: {self.balance} 💵"
        else:
            return "Insufficient funds ❌"

    def account_info(self):
        return f"Account {self.account_number}, Balance: {self.balance}"


# Derived class
class SavingsAccount(BankAccount):
    def __init__(self, account_number, balance, interest_rate):
        super().__init__(account_number, balance)
        self.interest_rate = interest_rate

    def add_interest(self):
        interest = self.balance * self.interest_rate / 100
        self.balance += interest
        return f"Interest added: {interest}. New balance: {self.balance} 


# Create objects
acc1 = BankAccount("12345", 1000)
acc2 = SavingsAccount("67890", 2000, 5)

print(acc1.account_info())
print(acc1.deposit(500))
print(acc1.withdraw(200))
print(acc2.account_info())
print(acc2.add_interest())


 Activity 2;

class Profession:
    def work(self):
        pass


class Doctor(Profession):
    def work(self):
        return "Treating patients 👨‍⚕️"


class Teacher(Profession):
    def work(self):
        return "Teaching students 👩‍🏫"


class Engineer(Profession):
    def work(self):
        return "Designing and building systems 👷"


# Polymorphism in action
workers = [Doctor(), Teacher(), Engineer()]

for w in workers:
    print(w.work())
