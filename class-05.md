# HTML Images CSS Color & Text

## Images

*A picture can say a thousand words, and great images help make the difference between an average-looking site and a really engaging one.*

### What images should Be like ?
1. Be relevant
2. Convey information
3. Convey the right mood
4. Be instantly recognisable
5. Fit the color palette

**If you are building a site from scratch, it is good practice to create a folder for all of the images the site uses.**

### How to adding image?
To add an image into the page you need to use an \<img> element. This is an empty element (which means there is no closing tag). It must carry the following two attributes:

*src*
This tells the browser where it can find the image file. This will usually be a relative URL pointing to an image on your own site. 
*alt*
This provides a text description of the image which describes the image if you cannot see it.
*title*
You can also use the title attribute with the \<img> element to provide additional information about the image. Most browsers will display the content of this attribute in a tootip when the user hovers over the image.
*Example:*

```
<img src="images/quokka.jpg" alt="A family of
quokka" title="The quokka is an Australian
marsupial that is similar in size to the
domestic cat." />
```

### Where to Place Images in Your Code ?

1. **before a paragraph**
The paragraph starts on a new line after the image.
2. **inside the start of a paragraph**
The first row of text aligns with the bottom of the image.
3: **in the middle of a paragraph**
The image is placed between the words of the paragraph that it appears in.

### There are three rules for creating images:

rule                             | details
---------------------------------|---------------------------------------
Save images in the right format  |Websites mainly use images in jpeg, gif, or png format
Save images at the right size    |You should save the image at appear on the website
Use the correct resolution       |saving images at a higher resolution results

## Colors
### You can specify any color in CSS in one of three ways:

![rgb](https://image.slidesharecdn.com/presentitudepresentscolortheorypart3-160427151921/95/the-4-important-color-models-for-presentation-design-16-638.jpg?cb=1461776860)

* **rgb values**
These express colors in terms of how much red, green and blue are used to make it up. For example: *rgb(100,100,90)*



* **hex codes**
These are six-digit codes that represent the amount of red,green and blue in a color, preceded by a pound or hash #sign. For example: *#ee3e80*



* **color names**
There are 147 predefined color names that are recognized by browsers. For example: *DarkCyan*

## Text

### Specifying Typefaces

* The font-family property allows you to specify the typeface that should be used for any text inside the element(s) to which a CSS rule applies.

* The value of this property is the name of the typeface you want to use.

* The people who are visitingyour site need the typeface you have specified installed on their computer in order for it to be displayed.

Example:

```
<style type="text/css">
body {
font-family: Georgia, Times, serif;}
h1, h2 {
font-family: Arial, Verdana, sans-serif;}
.credits {
font-family: "Courier New", Courier,
monospace;}
</style>
```

* Bold font-weight
> .class1 { font-weight: bold;}

* Italic
> .class1 { font-style: italic;}

* Underline & Strike text-decoration
> .class1 { text-decoration: underline;}
>a { text-decoration: none;}


## TL;DR

*  JPEG : Use JPEG format for all images that contain a natural scene or photograph where variation in colour and intensity is smooth.
* PNG:  Use PNG format for any image that needs transparency or for images with text & objects with sharp contrast edges like logos. 
* GIF: Use GIF format for images that contain animations.

Example on GIF
![Gif](https://giphy.com/gifs/silicon-valley-l0K4jMNck0La1a7aU?utm_source=iframe&utm_medium=embed&utm_campaign=Embeds&utm_term=https%3A%2F%2Fcdn.embedly.com%2F)