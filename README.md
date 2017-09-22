# ConvertHTMLEntities

#copy in html file and run or downlod and run html file.


Convert the characters &, <, >, " (double quote), and ' (apostrophe), in a string to their corresponding HTML entities.

convertHTML("Dolce & Gabbana") should return Dolce &?amp; Gabbana.
convertHTML("Hamburgers < Pizza < Tacos") should return Hamburgers &?lt; Pizza &?lt; Tacos.
convertHTML("Hamburgers < Pizza < Tacos") should return Hamburgers &?lt; Pizza &?lt; Tacos.
convertHTML("Sixty > twelve") should return Sixty &?gt; twelve.
convertHTML('Stuff in "quotation marks"') should return Stuff in &?quot;quotation marks&?quot;.
convertHTML("Shindler's List") should return Shindler&?apos;s List.
convertHTML("<>") should return &?lt;&?gt;.
convertHTML("abc") should return abc.

================================================================================


function convertHTML(string) {

    for (var key in HtmlEntities) {
        var entity = HtmlEntities[key];
        var regex = new RegExp(key, 'g');
        string = string.replace(regex, entity);
    }
    return string;

}
var HtmlEntities= {
  "&":"&amp;",
  "<":"&lt;",
  ">":"&gt;",
  '"':"&quot;",
  "'":"&apos;"
};