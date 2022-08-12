<!DOCTYPE html>

<html lang = "es">
    <head>
        <meta charset = "UTF - 8">
        <meta name="viewport" content="width = device-width">
        <title>SpyLetter</title>
        <link rel="stylesheet"  href="reset.css">
        <link rel="stylesheet"  href="home-style.css">
        <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap" rel="stylesheet"> 
    </head>
    <body>
        <header>
            <div class="caja">
                <h1><img id="logo" src="imagenes/logo.png" alt="Logo de SpyLetter"></h1>
                <nav>
                    <ul>
                        <li><a href="Home.html">Home</a></li>
                        <li><a href="contacto.html">Contacto</a></li>
                    </ul>
                </nav>
                </div>
        </header>
        <main>
            <section class="fondo-principal">
                <div class="principal">
                    <h1 class="tituloprincipal">¡Encripta tu mensaje!</h1>

                    <img class="espia" src = "imagenes/espia.png" alt="Espia">
                    
                    <p>Si eres un espia super secreto o tan solo quieres mandar un mensaje secreto¡<strong>SpyLetter</strong> es para ti!.</p>
                    <br>
                    <p>Si ves algún tipo de bug o mejora que podamos aplicar a la página puedes informarlo en la página de contacto.</p>
                    <br>
                    <p>Abajo podrás ver un tutorial de como utilizar la página correctamente, aunque con lo listo que debes ser tal vez no la necesites, ¡Buena suerte!.</p>
                </div>
            </section>
            <section class="encriptador">
                <form>
                    <fieldset>
                        <label for="mensaje">Escribe tu mensaje aquí:</label>
                        <textarea cols="70" rows="10" id="mensaje" class="input-padron" required></textarea>
                    </fieldset>
                    <div>
                        <input type="button" value="Encriptar" id="codigo"class="enviar">
                        <input type="button" value="Desencriptar" id="uncodigo" class="enviar">
                    </div>
                </form>
            </section>
            <section class="resultado">
                <p>Aquí está tu mensaje, entrégalo con cautela y si lo recibiste guardalo muy bien.</p>
                <textarea cols="70" rows="10" id="final" class="resultado-contenido"></textarea>
                <input type="button" value="¡Copiar!" id="copyar" class="copiar">
                <div class="mensaje-copy">
                    <p>¡Copiado al portapapeles!</p>
                </div>
                <iframe class="video" width="100%" height="315" src="https://www.youtube.com/embed/CRvB_O3Pqpk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </section>
        </main>
        <script>

            var input = document.getElementById("mensaje");
            input.focus();

            function texto (text){
                document.getElementById ("final").value = text;
            }

            var letras = 0;
            const nuevaStr = 0

            function eliminarespeciales(Letras){
                
                var outString = Letras.replace(/[`~¡!@#$%^&*()_|+\-=?;:'",.<>\{\}\[\]\\\/]/gi, '');
                return outString;
            }
            function reemplazare(letras){
                const str = letras;
                const nuevaStr = str.replace(/e/g, "enter");
                return nuevaStr;
            }
            function reemplazari(letras){
                const str = letras;
                const nuevaStr = str.replace(/i/g, "imes");
                return nuevaStr;
            }
            function reemplazara(letras){
                
                const str = letras;
                const nuevaStr = str.replace(/a/g, "ai");
                return nuevaStr;
            }
            function reemplazaro(letras){
                const str = letras;
                const nuevaStr = str.replace(/o/g, "ober");
                return nuevaStr;
            }
            function reemplazaru(letras){
                const str = letras;
                const nuevaStr = str.replace(/u/g, "ufat");
                return nuevaStr;
            }

            function reemplazarte(){

                letras = input.value;
                letras = letras.toLowerCase();
                letras = eliminarespeciales(letras)
                letras1 = reemplazare(letras);
                letras2 = reemplazari(letras1);
                letras3 = reemplazara(letras2);
                letras4 = reemplazaro(letras3);
                letras5 = reemplazaru(letras4);
                return letras5;
            }
            function encriptar() {

                texto(reemplazarte());
            
                input.value = "";
                input.focus();
            }
            function reemplazarenter(letras){
                const str = letras;
                const nuevaStr = str.replace(/enter/g, "e");
                return nuevaStr;
            }
            function reemplazarimes(letras){
                const str = letras;
                const nuevaStr = str.replace(/imes/g, "i");
                return nuevaStr;
            }
            function reemplazarai(letras){
                
                const str = letras;
                const nuevaStr = str.replace(/ai/g, "a");
                return nuevaStr;
            }
            function reemplazarober(letras){
                const str = letras;
                const nuevaStr = str.replace(/ober/g, "o");
                return nuevaStr;
            }
            function reemplazarufat(letras){
                const str = letras;
                const nuevaStr = str.replace(/ufat/g, "u");
                return nuevaStr;
            }

            function reemplazartd(){
                
                letras = input.value;
                letras = letras.toLowerCase();
                letras1 = reemplazarenter(letras);
                letras2 = reemplazarimes(letras1);
                letras3 = reemplazarai(letras2);
                letras4 = reemplazarober(letras3);
                letras5 = reemplazarufat(letras4);
                return letras5;
            }
            function desencriptar() {

                texto(reemplazartd());
            
                input.value = "";
                input.focus();
            }

                    var button = document.getElementById("codigo");
                    button.onclick = encriptar;
                    var button = document.getElementById("uncodigo");
                    button.onclick = desencriptar;

        </script>
        <script>

            var item = document.getElementsByClassName('copiar');

            for(var i=0; i < item.length; i++){
                item[i].addEventListener('click', function(event){

                    var text = document.getElementsByClassName('resultado-contenido');
                    text[0].select();

                    try{
                        var successful = document.execCommand('copy');
                        var msg = successful ? 'successful' : 'unsuccessful';    
                        console.log('Copy was ' + msg);  
                        alert("¡Copiado!")
                    } 
                    catch(err) {  
                        console.log('Oops, no se pudo copiar');
                    }  
                    });
            }
            var button = document.getElementById("copyar");
            button.onclick = copylink("final");
        </script>
        <footer>
            <img src="imagenes/logo.png" alt="Logo de SpyLetter">
            <div class="socialmedia">
                <a href="https://www.instagram.com/susy_diaz73/" class="link">
                  <img class="fa-brands fa-instagram instagram"> <img id="insta" src="imagenes/insta.jpg"></i>
              </a>
              <a href="https://twitter.com/dbhrnf" class="link">
                  <img class="fa-brands fa-twitter twitter"> <img id="twitter" src="imagenes/twitter.png"></img>
              </a>
              <a href="https://www.youtube.com/channel/UC0TDqzbyJ_4RWAOPCg_9isw" class="link">
                  <img class="fa-brands fa-youtube youtube"> <img id="youtube" src="imagenes/youtube.png"></img>
              </a>
              <a href="https://www.linkedin.com/in/susy-diaz/" class="link">
                  <img class="fa-brands fa-linkedin linkedin"> <img id="linkedin" src="imagenes/linkedin.jpg"></img>
              </a>
                </div>
            <p class="copyright">&copy Copyright SpyLetter - 2022</p>
        </footer>

    </body>

</html>
