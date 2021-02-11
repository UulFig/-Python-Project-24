# -Python-Project-24
# #24 Caesar Cipher 1.0

print("Welcome to Cipher text encode and decode!\n")

def main():

    alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm',
                'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
    def encrypt():
        cipher_text = ""
        plain_text = input("Type your message:\n").lower()
        shift_amount = int(input("Type the shift number:\n"))
        if shift_amount > 26:
            print("You should use numbers between '0 ~ 26'")
            return main()

        for letter in plain_text:
            position = alphabet.index(letter)
            new_position = position + shift_amount
            if new_position > 25:
                new_position = new_position - 26
            new_letter = alphabet[new_position]
            cipher_text += new_letter
        print(f"Your new encode letter is {cipher_text.title()}\n")

    def decrypt():
        cipher_text = ""
        plain_text = input("Type your message:\n").lower()
        shift_amount = int(input("Type the shift number:\n"))

        for letter in plain_text:
            position = alphabet.index(letter)
            new_position = position - shift_amount
            if new_position < 0:
               new_position = new_position + 26
            new_letter = alphabet[new_position]
            cipher_text += new_letter
        print(f"Your new decrypted letter is {cipher_text.title()}\n")


    answer = input("Do you want do encode or decode?\n").lower()
    if answer == "encode":
        encrypt()
    elif answer == "decode":
        decrypt()
    else:
        print("Sorry, i don't get it. You should use  'encode' or 'decode'\n")
        return main()

    def yes_no(message):
        while True:
            yes_no = input(message).lower()
            if yes_no == "yes":
                return True
            elif yes_no == "no":
                return False
            else:
                print("Please use 'yes' or 'no'\n")

    while True:
            if yes_no("Do you want try again?\n"):
                return main()
            else:
                print("Good bye!")
                quit()


main()
