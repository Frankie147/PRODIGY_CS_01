def encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            if char.isupper():
                result += chr((ord(char) + shift - 65) % 26 + 65)
            else:
                result += chr((ord(char) + shift - 97) % 26 + 97)
        else:
            result += char
    return result

def decrypt(text, shift):
    return encrypt(text, -shift)

def main():
    message = input("Enter the message: ")
    shift = int(input("Enter the shift value: "))

    encrypted_message = encrypt(message, shift)
    decrypted_message = decrypt(encrypted_message, shift)

    print("\nEncrypted message:", encrypted_message)
    print("Decrypted message:", decrypted_message)

if __name__ == "__main__":
    main()
