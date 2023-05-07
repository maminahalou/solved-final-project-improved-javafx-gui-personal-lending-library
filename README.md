Download Link: https://assignmentchef.com/product/solved-final-project-improved-javafx-gui-personal-lending-library
<br>
In this project we will improve our personal lending library tool by (1) adding the ability to delete itemsfrom the library, (2) creating a graphical user interface that shows the contents of the library and allowsthe user to add, delete, check out, or check in an item, (3) using a file to store the library contents sothat they persist between program executions, and (4) removing the 100 item size restriction.Sample RunThe video final.swf on the course website shows a sample run of this program.SuggestionsYou have the freedom to design your program however you want, provided that it meets therequirements and follows good design principles. However, if you would like some ideas of where tostart, they are provided in this section. Modify the Library class to use an ArrayList rather than an array (to eliminate the size limit) Rewrite all of the methods in the Library class that display error messages to throw exceptions Add the following methods to the Library class: public void delete(String title) – Removes the item with this title from the library (the ArrayListof MediaItems) public void save() – Writes all of the items out to the data file library.txt. For each MediaItem,write its title, format, whether or not it is on loan (true/false), who it is loaned to (or null, if noton loan), and the date is was loaned (or null, if not on loan). Write out some weird symbol inbetween each of these things – be sure to pick something that is not likely to appear in a title orsomeone’s name. public void open() – Reads in the data from library.txt, recreates the MediaItems, and puts theminto the ArrayList. When you read in each line, you will need to tokenize it based on whateversymbol you picked. Then create a new MediaItem object and set the fields appropriately. Create a JavaFX LibraryGUI class This class should have a Library object as one of its fields. In the LibraryGUI constructor you willneed to call the library constructor method to initialize this field and then call its open() methodto read in the items from the data file. Use a javafx.scene.control ListView class to display the contents of the library (see Chapter 16 ofLiang, pp. 647-651, as well as <a href="http://www.javafxcookbook.com/home)" target="_blank" rel="nofollow noopener noreferrer">http://www.javafxcookbook.com/home)</a>.The code below shows how to use the ListView control to display list of items(<a href="http://www.javafxcookbook.com/home)" target="_blank" rel="nofollow noopener noreferrer">http://www.javafxcookbook.com/home)</a>. The control takes a data model (a sequence of items) as itsdata source. The code below shows how it is used:ListView {width:w-200height:h-50effect:DropShadow{offsetY:3 offsetX:3}items: for (i in [1..50]) “Cloud {%5s i}”}The snippet above would produce the ListView shown in the following figure: Provide buttons for adding, deleting, checking in, and checking out items Attach action listeners to the buttons that use dialog boxes to get any required information fromthe user and then call the appropriate method in the library. If the user currently has an itemselected in the list, assume this is the item they want to check in/check out/delete.HintsWhen the user has an item in the list selected and they choose to check in, check out, or delete thatitem, you will need to get the item’s title in order to pass it to the appropriate library method. To dothis, you can use the following code:Object selected = list.getSelectedValue(); // gets the selected itemString s = selected.toString(); // converts that to a StringString title = s.substring(0, s.lastIndexOf(“(“)); // extracts the titleString title = title.trim(); // removes any trailing whitespaceYou will need to call the Library class’s save method when the user closes the application.