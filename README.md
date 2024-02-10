# Decode Function 
Implementation of decode function in python syntax 


def decode(message_file):
    # Read the content of the file
    with open(message_file, 'r') as file:
        lines = file.readlines()

    # Create a dictionary to store the words corresponding to each number
    pyramid_dict = {}
    
    # Iterate through each line in reverse order
    for i, line in reversed(list(enumerate(lines, start=1))):
        _, word = line.split()
        pyramid_dict[i] = word.strip()

    # Extract the words corresponding to the pyramid's base numbers
    decoded_words = [pyramid_dict[i] for i in range(1, len(pyramid_dict) + 1)]

    # Join the decoded words into a string
    decoded_message = ' '.join(decoded_words)

    return decoded_message

# Example usage:
message_file = 'path/to/your/file.txt'
result = decode(message_file)
print(result)
