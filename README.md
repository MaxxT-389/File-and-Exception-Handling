# File-and-Exception-Handling

def modify_text(content):
    """Modify the text - here, converting to uppercase."""
    return content.upper()  # Modify as needed

def read_and_modify_file():
    """Reads a file and writes a modified version to a new file, handling errors."""
    filename = input("Enter the filename to read: ")

  try:
        with open(filename, "r") as file:
            content = file.read()  # Read the file

        modified_content = modify_text(content)  # Modify content

        new_filename = "modified_" + filename
        with open(new_filename, "w") as new_file:
            new_file.write(modified_content)  # Write to new file

        print(f"Modified content saved to: {new_filename}")

    except FileNotFoundError:
        print("❌ Error: The file does not exist.")
    except IOError:
        print("❌ Error: Unable to read the file.")

read_and_modify_file()
