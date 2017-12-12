# "Modal (Pop-up Window)": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary
This example creates a re-usable modal window. It can be opened using the combination of *(link-repeat:)* and *(show:)* to 'show' the window and be 'closed' using *(link-repeat:)* with the *(replace:)* macro to change the content. CSS rules are used to style the window and create the effect of having content be darkeneded behind the 'shown' content.

## Live Example

<section>
<iframe src="harlowe_modal_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_modal_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Modal

:: UserStylesheet[stylesheet]
/* The Modal (background) */
.modal {
    display: block;
    position: fixed; /* Stay in place */
    z-index: 1; /* Sit on top */
    left: 0;
    top: 0;
    width: 100%; /* Full width */
    height: 100%; /* Full height */
    overflow: auto; /* Enable scroll if needed */
    background-color: rgb(0,0,0); /* Fallback color */
    background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
    background-color: #fefefe;
    margin: 15% auto; /* 15% from the top and centered */
    padding: 20px;
    border: 1px solid #888;
    width: 80%; /* Could be more or less, depending on screen size */
  	color: black; /* Make the text black */
}

/* The Close Button */
.close {
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}


:: Start
{[
	<div class="modal">
  		<div class="modal-content">
    		<span class="close">
			{(link-repeat: "×")[(replace: ?modal)[] ]}
			</span>
    	Some text in the Modal..
  		</div>
	</div>
](modal|}
(link-repeat:"Open Modal!")[(show:?modal)]


```

Download: <a href="harlowe_modal_twee.txt" target="_blank">Twee Code</a>
