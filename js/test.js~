

$(document).ready(function(){

//var myData = JSON.stringify(TextData);
var TextData =["#Trump Where was Trump when Cruz was fighting Rubio and Schumer on amnesty for illegals? Cruz is the true conservative.","#RealDonaldTrump is the greatest business mind: https://t.co/nJZdbmkpJG https://t.co/pivvj0nvje","Trending Now: #Trump | #Oregon | #Debate | #Up | #China | #Sanders | #After | #Bundy | #Leader | #Obama via https://t.co/942kPJKfeu#RealDonaldTrump will save us: https://t.co/cSpSIMH5W9 https://t.co/AYUHae69bb","#RealDonaldTrump is the greatest business mind: https://t.co/nJZdbmkpJG https://t.co/W8LvHyQl9l"];
var textData="";
    for(var i=0;i<TextData.length;i++){
        var shortText= TextData[i];


       var urlRegex = /(https?:\/\/[^\s]+)/g;
     var characterRegex=/[^a-z0-9]+|\s+/gmi;
       shortText =shortText.replace(urlRegex," ").replace(characterRegex," ");

      //shortText=shortText.replace

       textData=textData+" "+shortText;
    }

    var stopWords ="(i|me|my|myself|we|us|our|just|ours|JUST|TRUMP2016|REALDONALDTRUMP|TRUMP|ourselves|you|your|yours|yourself|yourselves|he|him|his|himself|she|her|hers|herself|it|its|itself|they|them|their|theirs|themselves|what|which|who|whom|whose|this|that|these|those|am|is|are|was|were|be|been|being|have|has|had|having|do|does|did|doing|will|would|should|can|could|ought|i'm|you're|he's|she's|it's|we're|they're|i've|you've|we've|they've|i'd|you'd|he'd|she'd|we'd|they'd|i'll|you'll|he'll|she'll|we'll|they'll|isn't|aren't|wasn't|weren't|hasn't|haven't|hadn't|doesn't|don't|didn't|won't|wouldn't|shan't|shouldn't|can't|cannot|couldn't|mustn't|let's|that's|who's|what's|here's|there's|when's|where's|why's|how's|a|an|the|and|but|if|or|because|as|until|while|of|at|by|for|with|about|against|between|into|through|during|before|after|above|below|to|from|up|upon|down|in|out|on|off|over|under|again|further|then|once|here|there|when|where|why|how|all|any|both|each|few|more|most|other|some|such|no|nor|not|only|own|same|so|than|too|very|say|says|said|shall|@Trump|@|#Trump2016|#Trump|#DonaldTrump)";
    var colorRange=["#fc61e2","#7d3070","#511f49"];
     wordCloud(textData, stopWords);

	
});







 function  wordCloud(textData, stopWords,colorRange){
    
    var width = $("#wordCloud").width();
   // var widthDid = $("news").width();
    var height = $("#wordCloud").height();
    /*$.ajax({
            url: ur,
            dataType: "json",
	    contentType:'application/json',
    	    data: JSON.stringify(Candidates),
            type: "POST",
            success: function(e){ */
                if(textData){
		                                                
                  var text={
                                  "width":width,
                                  "height": height,
                                  "padding": {"top":0, "bottom":0, "left":0, "right":0},

                                  "data": [
                                    {
                                      "name": "table",
                                      "values": [ textData
                                          ],

                                      "transform": [
                                        {
                                          "type": "countpattern",
                                          "field": "data",
                                          "case": "upper",
                                          "pattern": "[\\w']{3,}",
                                          "stopwords": stopWords
                                        },
                                        {
                                          "type": "formula", "field": "angle",
                                          "expr": "[-45, 0, 45][~~(random() * 3)]"
                                        },
                                        {
                                          "type": "formula", "field": "weight",
                                          "expr": "if(datum.text=='VEGA', 600, 300)"
                                        },
                                        {
                                          "type": "wordcloud",
                                          "size": [800, 400],
                                          "text": {"field": "text"},
                                          "rotate": {"field": "angle"},
                                          "font": {"value": "Arial"},
                                          "fontSize": {"field": "count"},
                                          "fontWeight": {"field": "weight"},
                                          "fontScale": [10, 40]
                                        }
                                      ]
                                    }
                                  ],

                                  "scales": [
                                    {
                                      "name": "color",
                                      "type": "ordinal",
                                      "range":["#fc61e2","#7d3070","#511f49"]
                                    }
                                  ],

                                  "marks": [
                                    {
                                      "type": "text",
                                      "from": {"data": "table"},
                                      "properties": {
                                        "enter": {
                                          "x": {"field": "layout_x"},
                                          "y": {"field": "layout_y"},
                                          "angle": {"field": "layout_rotate"},
                                          "font": {"field": "layout_font"},
                                          "fontSize": {"field": "layout_fontSize"},
                                          "fontStyle": {"field": "layout_fontStyle"},
                                          "fontWeight": {"field": "layout_fontWeight"},
                                          "text": {"field": "text"},
                                          "align": {"value": "center"},
                                          "baseline": {"value": "alphabetic"},
                                          "fill": {"scale": "color", "field": "text"}
                                        },
                                        "update": {
                                          "fillOpacity": {"value": 1}
                                        },
                                        "hover": {
                                          "fillOpacity": {"value": 0.5}
                                        }
                                      }
                                    }
                                  ]
                               
                     };

                     };
		var viewUpdateFunction = (function(chart) {
		this.view = chart({el:"#wordCloud"}).update();
		}).bind(this);
		vg.parse.spec(text, viewUpdateFunction);
          /*  },
	    error: function(er){
		alert("Error Graph Sentiment" + er);
	   }
     }); */
}
