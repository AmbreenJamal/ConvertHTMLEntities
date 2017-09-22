# ConvertHTMLEntities<br />

#copy in html file and run or downlod and run html file.<br />


Convert the characters &, <, >, " (double quote), and ' (apostrophe), in a string to their corresponding HTML entities.<br />

convertHTML("Dolce & Gabbana") should return Dolce &?amp; Gabbana.<br />
convertHTML("Hamburgers < Pizza < Tacos") should return Hamburgers &?lt; Pizza &?lt; Tacos.<br />
convertHTML("Hamburgers < Pizza < Tacos") should return Hamburgers &?lt; Pizza &?lt; Tacos.<br />
convertHTML("Sixty > twelve") should return Sixty &?gt; twelve.<br />
convertHTML('Stuff in "quotation marks"') should return Stuff in &?quot;quotation marks&?quot;.<br />
convertHTML("Shindler's List") should return Shindler&?apos;s List.<br />
convertHTML("<>") should return &?lt;&?gt;.<br />
convertHTML("abc") should return abc.<br />

================================================================================<br />
<br />
<br />
function convertHTML(string) {<br />

    for (var key in HtmlEntities) {<br />
        var entity = HtmlEntities[key];<br />
        var regex = new RegExp(key, 'g');<br />
        string = string.replace(regex, entity);<br />
    }<br />
    return string;<br />

}<br />
var HtmlEntities= {  
  "&":"&amp;",  
  "<":"&lt;",  
  ">":"&gt;",  
  '"':"&quot;",  
  "'":"&apos;"  
};    

convertHTML('Hamburgers < Pizza < Tacos');