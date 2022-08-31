# testpage
Test de pagina con tag manager


<html lang="ES" class="js no-touchevents"> 
  <header>
    <script>
      (function () {
        function getDom(selector) {
          return document.querySelector(selector);
        }

        var div = document.createElement("div");
        document.getElementsByTagName("body")[0].appendChild(div);
        div.outerHTML =
          "<div id='bindbot-container'> <a class='cerrar-movil' href='#'>X</a> <div class='bindbot-button'>   <div id='botDiv' class='bottombutton'>     <span class='botSymbol bounce'>»</span>     <div class='botIcon rubberBand'><span></span></div>     <span class='botDivText'></span>   </div>   <div id='animate' class='icon-pulse'></div> </div> <div id='botDivFrame' class='bottombutton'>   <div style='display: flex; position: relative;'>     <p style='color: white;font-family:boldcitroen !important;font-size:18px;margin:0;padding-top:15px;padding-bottom:15px'>EN QUE TE PUEDO AYUDAR?</p>     <a class='ayuda' href='#'>?</a> <a class='cerrar' href='#'>X</a>     <div id='bloque_ayuda'>       <div class='texto'>         <div class='titulo'>           Comandos disponibles en Cotización y Test Drive         </div>         <div class='indicaciones'>           Usando estos comandos podrás realizar las acciones que se indican,           por ejemplo salir de cotización actual, o volver a la pregunta           anterior y seguir conversando con nosotros.         </div>         <ul class='comandos'>           <li><strong>Regresar</strong>: Regresar a la pregunta anterior.</li>           <li>             <strong>Ayuda</strong>: Muestra el tipo de respuestas que puedes             dar.           </li>           <li>             <strong>Salir</strong>: Salir del formulario sin terminarlo.           </li>           <li>             <strong>Reiniciar</strong>: Empezar de nuevo a llenar el             formulario. (Con los valores predeterminados con anterioridad).           </li>           <li>             <strong>Estado</strong>: Muestra el progreso en el llenado de la             forma hasta ahora.           </li>         </ul>       </div>     </div>     <span class='btn-close'> <span></span> </span>   </div>      <iframe     id='frmWebChat'     class='botFrame'     frameborder='0'     src='https://citroenchatbot.azurewebsites.net'   ></iframe> </div></div>"

        var optionbutton = "bottom";

        // para no usar animacion ingresar 'none'
        var animationPulse = "icon";

        getDom("#botDiv").classList.add(optionbutton + "button");
        getDom("#botDivFrame").classList.add(optionbutton + "button");
        getDom("#animate").classList.add(animationPulse + "-pulse");

        if (botDivFrame.classList.value == "iconbutton") {
          getDom("#botDiv").classList.add("pulse");
        } else if (botDivFrame.classList.value == "bottombutton") {
          getDom(".botIcon").classList.add("rubberBand");
        }

        document.querySelector("body ").addEventListener("click", function (e) {
          e.target.matches = e.target.matches || e.target.msMatchesSelector;
          if (
            e.target.matches("#bindbot-container #botDiv") ||
            e.target.matches("#bindbot-container .botDivText") ||
            e.target.matches(".botSymbol") ||
            e.target.matches("#bindbot-container .btn-close") ||
            e.target.matches(".btn-close span") ||
            e.target.matches("#bindbot-container .botIcon span")
          ) {
            var botDiv = document.querySelector("#botDiv");
            var botDivFrame = document.querySelector("#botDivFrame");

            //Tamaño normal
            if (window.screen.width > 100) {
              // ======================  PANEL SLIDE CONTROL  =====================
              if (botDivFrame.style.height == "560px") {
                // ==========================  SLIDE DOWN  =========================
                getDom("#botDivFrame").classList.remove("slideUp");
                getDom("#botDivFrame").classList.add("slideDown");

                setTimeout(function () {
                  getDom("#botDivFrame").style.height = "0px";
                }, 0);

                setTimeout(function () {
                  getDom(".bindbot-button").style.display = "block";
                  getDom(".bindbot-button").classList.add("fadeIn");
                }, 0);
              } else {
                // ===========================  SLIDE UP  ==========================
                getDom(".bindbot-button").style.display = "none";

                getDom("#botDivFrame").classList.remove("slideDown");
                getDom("#botDivFrame").classList.add("slideUp");

                setTimeout(function () {
                  getDom("#botDivFrame").style.height = "560px";
                }, 0);
              }
            }
            //Mobile
            // =============  A PARTIR DE AQUI NO SE HA MODIFICADO  =============
            else {
              if (botDivFrame.classList.contains(optionbutton + "button")) {
                if (botDivFrame.style.height == "100%") {
                  // ==========================  SLIDE DOWN  =========================
                  getDom("#botDivFrame").classList.remove("slideUp");
                  getDom("#botDivFrame").classList.add("slideDown");

                  setTimeout(function () {
                    getDom("#botDivFrame").style.height = "0px";
                  }, 0);

                  setTimeout(function () {
                    getDom(".bindbot-button").style.display = "block";
                    getDom(".bindbot-button").classList.add("fadeIn");
                  }, 0);
                } else {
                  // ===========================  SLIDE UP  ==========================
                  getDom(".bindbot-button").style.display = "none";
                  getDom("#botDivFrame").classList.remove("slideDown");
                  getDom("#botDivFrame").classList.add("slideUp");

                  setTimeout(function () {
                    getDom("#botDivFrame").style.height = "560px";
                  }, 0);
                }
              }
            }
          }
        });
        /*AYUDA*/
        document
          .querySelector(".ayuda")
          .addEventListener("click", function (e) {
            //fadeIn(getDom('#bloque_ayuda'));
            //fadeIn(getDom('.cerrar'));
            //fadeOut(getDom('.ayuda'));

            var cerrar = getDom(".cerrar");
            if (window.getComputedStyle(cerrar).display === "none") {
              cerrar.style.display = "block";
            }
            var bloque_ayuda = getDom("#bloque_ayuda");
            if (window.getComputedStyle(bloque_ayuda).display === "none") {
              bloque_ayuda.style.display = "block";
            }
            var ayuda = getDom(".ayuda");
            if (window.getComputedStyle(ayuda).display === "block") {
              ayuda.style.display = "none";
            }

            //FIN PROBAR.
          });
        document
          .querySelector(".cerrar")
          .addEventListener("click", function (e) {
            //fadeOut(getDom('#bloque_ayuda'));
            //fadeOut(getDom('.cerrar'));
            //fadeIn(getDom('.ayuda'));

            //TODO: PROBAR SI FUNCIONA
            var cerrar = getDom(".cerrar");
            if (window.getComputedStyle(cerrar).display === "block") {
              cerrar.style.display = "none";
            }
            var bloque_ayuda = getDom("#bloque_ayuda");
            if (window.getComputedStyle(bloque_ayuda).display === "block") {
              bloque_ayuda.style.display = "none";
            }

            var ayuda = getDom(".ayuda");
            if (window.getComputedStyle(ayuda).display === "none") {
              ayuda.style.display = "block";
            }
            //FIN PROBAR.
          });

        function fadeOut(element) {
          var op = 1; // initial opacity

          var timer = setInterval(function () {
            if (op <= 0.1) {
              clearInterval(timer);
              element.style.display = "none";
            }
            element.style.opacity = op;
            element.style.filter = "alpha(opacity=" + op * 100 + ")";
            op -= op * 0.1;
          }, 50);
        }

        function fadeIn(element) {
          var op = 0.1; // initial opacity
          element.style.display = "block";
          var timer = setInterval(function () {
            if (op >= 1) {
              clearInterval(timer);
            }
            element.style.opacity = op;
            element.style.filter = "alpha(opacity=" + op * 100 + ")";
            op += op * 0.1;
          }, 10);
        }
        /*FIN AYUDA*/
      })();
    </script>
  </header>
