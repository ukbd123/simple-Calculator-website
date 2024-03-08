(NOTE:Make sure that you link the css file with the same name )
HTML :
<!DOCTYPE html><!--This declaration specifies the document type and version of HTML used in the document -->
<html><!--This tag indicates the beginning of the HTML document. -->
<head><!--This section contains meta-information about the HTML document -->
    <meta name="viewport" content="width=device-width,initial-scale=1.0"><!-- meta tag defines the viewport settings for the document, ensuring that the width of the viewport is equal to the device width and sets the initial zoom level to 1.0.-->
    <title>Calculator Wibsite</title><!--title of the website -->
    <link rel="stylesheet" href="calculator.css"><!--This line links an external stylesheet named "calculator.css" to the HTML document, allowing the document to apply styles defined in that CSS file. -->
</head>
<body><!-- This tag indicates the beginning of the document's body, which contains the visible content of the webpage.-->

<div class="container"><!-- div define a container,It serves as a wrapper for the calculator, applying styles defined in the CSS file. -->
    <div class="calculator"><!--: Inside the container,, which contains the calculator interface. -->
        <form ><!-- This form element wraps the calculator's input elements.-->
            <div class="display"><!--the calculator's display/output will be shown. -->
                <input type="text" name="display"> 
            </div>
            <div>
                <input type="button" value="AC" onclick="display.value =''"><!-- removes everything-->
                <input type="button" value="DE" onclick="display.value = display.value.toString().slice(0,-1)"><!-- (Delete) that removes the last character from the calculator's display when clicked.-->
                <input type="button" value="."  onclick="display.value +='.'"><!-- (decimal point)-->
                <input type="button" value="/"  onclick="display.value +='/'"><!--(division) -->
            </div>
            <div>
                <input type="button" value="7" onclick="display.value +='7'">
                <input type="button" value="8" onclick="display.value +='8'">
                <input type="button" value="9" onclick="display.value +='9'">
                <input type="button" value="*" onclick="display.value +='*'"><!--( multiplication) -->
            </div>
            <div>
                <input type="button" value="4" onclick="display.value +='4'">
                <input type="button" value="5" onclick="display.value +='5'">
                <input type="button" value="6" onclick="display.value +='6'">
                <input type="button" value="-" onclick="display.value +='-'"><!--(subtraction) -->
            </div>
            <div>
                <input type="button" value="1" onclick="display.value +='1'">
                <input type="button" value="2" onclick="display.value +='2'">
                <input type="button" value="3" onclick="display.value +='3'">
                <input type="button" value="+" onclick="display.value +='+'"><!--(addition) -->
            </div>
            <div>
                <input type="button" value="00" onclick="display.value +='00'">
                <input type="button" value="0"  onclick="display.value +='0'">
                <input type="button" value="=" onclick="display.value= eval(display.value)" class="equal"><!--The eval() function in JavaScript is used to evaluate a string of JavaScript code represented as a text string. (equal) -->
            </div>
        </form>
    </div>
</div>
</body>
</html>

CSS:

*{/* This sets default styles for all elements on the page, such as setting margins and padding to zero, specifying the font family, and using the border-box box-sizing model.*/
    margin:0;
    padding: 0;
    font-family: 'Poppins', sans-serif;
    box-sizing: border-box;
 }
    
 
 .container
 {
        width: 100%;/* Sets the width of the container to 100% of its containing element's width.*/
        height: 100vh;/* Sets the height of the container to 100% of the viewport height.*/
        background: #929e9e ;/*background color */
        display: flex;/* Displays the container as a flex container.When an element is designated as a flex container, it enables the use of flexbox layout properties to control the arrangement, alignment, and distribution of its child elements (flex items) along a flex container's main axis and cross axis.*/
        align-items: center;/*Aligns the items (children) of the container vertically in the center. */
        justify-content: center;/*Aligns the items (children) of the container horizontally in the center. */
 }
 
 .calculator{
    background: #443d3d ;/*calcultor color */
    padding: 20px;/*controls the space between the numbers and the calculator borader the bigger the num the smaller the numbers get */
    border-radius: 10px;/* Rounds the corners of the calculator with a border radius*/
 }
 .calculator form input{
    border: 10;/* gives a  border for the input elements. */
    outline: 0;/*Removes the outline (focus indicator) from the input elements */
    width: 60px;/* Sets the width and height of the input elements to 60 pixels each.*/
    height: 60px;
    border-radius: 15px;/*ounds the corners of the input elements with a border radius */
    box-shadow: -8px -8px 15px rgba(255,255,255,0.1),5px 5px 15px rgba(0,0,0,0.2);/*used to add a shadow effect to an element's frame. */
    background: transparent;/* Sets the background of the input elements to transparent. */
    font-size: 20px;/* numbers font size*/
    color: #efe8e8;/*numbers color */
    cursor: pointer;/* Changes the cursor to a pointer when hovering over the input elements.*/
    margin: 10px;/* Adds a margin of 10 pixels around the input elements, providing spacing between them.*/
 }

 form .display{
    display: flex;/* Displays the elements with the class "display" as a flex container.*/
    justify-content: flex-end;/* Aligns the content of the flex container to the end of the main axis (horizontally) to push it to the right.*/
    margin: 20px 0;/* Adds a margin of 20 pixels on the top and bottom of the elements with the class "display".*/
 }
 
 form .display input{
    text-align: right;/*set the entered numbers on right corner  */
    flex: 1;/* Allows the input elements to expand and fill the available space within the flex container.*/
    font-size: 45px;/*  Sets the font size of the text within the input elements to 45 pixels.*/
    box-shadow: none;/* Removes any box shadow from the input elements.*/
 }

 form input.equal
 {
    width: 145px;/*to make the (=)  twice as big to fill the empty space */
 }

