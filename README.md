# testpage
<html>
<body>
<h1>The Document Object</h1>
<h2>The querySelector() Method</h2>

<h3>Add a background color to the first p element:</h3>
<p>This is a p element.</p>
<p>This is a p element.</p>
  v
         
<script>
document.querySelector("p").style.backgroundColor = "red";
  ar div = document.createElement("div");
          document.getElementsByTagName("body")[0].appendChild(div);
          div.outerHTML =
            "<div id='bindbot-container'> <a class='cerrar-movil' href='#'>X</a> <div class='bindbot-button'>   <div id='botDiv' class='bottombutton'>     <span class='botSymbol bounce'>»</span>     <div class='botIcon rubberBand'><span></span></div>     <span class='botDivText'></span>   </div>   <div id='animate' class='icon-pulse'></div> </div> <div id='botDivFrame' class='bottombutton'>   <div style='display: flex; position: relative;'>     <p style='color: white;font-family:boldcitroen !important;font-size:18px;margin:0;padding-top:15px;padding-bottom:15px'>EN QUE TE PUEDO AYUDAR?</p>     <a class='ayuda' href='#'>?</a> <a class='cerrar' href='#'>X</a>     <div id='bloque_ayuda'>       <div class='texto'>         <div class='titulo'>           Comandos disponibles en Cotización y Test Drive         </div>         <div class='indicaciones'>           Usando estos comandos podrás realizar las acciones que se indican,           por ejemplo salir de cotización actual, o volver a la pregunta           anterior y seguir conversando con nosotros.         </div>         <ul class='comandos'>           <li><strong>Regresar</strong>: Regresar a la pregunta anterior.</li>           <li>             <strong>Ayuda</strong>: Muestra el tipo de respuestas que puedes             dar.           </li>           <li>             <strong>Salir</strong>: Salir del formulario sin terminarlo.           </li>           <li>             <strong>Reiniciar</strong>: Empezar de nuevo a llenar el             formulario. (Con los valores predeterminados con anterioridad).           </li>           <li>             <strong>Estado</strong>: Muestra el progreso en el llenado de la             forma hasta ahora.           </li>         </ul>       </div>     </div>     <span class='btn-close'> <span></span> </span>   </div>      <iframe     id='frmWebChat'     class='botFrame'     frameborder='0'     src='https://citroenchatbot.azurewebsites.net'   ></iframe> </div></div>"
  
          var optionbutton = "bottom";
  
          // para no usar animacion ingresar 'none'
          var animationPulse = "icon";
  
          getDom("#botDiv").classList.add(optionbutton + "button");
          getDom("#botDivFrame").classList.add(optionbutton + "button");
          getDom("#animate").classList.add(animationPulse + "-pulse");
  
</script>

</body>
</html>



