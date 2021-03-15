# "Modal (Pop-up Window)": Snowman (1.3.0)

## Summary

This example uses the jQuery **[click()](https://api.jquery.com/click/)** and **[show()/hide()](http://api.jquery.com/show/)** functions to watch for the user clicking on a button (to open) or "X" (to close). Additional CSS rules are used to create the effect of having the content 'behind' the [modal window](https://en.wikipedia.org/wiki/Modal_window) be darkened and unusable until the modal itself is closed.

## Example

[Download](snowman_modal_example.html){: target="_top" download="snowman_modal_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Modal

:: UserScript[script]
$(function(){

        // When the user clicks the button, open the modal
        $("#myBtn").click(function() {
              $("#myModal").show();
        });

        // When the user clicks on <span> (x), close the modal
        $(".close").click(function() {
              $("#myModal").hide();
        });

});


:: UserStylesheet[stylesheet]
/* The Modal (background) */
.modal {
    display: none; /* Hidden by default */
    position: fixed; /* Stay in place */
    z-index: 1; /* Sit on top */
    padding-top: 100px; /* Location of the box */
    left: 0;
    top: 0;
    width: 100%; /* Full width */
    height: 100%; /* Full height */
    overflow: auto; /* Enable scroll if needed */
    background-color: rgb(0,0,0); /* Fallback color */
    background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content */
.modal-content {
    background-color: #fefefe;
    margin: auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
}

/* The Close Button */
.close {
    color: #aaaaaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: #000;
    text-decoration: none;
    cursor: pointer;
}


:: Start
<button id="myBtn">Open Modal</button>

<div id="myModal" class="modal">
  <div class="modal-content">
    <span class="close">×</span>
    <p>Example text in the modal</p>
  </div>
</div>

```

[Twee Download](snowman_modal_twee.txt){ target="_top" download="snowman_modal_twee.txt"}
