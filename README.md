
# CV Generator

This project is a dynamic CV generator. You fill all the infos that you want in your CV and it's transformed in an HTML structure that allows you to generate a PDF by using the `print` function of the browser

## Structure of the project

The project has the following files and folders:
- `index.html` - imports the style and script that generate the CV
- `index.css` - the default theme for the CV. If you don't want to create an specific theme for your CV, you will have a simple but clean layout
- `data.js` - contains all the information that will be used in your cv. 
- `index.js` - use vanilla JS to generate the CV Structure based on the infos filled at the *data.js* file

## Running the project
Since this use JS modules, it's necessary to use a server to run the code. I'm currently using `live-server`, because it's simples and fast. 
To use it, you'll have to install it globally using `npm install live-server -g` and then, in the project folder, run `live-server`. This will open the 8080 port in your browser so you can see your CV as a webpage.

## Data.js explained 
At this file, you can add:
- *theme* - is used to import your specific CSS, to add the style that you want to the elements
- *language* - in case you want to have your CV in more than one language
- *header* - allows you to add the logo and infos that will be displayed at the header of your CV
- *data* - this is the main content of your CV. Your goals, skills and experience must be in this array

### Header infos
In your `data.js` file you'll be able to set your personal infos that will appear at the header of the CV. So, at the `header` const you'll add the following keys to the object:
- *image* - if you want to add a picture or your logo to the header
- *alt* - it's mandatory if you add an image
- *divider* - it's optional, in case you want to add a `hr` element between the image and the content
- *personalInfos* - it's an array of object with the `type`, `content` and `href` keys. Type must be "text" or "link"; content is the text that the reader will see and "href" is mandatory for "link" types of content 

### Data infos
You will add your goals, skills and experience at this file too. Each section must be a differente object, in wich you can use three types of structure:
- *content as string* - if you set a string for the `content` key, the text will be displayed in a `p` element
- *content as an array of strings* - this will create a bullet list using `ul` and `li` elements
- *content as an array of objects* - this is recommended for experience section, because you can add three keys: title, date and content.
    - all the keys are optional, so this structure can be used with just title and content, or title and date, or even with just date and content, it's up to you!