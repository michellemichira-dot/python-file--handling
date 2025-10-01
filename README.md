def modify_content(content):
    """
    Modify file content.
    In this example, convert text to uppercase.
    """
    return content.upper()


def read_and_write_file():
    try:
        # Ask the user for the input file name
        input_filename = input("Enter the name of the file to read: ")

        # Open the file in read mode
        with open(input_filename, "r") as infile:
            content = infile.read()

        # Modify the content
        modified_content = modify_content(content)

        # Create a new output file name
        output_filename = "modified_" + input_filename

        # Write modified content to the new file
        with open(output_filename, "w") as outfile:
            outfile.write(modified_content)

        print(f"✅ File processed successfully! Modified file saved as '{output_filename}'.")

    except FileNotFoundError:
        print("❌ Error: The file was not found. Please check the filename and try again.")
    except PermissionError:
        print("❌ Error: You do not have permission to read this file.")
    except Exception as e:
        print(f"⚠️ An unexpected error occurred: {e}")


# --- Main Program ---
if __name__ == "__main__":
    read_and_write_file()
