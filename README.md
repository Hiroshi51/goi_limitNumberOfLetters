# limitNumberOfLetters
This is a Jquery Script to forcibly limit the number of letters in elements like, p, span, div...

(function($) {
    //to restrict the number of letters in a element
    $.fn.limitNumberOfLetters = function(NumberOfLetters){
    var cutFigure = NumberOfLetters; // How many Letters?
    var afterTxt = '...'; // text after the cut string
 　　$(this).css({visibility:'hidden'});　// To hide the elment before the Length is decided
    this.each(function(){
        var textLength = $(this).text().length;
        var textTrim = $(this).text().substr(0,(cutFigure))
 
        if(cutFigure < textLength) {
            $(this).html(textTrim + afterTxt).css({visibility:'visible'});
        } else if(cutFigure >= textLength) {
            $(this).css({visibility:'visible'});
        }
    });
	return(this);
    };
})(jQuery);
