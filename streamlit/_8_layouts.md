# Layouts

1. ```st.sidebar.title("...")```
    - we create a sidebar with the given title

2. ```st.sidebar.write("...")```
    - put something in the side bar

3. ```st.sidebar.text_input("...")```
    - input box

4. ```st.tabs([])```
    - ```val1, val2... = st.tabs([".." , "..", ".."])```
    - create tabs
    - provide the names of the tab in the list
    - then we can write in each tab:
    - ```with val1:```

5. ```st.columns()```
    - ```val1, val2, ... = st.columns(number)```
    - then we can write in each column as
    - ```with val1:```

6. ```st.container(border=True)```
    - this creates a container with a border
    - we can write text inside it
    - use it with ```with```

7. ```var = st.empty()```
    - this creates an empty element that can be given content dynamically 

8. ```st.expander("label")```
    - this creates a dropdown expander that can show some more details

9. ```st.button("...", help="...")```
    - this creates a hover on the button





