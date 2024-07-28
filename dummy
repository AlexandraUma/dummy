import os
import streamlit as st

def create_directory_and_write_file(dir_path, filename, content):
    try:
        # Create the directory if it doesn't exist
        os.makedirs(dir_path, exist_ok=True)

        # Full path for the file
        file_path = os.path.join(dir_path, filename)

        # Write content to the file
        with open(file_path, 'w') as file:
            file.write(content)
        
        st.success(f"File '{filename}' created successfully in '{dir_path}'!")
        return file_path
    except Exception as e:
        st.error(f"Error creating file: {e}")
        return None

def main():
    st.title("File Writing Example")

    # Input fields for directory and file name
    dir_path = st.text_input("Enter directory path:", "/path/to/directory")
    filename = st.text_input("Enter file name:", "sample.txt")
    content = st.text_area("Enter file content:", "This is a sample text file content.")

    if st.button("Create File"):
        file_path = create_directory_and_write_file(dir_path, filename, content)

        if file_path:
            # Provide a download button for the created file
            with open(file_path, "rb") as file:
                st.download_button(
                    label="Download File",
                    data=file,
                    file_name=filename,
                    mime="text/plain"
                )

if __name__ == "__main__":
    main()
