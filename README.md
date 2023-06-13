# multimeadia-app

## 1.) Two additional Feature that I added are File Sorting and Searching:

### File Sorting: 
The file sorting feature allows users to sort their files based on different criteria such as name, size, type, or date. Users can select the sorting criteria and order (ascending or descending) from the dropdown menus. Upon clicking the "Sort" button, the files will be rearranged according to the selected criteria and order.

### File Search: 
The file search feature enables users to search for specific files by name or type. Users can enter their search term in the search input field and click the "Search" button. The app will filter the files based on the search term, displaying only the files that match the search criteria.


## 2.) Reasons for choosing these two features:

By providing sorting options, users can easily change the order in which files are displayed, making it more convenient for them to find the files they need and also there are several
sorting criteria like date which can help easily locate files when user forgot the name.

Implementing a search functionality allows users to quickly locate specific files by searching for file names or types. It eliminates the need for manual scanning or scrolling through a long list of files, saving users time and effort.

Overall, these functionalities enhance the usability and efficiency of our file manager, allowing users to organize and locate files more effectively.

## 3.) How these two functionalities work:

To add these functionalities I used the useState hook present in react
three new states were added to change the states of myFile and re-render the component:
const [sortCriteria, setSortCriteria] = useState("name");
const [sortOrder, setSortOrder] = useState("asc");
const [searchTerm, setSearchTerm] = useState("");

### sortCriteria state:
It holds the value of the selected sorting criteria, such as "name", "size", "type", or "date".
It is updated whenever the user selects a different sorting criteria from the dropdown menu using the onChange event handler.

### sortOrder state:
It stores the selected sorting order, either "asc" (ascending) or "desc" (descending).
It is updated whenever the user selects a different sorting order from the dropdown menu using the onChange event handler.

### searchTerm state:
It stores the search term entered by the user in the search bar.
It is updated whenever the user types in the search bar using the onChange event handler.

Two functions which handles the logic for searching and sorting:

### handleFileSorting function:
This function is called when the user clicks the "Sort" button after selecting the sorting criteria and order.
It retrieves the selected sorting criteria (sortCriteria) and order (sortOrder) from the state.
Based on the selected criteria, it applies the appropriate sorting logic to the myFiles array using JavaScript's sort() method.
The sorting logic compares the files based on the chosen criteria (e.g., name, size, type, or date) and the selected order (ascending or descending).
After sorting the array, the function updates the myFiles state using the setMyFiles function, causing the app to re-render and display the sorted files.

### handleFileSearch function:
It retrieves the current search term from the searchTerm state.
It filters the myFiles array based on the search term using JavaScript's filter() method.
The filtering logic checks if the file's name or type contains the search term (case-insensitive match).
The filtered array is then set as the new value for the myFiles state using the setMyFiles function, causing the app to re-render and display only the matching files.

I added the two buttons for sorting and Searching:

### Sort button: 
The code uses the handleFileSorting function to sort the files. It first creates a copy of the myFiles array. Then, based on the selected sorting criteria, the array is sorted using appropriate comparison logic.

### Search button: 
The code utilizes the handleFileSearch function to filter the files based on the search term. It creates a new array called filteredFiles by applying the filter method on the myFiles array. The filter method checks if the file name (converted to lowercase) includes the search term (also converted to lowercase). The resulting filteredFiles array is then set using the setMyFiles function, displaying only the matching files.
