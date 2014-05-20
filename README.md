velocity-truncate-html
======================

Velocity Macro for dotCMS to "smart" truncate a string of HTML at a given number of words across tags without needing to worry about unclosed tags or invalid HTML. Please keep in mind that this macro assumes that you are passing it valid HTML to begin with... Here is how you use it:
    
    #dotParse('/[PATH TO MACRO]/truncate-html.vtl]')##
    #set( $myHTML = '
    	<h1>HTML Ipsum Presents</h1>
	     
      <p><strong>Pellentesque habitant morbi tristique</strong> senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. <em>Aenean ultricies mi vitae est.</em> Mauris placerat eleifend leo. Quisque sit amet est et sapien ullamcorper pharetra. Vestibulum erat wisi, condimentum sed, <code>commodo vitae</code>, ornare sit amet, wisi. Aenean fermentum, elit eget tincidunt condimentum, eros ipsum rutrum orci, sagittis tempus lacus enim ac dui. <a href="#">Donec non enim</a> in turpis pulvinar facilisis. Ut felis.</p>
      
      <h2>Header Level 2</h2>
      	       
      <ol>
         <li>Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</li>
         <li>Aliquam tincidunt mauris eu risus.</li>
      </ol>
      
      <blockquote><p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus magna. Cras in mi at felis aliquet congue. Ut a est eget ligula molestie gravida. Curabitur massa. Donec eleifend, libero at sagittis mollis, tellus est malesuada tellus, at luctus turpis elit sit amet quam. Vivamus pretium ornare est.</p></blockquote>
      
      <h3>Header Level 3</h3>
      
      <ul>
         <li>Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</li>
         <li>Aliquam tincidunt mauris eu risus.</li>
      </ul>
      
      <pre><code>
      #header h1 a { 
      	display: block; 
      	width: 300px; 
      	height: 80px; 
      }
      </code></pre>
    ' )##

I have included the macro code and set up a variable that contains a string of HTML. Now I call the truncate HTML macro:

    #trucateHTML( $myHTML )##
    
This simple decleration is all you need to do in order to pull in the first 20 words of the HTML. The macro will do the work closing any clipped tags, so no need to worry. If you want more/fewer words, you can pass a second argument to the macro like so:

    #trucateHTML( $myHTML 50 )##
    
Now the first 50 words will be pulled in! If you want to add an elipsis or some other text to the end of your text where it was truncated you can pass the macro a third parameter:

    #trucateHTML( $myHTML 50 '...' )##
    
And there you have it. Happy coding!




