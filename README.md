# Code-Refactoring-Assignment
The provided HTML code and assets (including CSS file and images) by a marketing agency were taken and refactored. 
This was done to meet the marketing agency's acceptance criteria and to improve accessibility, readability, search engine optimization and efficiency of the code and website. 
 
## HTML code refactoring
### Semantic Elements
Initially the provided HTML code included non-semantic elements ( < div> ) with class attributes to differentiate them. 
In this project, to improve the quality of the HTML code, non-semantic elements were replaced with semantic elements. 
 
Semantic elements outline page structure and provide meaning to the content within each element, therefore by replacing existing non-semantic elements the site accessibility, search engine optimization and readability are improved.
 
The following < div> tags were replaced with semantic elements: 
Original non-semantic elements | Semantic elements
------------------|------------------
< div class="header"> | < header>
< div> *navigation bar content* </ div>|< nav> 
< div class= "content"> |< article> 
< div class="benefits">|< aside> 
< div> elements within < main> and < aside>|< section> (class attributes remain the same however)
< div class="footer">  |  < footer> 
 
In the style.css file, the corresponding selectors were changed to reflect change in HTML tag name.
 
 
### Image elements
All image elements were provided with alt attributes during the project. Alt attributes which describe the image are provided to improve accessibility and search engine optimization.

### Title element
The title was changed from 'website' to 'Horiseon: Online Business Marketing'. This was done to reflect the content of the website and to improve search engine optimisation. 
 
 
### Working links
Initially, the link for 'Search Engine Optimization' in the navigation bar wasn't working. Inspection of the HTML code revealed 'id = "search-engine-optimization" attribute was missing from its < section > tag. This was corrected to ensure the website functions correctly. 
 
### Simplify 
To simplify elements within < nav >, untitled list and list tags were removed as they were not required for functioning of the navigation bar. By doing this, readability of the code was improved as well as the size of HTML file and efficiency. 
 * Original HTML code for navigation bar: 
 ```
         <div>
            <ul>
                <li>
                    <a href="#search-engine-optimization">Search Engine Optimization</a>
                </li>
                <li>
                    <a href="#online-reputation-management">Online Reputation Management</a>
                </li>
                <li>
                    <a href="#social-media-marketing">Social Media Marketing</a>
                </li>
            </ul>
        </div>
```
* Modified HTML code for navigation bar: 
```
        <nav> 
            <a href="#search-engine-optimization">Search Engine Optimization</a>
            <a href="#online-reputation-management">Online Reputation Management</a>
            <a href="#social-media-marketing">Social Media Marketing</a>
        </nav>
```
<br>This change also allowed to reduce the size of CSS file by removing selectors and combining relevant properties under the new 'nav' selector.
* Original CSS code: 
```
.header div {
    padding-top: 15px;
    margin-right: 20px;
    float: right;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    font-size: 20px;
}

.header div ul {
    list-style-type: none;
}

.header div ul li {
    display: inline-block;
    margin-left: 25px;
}

a {
    color: #ffffff;
    text-decoration: none;
}

```
* Modified CSS code: 
```
nav {
    padding-top: 15px;
    margin-right: 20px;
    float: right;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    font-size: 20px;
    margin-left: 25px;
}

a {
    color: #ffffff;
    text-decoration: none;
    margin-left: 25px;
}
```
 
 
 
### Additional changes to HTML:
* During the initial read of the HTML code, an </ img > closing tag was found after the 'cost-management' image tag. This was corrected to improve formatting. 
* To improve readability of the code, comments were added.
 
## CSS clean-up
### Re-organising structure:
The selectors in the original CSS code did not follow a logical order. The order of selectors was rearranged to reflect the order of HTML elements to improve organization and readability.
 
 
### Grouping selectors: 
To clean up the provided CSS code, selectors with identical properties were grouped. This was done to reduce the size of the CSS file and allow it to become more efficient. 
<br>For example, the following selectors have similar properties: 
```
.benefit-lead { 
    margin-bottom: 32px; 
    color: #ffffff;
    }
.benefit-brand { 
    margin-bottom: 32px; 
    color: #ffffff;
    } 
.benefit-cost { 
    margin-bottom: 32px; 
    color: #ffffff; } 
```
 
These were combined as follows:
 
```
.benefit-lead, .benefit-brand, benefit-cost { 
    margin-bottom: 32px; 
    color: #ffffff;  
    }
```
 
### Remove repeated elements:  
In the original stylesheet, the three images within < article >  were identified twice under different selectors: 
```
.search-engine-optimization img { 
    max-height: 200px; 
} 
 
.online-reputation-management img { 
    max-height: 200px; 
} 
 
.social-media-marketing img { 
    max-height: 200px; 
} 
 
.float-left { 
    float: left; 
    margin-right: 25px; 
} 
 
.float-right { 
    float: right; 
    margin-left: 25px; 
} 
```
 
In the above, '.float-left' also applies to '.search-engine-optimization img' and '.social-media-marketing img'. Similarly 'float-right' also applies to '.online-reputation-management img'. 
To simplify and improve readability of the CSS file, properties from the first 3 selectors were incorporated into their respective bottom 2 selectors. 
 
