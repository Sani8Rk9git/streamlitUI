# Multi-page apps

- in the Main folder 
- create a Home.py that can be your main file (can also choose any other name)
- create a folder pages that can contain other pages of the applications
- Now as soon as the pages are rerendered, the state will be destroyed
    - so we need to use session state to make the content persist through the different page pressess

- we can change the title of the page at the top of the browser:
    - ```st.set_page_config(page_title="...")```

