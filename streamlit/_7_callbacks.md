# Callbacks

- use callback functions to update st.session_state before the app reruns. 
- This helps us avoid unexpected behavior when navigating between pages or changing the app's state.
- the callback run before any other code run on the next rerun.

- Example:
- without callback
```
import streamlit as st

if "page" not in st.session_state:
    st.session_state.page = "Home"

st.button("Play Game")

if st.session_state.page == "Home":
    st.session_state.page = "Game"  # Problem!

st.write(st.session_state.page)

```
- The page changes to "Game" automatically when the app runs, even without clicking the button.

- with callback 

```
import streamlit as st

if "page" not in st.session_state:
    st.session_state.page = "Home"

def go_to_game():
    st.session_state.page = "Game"

st.button("Play Game", on_click=go_to_game)

st.write(st.session_state.page)
```
- The page stays "Home" until you click the button. Then the callback changes it to "Game".
- args=() is also the argument that is given if the callback function need some arguments also
    - provide tuple values