</html>

<style>

@font-face {
  font-family: boldcitroen;
  src: url(https://media.citroen.cl/design/rel_6.28/frontend/assets_part/fonts/citroen_bold.ttf);
}

  a.cerrar-movil {
    display: none;
  }

  #botDiv.bottombutton .botSymbol {
    display: none;
  }

  #animate.icon-pulse {
    display: none;
    width: 80px;
    height: 80px;
    background: #ffffff;
    position: fixed;
    bottom: 48px;
    right: 42px;
    border-radius: 52px;
    border: solid 3px #455d9a;
    animation: pulse-opacity 0.7s ease infinite;
    z-index: 1004;
  }

  #botDiv.bottombutton .botIcon {
    height: 80px;
    width: 240px;
    background-color: none;
    border-radius: 0;
    padding: 0px;
    z-index: 1;
  }

  #botDiv.bottombutton .botIcon span {
    background: url(./logochatbotactua.gif);
    display: block;
    height: 100%;
    width: 100%;
    background-size: cover;
    background-repeat: no-repeat;
    margin: auto;
    margin-top: 0;
    margin-right: 8px;
    border-radius: 0;
  }

  #botDivFrame.iconbutton,
  #botDivFrame.bottombutton {
    height: 0;
    position: fixed;
    bottom: 15px;
    right: 42px;
    z-index: 1000;
    overflow: hidden;
    min-width: 340px;
    z-index: 999999;
  }

  #botDivFrame.slideUp {
    background-color: black;
    padding-right: 10px;
    padding-left: 10px;
    padding-bottom: 0px;
  }

  #bloque_ayuda {
    position: absolute;
    width: 100%;
    height: 450px;
    margin: 42px 0 0 0;
    background: #ffffff;
    -webkit-border-radius: 6px;
    -moz-border-radius: 6px;
    border-radius: 0px;
    padding: 20px;
    box-sizing: border-box;
    display: none;
    overflow-y: scroll;
  }

  #bloque_ayuda .texto {
    width: 100%;
  }

  #bloque_ayuda .texto .titulo {
    color: #6c7a8a;
    font-family: "Open Sans", sans-serif;
    font-size: 14px;
  }

  #bloque_ayuda .texto .indicaciones {
    color: #ffffff;
    font-family: "Open Sans", sans-serif;
    font-size: 13px;
    padding: 10px;
    background: #eb6428;
    margin: 10px 0 0 0;
  }

  #bloque_ayuda .texto ul.comandos {
    color: #6c7a8a;
    font-family: "Open Sans", sans-serif;
    font-size: 13px;
    margin: 10px 0 0 15px;
    float: left;
    clear: both;
    padding: 0;
  }

  #bloque_ayuda .texto ul.comandos li {
    margin: 0 0 10px 0;
  }

  #bloque_ayuda strong {
    font-weight: 700;
  }

  a.ayuda,
  a.cerrar {
    position: absolute;
    top: 9px;
    right: 53px;
    display: block;
    cursor: pointer;
    z-index: 17;
    font-family: "HyundaiSansHead-Regular", sans-serif;
    font-size: 12px;
    color: #fff;
    border: solid 1px #fff;
    padding: 6px 9px;
    text-decoration: none;
  }

  a.cerrar {
    display: none;
    border-color: #ffffff;
  }
  a.ayuda:hover {
    background: #000;
    border-color: #eb6428;
    text-decoration: none;
    color: #eb6428;
  }
  #botDivFrame .btn-close {
    position: absolute;
    top: 5px;
    right: 5px;
    display: block;
    width: 39px;
    height: 39px;
    cursor: pointer;
    z-index: 17;
  }

  #botDivFrame .btn-close span {
    background: #ffffff;
    display: block;
    width: 15px;
    height: 2px;
    margin-top: 18px;
    margin-left: 10px;
  }

  #botDivFrame #frmWebChat {
    width: 400px;
    height: 500px;
    background-color: white;
    padding-right: 10px;
  }

  #frmWebChat body {
      margin: 0!important;
  }

  @media only screen and (min-width: 480px) {
    #botDiv.bottombutton {
      position: fixed;
      right: 42px;
      bottom: 48px;
      z-index: 1005;
      cursor: pointer;
    }

    #botDiv {
      font-family: "HyundaiSansHead-Regular", Sans-Serif;
    }

    #botDiv.bottombutton .botDivText {
      display: inline-block;
      width: 260px;
      height: 30px;
      position: absolute;
      right: 82px;
      bottom: 21px;
      z-index: 9;
      background-size: cover;
      color: #fff;
      overflow: hidden;
      border-radius: 0;
      text-align: center;
      cursor: pointer;
      background: url(globo-texto.gif);
      display: none;
    }
  }
</style>

</body>
</html>


