{{FrontSide}}

<p id=answer>😺</p>

<div id=przod>{{przod}}</div>

<div id="DodatkoweInformacjePL">
{{Dodatkowe informacje PL}}
</div>

<script type="text/javascript">

$("#tyl i, #przod i").contents().unwrap();

$('body').addClass('example');

$( "#przod, #tyl, #KK, .tagi, #answer, #DodatkoweInformacjePL, #DodatkoweInformacje, #example" ).animate({
		opacity: "1",
		duration: "1000"
}, 1000 );

$('.tagi:contains("leech")').each(function(){
  $(this).html(
    $(this).html().replace(/leech/g,'')
  );
});

$('.tagi:contains("Tango")').each(function(){
  $(this).html(
    $(this).html().replace(/Tango/g,'🇯🇵')
  );
});

$('.tagi:contains("zapożyczenia")').each(function(){
  $(this).html(
    $(this).html().replace(/zapożyczenia/g,'🇺🇸')
  );
});



</script>