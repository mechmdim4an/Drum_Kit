The Detailed JavaScript without minify by Mentor


// Detecting button press


var numberOfdrumButtons = document.querySelectorAll(".drum").length;
for (var i = 0; i < numberOfdrumButtons; i++){
    document.querySelectorAll(".drum")[i].addEventListener("click", function () {
        var buttonInnerHtmal = this.innerHTML;
        makeTheSound(buttonInnerHtmal);
        buttonAnimation(buttonInnerHtmal);
    });
}


// Detecting keyboard press


document.addEventListener("keypress", function (event) {
    makeTheSound(event.key);
    buttonAnimation(event.key);
    
})


// Constructor Objects linked sound 


function makeTheSound(key) {
    switch (key){
        case "e":
            var tom1 = new Audio("sounds/tom-1.mp3");
            tom1.play();
        break;

        case "s":
            var tom2 = new Audio("sounds/tom-2.mp3");
            tom2.play();
        break;

        case "d":
            var tom3 = new Audio("sounds/tom-3.mp3");
            tom3.play();
        break;

        case "f":
            var tom4 = new Audio("sounds/tom-4.mp3");
            tom4.play();
        break;

        case "j":
            var snare = new Audio("sounds/snare.mp3");
            snare.play();
        break;

        case "k":
            var crash = new Audio("sounds/crash.mp3");
            crash.play();
        break;

        case "l":
            var kick = new Audio("sounds/kick-bass.mp3");
            kick.play();
        break;

        default: console.log(buttonInnerHtmal);
    }
    
}

<!-- Animation -->

function buttonAnimation (currentKey){
    var activeButton = document.querySelector("."+currentKey); // button created
    activeButton.classList.add('pressed'); //class added
    
    <!-- // removing class after 100ms setTime(function, 100); -->
    setTimeout(function () {
        activeButton.classList.remove("pressed");    
    },100);

}

