## Hi there 👋
def modify_text(text):
    # Example modification: reverse each line and convert to uppercase
    lines = text.splitlines()
    modified_lines = [line[::-1].upper() for line in lines]
    return "\n".join(modified_lines)

def main():
    filename = input("Enter the filename to read: ")

    try:
        with open(filename, "r") as file:
            content = file.read()
    except FileNotFoundError:
        print(f"❌ Error: The file '{filename}' was not found.")
        return
    except IOError:
        print(f"❌ Error: The file '{filename}' could not be read.")
        return

    modified_content = modify_text(content)

    output_filename = "modified_" + filename
    try:
        with open(output_filename, "w") as file:
            file.write(modified_content)
        print(f"✅ Success! Modified content written to '{output_filename}'.")
    except IOError:
        print(f"❌ Error: Could not write to '{output_filename}'.")

if __name__ == "__main__":
    main()







