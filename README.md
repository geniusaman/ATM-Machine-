# ATM-Machine-
class Atm():

    def __init__(self):
        self.pin =""
        self.balance = 0
        self.menu()

    def menu(self):
        user_input = input('''
                        1. Enter 1 to create a pin :
                        2. Enter 2 to Deposite :
                        3. Enter 3 to withdraw :
                        4. Enter 4  to Check balance :
                        5. Enter 5 to Exit :
                        ''')
        if '1' in user_input :
          self.Create_pin()
        elif '2' in user_input:
            self.deposite()
        elif '3' in user_input :
            self.Withdraw()
        elif '4' in user_input :
            self.Check()
        else  :
            print('Bye')
            exit()

        return self.menu()


    def Create_pin(self):
        self.pin = input('Enter PIN : ')
        print('Scuessfully Created pin')

    def deposite(self):
        EN = input('Eneter your PIN number : ')
        if EN == self.pin:
            amount = int(input("Eneter Amount : "))
            self.balance = self.balance + amount
        else :
            print('Invalid PIN')

    def Withdraw(self):
        EN = input('Enter your PIN number : ')
        if EN == self.pin:
            eN = int(input('Eneter Amount :'))
            if eN < self.balance:
                self.balance = self.balance - eN
            else:
                print('Insufficent Balance')

        else:
            print("Invalide pin")

    def Check(self):
        EN = input('Enter the PIN : ')
        if EN == self.pin:
            print(self.balance)
        else:
            print('Invalid pin')


Aman = Atm()
