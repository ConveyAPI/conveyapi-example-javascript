# ConveyAPI Javascript Examples

Contained are two ConveyAPI JavaScript examples. The examples are self contained and will 
run on a desktop in any browser that supports JavaScript. To run the examples, open index.html in 
a browser and follow the instructions. 

## ConveyAPI 

ConveyAPI is a REST based text-analytics service. The current release supports annotations for 
sentiment (polarity), emotion (the 8 basic emotions from Plutchik's Wheel of Emotion), intensity and spam. 
Annotations are supported at both the document and sentence level. For more information about ConveyAPI or 
to obtain an API key, visit: [http://conveyapi.com](http://conveyapi.com/)

## Examples

The examples are designed to showcase the ease of use of ConveyAPI. Using Bootstrap, jQuery and ConveyAPI, 
the code highlights how quickly and easily data can be annotated and put into a UI for analysis and reporting.

* index.html
    * A landing page with a code example and links to the two other pages.
* document.html
    * Analyze a single block of text and view the annotated results.
* twitter.html
    * Enter a search term for Twitter and pull back 100 results. Take the 100 resuls and pass each one through ConveyAPI to annotate the tweets.

The only caveat is the JSONP 'callback' parameter. Make sure to use the 'callback' parameter in order to have your response returned as JSONP (JSON with Padding).

    $.getJSON("http://beta.conveyapi.com/analysis-engine/process?callback=?",
      { api_key: apiKey, text: textToAnalyze},
      function(jsonData) {
        var document = jsonData.documents[0]; //Get the first document (only one will be returned in this example)
        var polarity = document.annotations.polarity; //Get the polarity annotation
        alert("Document was: " + polarity.value + "(confidence: " + polarity.confidence + ")");
      });

### Useful Links
* [ConveyAPI](http://conveyapi.com/)
* [jQuery](http://jquery.com/)
* [Bootstrap](http://twitter.github.com/bootstrap/)
* [JSONP Information](http://api.jquery.com/jQuery.getJSON/)


