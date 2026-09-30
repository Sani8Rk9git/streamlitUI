# Chatbot related commands

- ```st.chat_input("...")```
    - displays a chat input widget, enabling users to submit text, and optionally attach files or record audio directly into a Streamlit application

    - When a user types a message and clicks the send icon (or presses Enter), Streamlit reruns the app. The widget returns the entered string value during that rerun; otherwise, it returns None

```
st.chat_input(
    placeholder="Your message", 
    key=None, 
    max_chars=None, 
    disabled=False, 
    on_submit=None, 
    height="content", 
    accept_file=False, 
    accept_audio=False
)

```

- Automatically pins to the bottom of the main app body by default (or can be placed inline inside containers). It triggers a script rerun when submitted.


- ```st.chat_message()```

    - a Streamlit function that inserts a chat message container into your app to render chat bubbles for users, assistants, or custom authors.

    - Syntax:
    ```
    st.chat_message(name, *, avatar=None, width="stretch")
    ```

    - name: Sets the author name and accessibility label. Use "user", "assistant", "ai", "human", or any custom string. Standard names trigger preset styling and icons.
    - avatar: Defines the displayed icon. Supports single emojis, image URLs, Material symbols (:material/icon_name:), or "spinner".
    - width: Controls container width ("stretch", "content", or an integer)

- Renders inline wherever you call it in your script layout, typically inside a loop iterating through past chat history.