# STREAMLIT COMMANDS

- ```st.write()```
    - this function is used to add anything to the web page
    - it can write all the python objects
    - it automatically determine how to write that based on its type
    - magic command
        - anything we pass, it figure out how to write it, throw that on screen
    - we can also write any expression without the st.write() function and it will automatically be shown on the screen

- ```st.button()```
    - create a button
    - provide a string that is shown as the name of the button
    - ```st.button("Name")```

### Text Elements

- These elements are for rendering text

1. ```st.title("Title")```
    - render the title

2. ```st.header("...")```
    - render the header

3. ```st.subheader("...")```
    - render the subheader

4. ```st.markdown("...")```
    - render the markdown text provided

5. ```st.caption("...")```
    - render caption text

6. ```st.code()```
    - this is used to render codes on the screen
    ```
    st.code(<code> , language = "<language_name>")
    ```

7. ```st.divider()```
    - shows the horizontal line on the screen

### Putting images on the screen

- ```st.image("...")```
    - render the image on the screen
    - provide the image path
    - can provide the width as an argument also

### Data Elements

- these elements are for rendering data
- can do with python pandas data frames

1. ```st.dataframe()```
    - this is specifically used for pandas dataframe
    - pass a pandas dataframe object to it

2. ```st.data_editor()```
    - we can edit the dataset
    - if we use this with a variable, everytime we change the values of the dataset
    - new values will be saved
    - Entire python file reruns again when we make the changes.

3. ```st.table()```
    - render the dataset as a simple table

4. ```st.metric(label = "" , value = "")```
    - used to print different information about tables
    - in the value argument, provide the operation on the dataframe.

5. ```st.json()```
    - show the provided dictionary as the json format

### Chart Elements

1. ```st.area_chart()```
    - creates an area chart
    - require a dataset object as argument.

2. ```st.bar_chart()```
    - creates a bar chart
    - require a dataset object as argument

3. ```st.line_chart()```
    - creates a line chart
    - require a dataset object as argument.

4. ```st.scatter_chart()```
    - creates a scatter chart
    - require a dataset object as argument.

5. ```st.map()```
    - it creates a geolocation map
    - Latitude and longitude are imaginary grid lines used to find any exact location on Earth.
    - Latitude: Run horizontally east-west and are parallel to each other.
        - Measure how far north or south you are from the Equator (0°)
        - Goes from 0° at the Equator up to 90° North at the North Pole and 90° South at the South Pole.
    - Longitude: Run vertically north-south and meet at the poles.
        - Measure how far east or west you are from the Prime Meridian (0°), which passes through Greenwich, England.
        - Goes from 0° to 180° East and 0° to 180° West.
    - Written as latitude first, then longitude
    - require two columns (name: lat and lon)

6. ```st.pyplot()```
    - plot the matplotlib charts
    - fig , ax = plt.subplots()
    - ```ax.plot(<column> , <column>)```
    - st.pyplot(fig)

### Form elements

```
with st.form(key="..."):
    # form elements
```
- we have written the with statement first and then put the form elements inside it.
- This avoid the issue of constantly rerunning the script evertime some form elements get changed.
- only when we have press the submit option, then it collect all the information from the form and then rerun the python file
- the **key=""** argument provides a unique identification to the form.
- So the form handle its own internal state.

1. ```st.text_input("label")```
    - provide a text input box with a label
    - can also provide the placeholder="..." argument

2. ```st.selectbox("label",[])```
    - provides a list of options to select from.
    - Give the options in a list

3. ```st.date_input("label")```
    - takes date as input
    - if we need to increase the range of the data
    - has two arguments max_value= and min_value=
    - give these arguments the variables
    ```
    from datetime import datetime
    min_date = datetime(1990,1,1)
    max_date = datetime.now()

4. ```st.text_area("label")```
    - used to display a multi-line text input field
    - placeholder and height are other arguments that can be provided.

5. ```st.form_submit_button("label")```
    - this is to submit the form
    - it is required
    - ```use_container_width=True```
        - is a parameter that makes the button stretch to fill the entire width of its parent container, rather than shrinking to fit just the size of the text 

- To check if all the fields are filled:
```
submit = st.form_submit_button()

if submit:
    if not all(form_values.values()):
        st.warning("...")

    else:
        st.balloons()
        st.write()
    
```

- ```st.success("")```
    - can be written in the else of the form.

- we can also put the if statement right below the submit button as when we press submit then the application rerun and the value of the submit button becomes True. 
    - So the condition is handled after we press the submit.

- inside the form if we have written some code that do the dynamic update (means as we enter a value in the field, we want something to happen), it will not work until you press submit
- In these cases we use session state.

- 6. ```st.number_input("label")```
         - Takes only number as input.
         - can also provide limits to the number

- ```st.file_uploader("label", type=["pdf"])```
         - can be used to take files as input



