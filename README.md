def encrypt(text, shift):
    result = ""
    for i in range(len(text)):
        char = text[i]
        if char.isupper():
            result += chr((ord(char) + shift - 65) % 26 + 65)
        elif char.islower():
            result += chr((ord(char) + shift - 97) % 26 + 97)
        else:
            result += char
    return result

def decrypt(text, shift):
    return encrypt(text, -shift)

message = input("Enter the message: ")
shift_value = int(input("Enter the shift value: "))

encrypted_message = encrypt(message, shift_value)
print(f"Encrypted Message: {encrypted_message}")

decrypted_message = decrypt(encrypted_message, shift_value)
print(f"Decrypted Message: {decrypted_message}")
