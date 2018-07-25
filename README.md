Start of transcript. Skip to the end.
D3 is a set of objects functions and other good stuff that comes in the form
of a third-party JavaScript file written by Mike Bostock which you can use just
like any external javascript file in the script tag and we've included here so
what D3 does is it creates SVG's similar to what we created in earlier
units plus a lot more but it does it programmatically rather than in the form
of markup one of the things d3 relies on is attaching itself to some HTML iment
such as a div for example
you
we're going to create an SVG inside that div with the ID draw here unless we're
doing now also notice on line 20 we have a JavaScript array with five items so
we're going to use those as the data to be provided to our SVG's notice they're
on line 22 we're using the d3 object and a function on that object called select
so that attaches that the Select inside the Select we attach ourselves to they
to the draw here ID also notice that d3 allows you to chain functions together
you'll see that they're separated by a dot that's it conveniently allows you to
chain related functions together so you can see on line 23 we are
programmatically creating an SVG element then were creating an assigning a width
attribute and a height attribute to that SVG and the width and the height values
are declared on lines 18 and 19 line 22 results in the creation of a variable or
an object called SVG we could name or whatever we chose to name it would we're
going to call SVG we then use that object then to call a particular
function called select all and that select all will select all the circles
we'll let's select as many circles as that are generated as a result of
binding to the data on line 20 we then use the array defined on line 20 and
pass it as a variable into our data function we then use the enter function
they d3 enter function to bind the data to the circles that we are about to
create so then we create a circle we're going to create a circle for each datum
which is d each entry in the array the x value for each one will be set
programmatically and we use an anonymous function here and the anonymous function
can take one or two variables our parameters in our case we're using
two at the moment d and i represents the individual data such as 40 50 10 and
so on and I is the index of that data in the array by the way the naming D and I
is just a convention you could call them anything you want to but but Convention
and dictates that we call them d and i so that will give us our our
x-coordinate for each for each datum for each circle now we want to do is they on
line 32 we constructed so that each entry the x-value of each entry is a
hundred and fifty units to the right of its predecessor the y-coordinate splits
the height of the viewport and into
and you can see that here so these elements combine to be 500 pixels apart
and the radius then for each one of these has been defined in the array so
let's try a little experiment let's add an extra element to our to our data we
do refresh we can't see it why not it's because that last element is
displayed but it's outside the maximum width of our viewport so keep an eye on
that it catches people out in the beginning when they're learning d3
initially so we increase
the width and there we can see it so that's a nice introduction to d3
End of transcript. Skip to the start.
  Links To External Resources