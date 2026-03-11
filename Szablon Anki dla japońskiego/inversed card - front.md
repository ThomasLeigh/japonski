{{#Rewers?}}
{{#Tags}}
<div class=tagi>{{Tags}}</div>
{{/Tags}}

<div id="KK">
<span class="Kana">
{{^Kanji}}{{tts ja_JP voices=Microsoft_Ayumi:Kana}}{{/Kanji}}
{{Kana}}
</span>
<span class="Kanji">
{{tts ja_JP voices=Microsoft_Ayumi:Kanji}}
{{Kanji}}
</span>
</div>

<div id=tyl>{{tyl}}</div>

<div id="DodatkoweInformacje">
{{Dodatkowe informacje}}
</div>

{{/Rewers?}}

<script type="text/javascript" src="https://code.jquery.com/jquery-1.9.1.min.js"></script>

<script type="text/javascript">

{{#Kanji}}
	$("#KK span.Kanji").wrapInner( "<ruby></ruby>" );
	$("ruby").append("<rt></rt>");
	$("rt").html($("span.Kana").html());
	$("span.Kana").remove();
{{/Kanji}}

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

$("#tyl").after("<div id='SideNotes'><ul></ul></div>")

if ($('.Kanji').text().includes('週間') || $('.Kanji').text().includes('時間')) {
  $('#SideNotes').append('<li><strong>~<ruby>間<rt>かん</rt></ruby></strong> dodajemy <strong>zawsze</strong>, podając godziny lub tygodnie.</li>');
}

if ($('.Kanji').text().includes('如何して')) {
  $('#SideNotes').append('<li><strong>~<ruby>如何して？<rt>どうして？</rt></ruby></strong> „dlaczego?” (zdziwienie, żal lub złość) - trochę bardziej formalne / uprzejme od 「nande」.<br /><br /><small><a href=https://t.me/askplexbot>źródło »</a></small></li>');
}

if ($('.Kanji').text().includes('何故')) {
  $('#SideNotes').append('<li><strong>~<ruby>何故？<rt>なぜ？</rt></ruby></strong> „dlaczego?” najbardziej formalne i racjonalne, bez emocji.<br /><br /><small><a href=https://t.me/askplexbot>źródło »</a></small></li>');
}

if ($('.Kanji').text().includes('何で') && $('#przod').text().includes('laczego')) {
  $('#SideNotes').append('<li><strong>~<ruby>何で？<rt>なんで？</rt></ruby></strong> „dlaczego?” najbardziej potocznie.<br /><br /><small><a href=https://t.me/askplexbot>źródło »</a></small></li>');
}

if ($('#przod').text().includes('młodzież')) {
} else {
if ($('#tyl').text().includes('kamo')) {
  $('#SideNotes').append('<li><strong>「kamo (shiremasen / shirenai)」</strong><br /><strong>„być może (może (tak jest), choć nie mam pewności)”</strong> - prawdopodobieństwo ok. 30%; uprzejmie. Samego 「kamo」 nie można łączyć z 「-kara」.</li>');
  }
}

if ($('#tyl').text().includes('deshou')) {
  $('#SideNotes').append('<li><strong>「deshou」</strong><br /><strong>„prawdopodobnie / prawda? / czyż nie?”</strong> - w stopniu ok. 60%; uprzejmie, np. w prognozach pogody, czy programach informacyjnych; przypuszczalna forma grzecznościowego 「desu」.</li>');
}

if ($('#tyl').text().includes('Tabun') || $('#tyl').text().includes('tabun')) {
  $('#SideNotes').append('<li><strong>「tabun」</strong><br /><strong>„zapewne”</strong> / + 「deshou」 / 「darou」 <strong>„najbardziej prawdopodobne”</strong> - Coś jest bardzo prawdopodobne, ale nadal nie całkowicie pewne; potocznie.</li>');
}

if ($('.Kanji').text().includes('会い') ||$('.Kanji').text().includes('会う') ||$('.Kanji').text().includes('会え')) {
  $('#SideNotes').append('<li><strong>Z którą partykułą 「会う」?</strong><br />に - spotkanie przypadkowe, natknięcie się na kogoś.<br />と - celowe, umówione spotkanie lub częste spotykanie się z kimś.</li>');
}

if ($('.Kanji').text().includes('呉れ') ||$('.Kanji').text().includes('呉れ')) {
  $('#SideNotes').append('<li><strong>「kureru」 / 「呉れる」</strong><br /><strong>„da(wa)ć, podarować”</strong> - mi lub komuś z mojej rodziny.</li>');
}

if ($('.Kanji').text().includes('上げ') ||$('.Kanji').text().includes('上げ')) {
  $('#SideNotes').append('<li><strong>「ageru」 / 「上げる」</strong><br /><strong>„dawać”</strong> - komuś poza mną lub moją rodziną.</li>');
}

if ($('#tyl').text().includes('tokui')) {
  $('#SideNotes').append('<li><strong>「tokui」 / 「得意」</strong><br /><strong>Czuć się</strong> w czymś dobrym, mocnym - skromniejszy sposób na ocenę własnych lub cudzych kompetencji na bazie <strong>subiektywnego</strong> odczucia pewno?ci / komfortu w ich względzie.</li>');
}

if ($('#tyl').text().includes('jouzu')) {
  $('#SideNotes').append('<li><strong>「jouzu」 / 「上手」</strong><br />Ktoś jest w czymś dobry <strong>obiektywnie</strong>.</li>');
}

if ($('#tyl').text().includes('下手')) {
  $('#SideNotes').append('<li><strong>「heta」</strong><br /><strong>Być w czymś słabym.</li>');
}

if ($('#tyl').text().includes('苦手')) {
  $('#SideNotes').append('<li><strong>「nigate」</strong><br /><strong>Być w czymś słabym <strong>i nie przepadać za tym</strong>.</li>');
}

if ($('#tyl').text().includes('ushite') || $('#tyl').text().includes('nigate')) {
} else {
if ($('#tyl').text().includes('te ')) {
  $('#SideNotes').append('<li><strong>Forma 「~te」 czasownika</strong><br /><strong>+ 「imasu」</strong> - tworzy <strong>czas teraźniejszy ciągły</strong> (czynność trwa w tej chwili) lub <strong>aspekt rezultatywny czasownika</strong> (czynność została wykonana raz, ale jej rezultat utrzymuje się do tej pory).<br /><br />Opisuje <strong>sekwencję czynności</strong> (a więc wtedy, gdy potrzebujesz użyć w jednym zdaniu więcej, niż jednego czasownika).<br /><br /><strong>+ 「kudasai」</strong> (w języku formalnym, <u>pomijane w mowie nieoficjalnej</u>) - służy <strong>do tworzenia próśb</strong>.<br /><br /><strong>+ 「-mo ii desu-ka.」</strong> - tworzy strukturę proszenia o pozwolenie.<br /><br /><strong>+ 「-wa ikemasen / ikenai」</strong> - tworzy strukturę braku możliwości czegoś, podyktowanego wolą (nie zewnętrznym czynnikiem, jak np. prawo, regulamin, itp.).</li>');
  }
}

if ($('#przod').text().includes('stycznia') || $('#przod').text().includes('lutego') || $('#przod').text().includes('marca') || $('#przod').text().includes('kwietnia') || $('#przod').text().includes('maja') || $('#przod').text().includes('czerwca') || $('#przod').text().includes('lipca') || $('#przod').text().includes('sierpnia') || $('#przod').text().includes('września') || $('#przod').text().includes('października') || $('#przod').text().includes('listopada') || $('#przod').text().includes('grudnia')) {
  $('#SideNotes').append('<li><strong>Końcówka dni miesi?ca:</strong><br /><strong>1-10, 14, 20, 24</strong> - ~か,<br /><strong>11-31 (bez 14, 20, 24)</strong> - ~にち</li>');
}

if ($('#tyl').text().includes('-de')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-de」</strong><br />Doklejana do narzędzia lub miejsca akcji.</li>');
}

if ($('#tyl').text().includes('-ka.')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ka.」</strong><br />W formalnym japońskim <strong>ekwiwalent znaku zapytania</strong> (w nieformalnym może brzmieć apodyktycznie).</li>');
}

if ($('#tyl').text().includes('-ka na.')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ka na」</strong><br />Gdy zastanawiasz się nad czymś.</li>');
}

if ($('#tyl').text().includes('-ga ')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ga」</strong><br />Oznacza temat wypowiedzi.<br /><br /><strong>W zdaniach złożonych</strong> oznacza <u>podmiot pierwszej części zdania</u>, gdy w drugiej występuje inny.</li>');
}

if ($('#tyl').text().includes('-ga.')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ga」</strong><br /><strong>Chęć zrobienia czegoś</strong> wyrażona z końcową partykułą 「-ga」 (?zmiękczającą” wypowiedź, wprowadzającą element niepewności i bezradności) jest najbardziej typową i uniwersalną metodą zwrócenia się do kogoś o pomoc.<br /><br />Np. 「Sumimasen, kono nimotsu-o okuritai desu-ga...?」 - „Przepraszam, chciałbym wysłać tą paczkę...?” » wydźwięk: „Chciałbym wysłać paczkę, ale nie wiem, jak to zrobić, co dalej robić, proszę mi pomóc...itp.”<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

if ($('#tyl').text().includes('-ga,')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ga,」</strong><br />Ekwiwalent polskiego „ale” - gdy chcesz wyrazić sprzeczność <u>w jednym zdaniu</u>.</li>');
}

if ($('#tyl').text().includes('-goro,')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-goro」</strong><br />Ekwiwalent polskich „około, mniej więcej” (partykuła przybliżonego czasu).</li>');
}

if ($('#tyl').text().includes('-nado')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-nado」</strong><br />Ekwiwalent polskich „i inne, itp.”.</li>');
}

if ($('#tyl').text().includes('-nara')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-nara」</strong><br />Ekwiwalent polskich „W przypadku...; Jeśli..., to...” (japoński tryb warunkowy).</li>');
}

if ($('#tyl').text().includes('-ne')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ne」</strong><br />Ekwiwalent polskiego „(czyż) nie? / dobrze?” - często używany w języku nieformalnym.<br /><br />Kobiety mają tendencję do dodawania jej po rzeczowniku, 「da -ne」 używa szersze grono osób.<br /><br /><small><a href="https://play.google.com/store/apps/details?id=com.busuu.android.enc">źródło »</a></small></li>');
}

if ($('#tyl').text().includes('-ni')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-ni」</strong><br />Wskazuje kierunek lub lokalizację w czasie.<br /><br />Tworzy formę celowości od czasowników (np. „aby czytać”, „aby kupić”, itp.; temat 「<u>~</u>masu」 czasownika + 「-ni」).<br /><br />Tworzy przysłówki od przymiotników 「-na」 (poprzez zamianę ich końcówki fleksyjnej 「-na」 na 「-ni」.<br /><br />Np. 「kirei-na」 » 「kirei-ni」, 「shizuka-na」 » 「shizuka-ni」).<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

if ($('#przod').text().includes('gdyż można')) {
} else {
if ($('#tyl').text().includes('-no')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-no」</strong><br />Oznacza , że <strong>coś przynależy do czegoś</strong> (do czego jest przyklejona).<br /><br /><strong>W języku nieformalnym</strong> często wieńczy pytania.<br /><br /><strong>Kończąc zdanie</strong>, wyraża emocje lub pragnienia.</li>');
  }
}

if ($('#tyl').text().includes('chikara')) {
} else {
if ($('.Kanji').text().includes('から')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-kara」</strong><br /><strong>„od” / „po” / „z”</strong> (skądś, z czegoś)<br /><br />Często poprzedzane jest formą nieoficjalną.<br /><br />To takie <strong>„bo”</strong> z emocją i bezpośredniością. Jest bardziej bezpośrednie, mocne i subiektywne, <strong>często używane w mowie potocznej</strong>. Można powiedzieć, że wyraża przyczynę z punktu widzenia mówiącego. <sup><a href="https://t.me/askplexbot">źródło »</a></sup></li>');
	}
}

if ($('.Kanji').text().includes('ので')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-node」</strong><br /><strong>„Ponieważ”</strong>, uprzejme i neutralne. Łagodniejsze, bardziej uprzejme i obiektywne, niż 「-kara」. Stosuje się je, gdy chce się wyrazić powód w bardziej neutralny lub uprzejmy sposób, np. w sytuacjach formalnych lub gdy chce się złagodzić wypowiedź. <sup><a href="https://t.me/askplexbot">źródło »</a></sup></li>');
}

if ($('#tyl').text().includes('-to ')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-to」</strong><br /><strong>„z / i”</strong> - najbliższy odpowiednik analogicznych łączników w języku polskim.<br /><br /><strong>Gdy wymieniasz</strong> <u>wszystkie</u> części danego zbioru, tzn. np. wszystkie przybory do pisania, które znajdują się w piórniku.<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small><br /><br />Doklejasz ją do słów, które <strong>przytaczasz, cytujesz</strong>.</li>');
}

if ($('#tyl').text().includes('-wa')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-wa」</strong><br />Ekwiwalent polskiego „Jeśli o [tu to, do czego jest doklejona] chodzi... / Odnośnie []...”.</li>');
}

if (
  ($('#tyl').text().includes('-wa') && $('#tyl').text().includes('nai')) ||
  ($('#tyl').text().includes('-wa') && $('#tyl').text().includes('masen'))
) {  $('#SideNotes').append('<li><strong>Partykuła 「-wa」 w negacji</strong><br />Zazwyczaj kładzie nacisk na przeczony podmiot czy dopełnienie - np.: „<u>Uczyć</u> to ja się nie lubię” (ale bawić - owszem).<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

if ($('#tyl').text().includes('-wo')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-wo」 (tzw. dopełnienie bliższe)</strong><br />Doklejana do czasowników ruchu, gdy podmiot zdania się po czymś przemieszcza (np. 「aruku」, 「wataru」, 「sanpo-suru」).</li>');
}

if ($('#tyl').text().includes('-ya')) {
  $('#SideNotes').append('<li><strong>Partyku?a 「-ya」</strong><br />Gdy wymieniasz <u>przykładowe</u> części danego zbioru (ekwiwalent „takie, jak..., itp.”)</li>');
}

if ($('#tyl').text().includes('-yo.')) {
  $('#SideNotes').append('<li><strong>Partykuła 「-yo」</strong><br />Gdy chcesz dodatkowo zaakcentować swą wypowiedź, coś podkreślić, wyrazić pewność może,<br /><br />Gdy chcesz złagodzić ton swej wypowiedzi.<br /><br />Gdy podajesz nową informację.<br /><br />Często używana w języku nieformalnym.</li>');
}

if ($('.Kanji').text().includes('だった')) {
  $('#SideNotes').append('<li><strong>datta</strong><br />Odpowiednik 「でした」 w nieoficjalnych twierdzeniach w czasie przeszłym z przymiotnikiem -na lub w zdaniach kończących się rzeczownikiem.</li>');
}

if ($('#tyl').text().includes('Sore')) {
  $('#SideNotes').append('<li><strong>「Sore」</strong><br /><strong>„To”</strong> - w pobliżu (1-2 metry od) słuchacza, rozmówcy, partnera z którym prowadzony jest dialog.<br /><br />A jeśli co najmniej dwie rozmawiające osoby znajdują się blisko siebie i trudno byłoby określić „zasięg terytorium” jednej i drugiej, wówczas dla przedmiotów leżących poza zasięgiem ich rąk.<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

if ($('#tyl').text().includes('Are')) {
  $('#SideNotes').append('<li><strong>「Are」</strong><br /><strong>„Tamto”</strong> - wzglednie daleko od obydwu osób prowadzących rozmowę - lub przy osobie trzeciej.<br /><br />A jeśli co najmniej dwie rozmawiające osoby znajdują się blisko siebie i trudno byłoby określić „zasięg terytorium” jednej i drugiej, wówczas w przypadku przedmiotów znacznie od nich oddalonych.<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

if ($('#tyl').text().includes('Kore')) {
  $('#SideNotes').append('<li><strong>「Kore」</strong><br /><strong>„To”</strong> - względnie blisko osoby mówiącej lub - jeśli co najmniej dwie rozmawiające osoby znajdują się blisko siebie i trudno byłoby określić „zasięg terytorium” jednej i drugiej - obu rozmówców.<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

if ($('#tyl').text().includes('っ')) {
  $('#SideNotes').append('<li><strong>「っ」</strong><br /><strong>„Małe 「tsu」”</strong> - pamiętaj, by nie używać go przed Hiraganą z rzędu 「n」 i 「m」 (do których podwajania używamy 「ん」).</li>');
}

if ($('.Kanji').text().includes('られま')) {
  $('#SideNotes').append('<li><strong>Forma potencjalna czasowników</strong> (np. ～られます).<br />Partykuły が i を są wymienne.<br /><br /><small><a href=https://play.google.com/store/apps/details?id=com.busuu.android.enc>źródło »</a></small></li>');
}

if ($('.Kanji').text().includes('何か')) {
  $('#SideNotes').append('<li><strong>Zaimki nieokreślone</strong> (np. „coś”, „ktoś”).<br />Zdarza się, że partykuła 「-ka」 występuje po pytajnikach, nadając im charakter zaimków nieokreślonych.<br /><br /><small>Źródło: <em>Język japoński dla początkujących</em> (Ewa Krassowska-Mackiewicz)</small></li>');
}

$('.Kanji').html($('.Kanji').html().replace(/か？/g, 'か。'));

</script>