# notes
des notes de tout et n'importe quoi :p

## CSS
### responsive 
#### Medias flexibles
<pre>
img, object, embed, canvas, video, audio, picture {
	max-width: 100%;
	height: auto;
}
</pre>
#### Grille.flexible
Pour calculer les largeurs des blocs pour créer une mise en page flexible (avec des pourcentages)

Ideal resolution: 1280 * 960 pixels

- pour calculer la largeur des blocks, on fera le calcul suivant:
  * largeur pourcentage = taille block / taille ideal * 100
  <pre>
  // pour calculer avec la console js
  function size_flexible_blocs(opts){
    //size_flexible_blocs({widthIdealInPx: 1024, widthMainContainerIdealInPx: 1280})
    return opts.widthIdealInPx /  opts.widthMainContainerIdealInPx * 100;  
  }
</pre>

<pre>
.layout-main {
	height: 100%;
	margin: 0px auto 0px auto;
	min-height: 100%;
	width: 80%; /* Ideal: 1024px -> 1024 / 1280 */
}
</pre>

- pour calculer la font-size
  * tailleEM = Ideal taille / taille base body
  <pre>
  function size_font_flexible(opts){
    // example size_font_flexible({idealSizeinPx: 24, sizeBaseBody: 16})
    
    return opts.idealSizeinPx / opts.sizeBaseBody;
    //return 24/ 16 * 100;
  }
  </pre>
<pre>example:
.menu h1 {
	font-size: 1.5em; /* Ideal: 24px */
}</pre>

<pre>
// 100% height et width
// definition de la font-size  à 16px
html, body{
	height: 100%;
	background-color: #FFFFFF;
	border: 0px solid transparent;
	font-size: 1em; /* Ideal: 16px */
	margin: 0px 0px 0px 0px;
	min-height: 100%;
	padding: 0px 0px 0px 0px;
	width: 100%;
}
.layout-main {
	height: 100%;
	margin: 0px auto 0px auto;
	min-height: 100%;
	width: 80%; /* Ideal: 1024px -> 1024 / 1280 */
}
.main {
	height: 100%;
	min-height: 100%;
}
.layout-menu, .layout-content, .layout-adv {
	display: inline-block;
	height: 100%;
	min-height: 100%;
	vertical-align: top;
}
.layout-menu {
	color: #FFFFFF;
	background-color: #CC0000;
	width: 20.8984375%; /* Ideal: 214px -> 214 / 1024 */
}
.layout-content {
	color: #000000;
	background-color: #FFFFFF;
	width: 58.203125%; /* Ideal: 596px -> 596 / 1024 */
}
.layout-adv {
	color: #000000;
	background-color: #F9F7ED;
	width: 20.8984375%; /* Ideal: 214px -> 214 / 1024 */
}
</pre>
