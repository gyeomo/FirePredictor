<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>canino_화재예측과제_KernelSource</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="EDA">EDA<a class="anchor-link" href="#EDA">&#182;</a></h1>
<pre><code>{.python}
train_data = train_data.dropna(axis='columns',thresh=25000)
test_data = test_data.dropna(axis='columns',thresh=2300)
submission_data = submission_data.dropna(axis='columns',thresh=640)</code></pre>
<p>null 데이터가 많은 변수는 제거</p>

<pre><code>{.python}
fr_yn_mapping = {
    'N' : 0.0, 'Y' : 1.0
}</code></pre>
<p>label을 0과 1로 수치화</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="o">%</span><span class="k">matplotlib</span> inline
<span class="n">warnings</span><span class="o">.</span><span class="n">filterwarnings</span><span class="p">(</span><span class="s1">&#39;ignore&#39;</span><span class="p">)</span>

<span class="n">train_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;PJT002_train.csv&#39;</span><span class="p">)</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;PJT002_validation.csv&#39;</span><span class="p">)</span>
<span class="n">submission_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;PJT002_test.csv&#39;</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(((</span><span class="n">train_data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="nb">len</span><span class="p">(</span><span class="n">train_data</span><span class="p">))</span> <span class="o">&gt;</span><span class="mf">0.7</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
<span class="nb">print</span><span class="p">(((</span><span class="n">test_data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="nb">len</span><span class="p">(</span><span class="n">test_data</span><span class="p">))</span> <span class="o">&gt;</span><span class="mf">0.7</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
<span class="nb">print</span><span class="p">(((</span><span class="n">submission_data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="nb">len</span><span class="p">(</span><span class="n">submission_data</span><span class="p">))</span> <span class="o">&gt;</span><span class="mf">0.7</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>

<span class="n">train_data</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">dropna</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">,</span><span class="n">thresh</span><span class="o">=</span><span class="mi">25000</span><span class="p">)</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">test_data</span><span class="o">.</span><span class="n">dropna</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">,</span><span class="n">thresh</span><span class="o">=</span><span class="mi">2300</span><span class="p">)</span>
<span class="n">submission_data</span> <span class="o">=</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">dropna</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">,</span><span class="n">thresh</span><span class="o">=</span><span class="mi">640</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(((</span><span class="n">train_data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="nb">len</span><span class="p">(</span><span class="n">train_data</span><span class="p">))</span> <span class="o">&gt;</span><span class="mf">0.7</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
<span class="nb">print</span><span class="p">(((</span><span class="n">test_data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="nb">len</span><span class="p">(</span><span class="n">test_data</span><span class="p">))</span> <span class="o">&gt;</span><span class="mf">0.7</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
<span class="nb">print</span><span class="p">(((</span><span class="n">submission_data</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">/</span> <span class="nb">len</span><span class="p">(</span><span class="n">submission_data</span><span class="p">))</span> <span class="o">&gt;</span><span class="mf">0.7</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">())</span>
<span class="n">train_data</span> <span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">train_data</span><span class="p">,</span> <span class="n">test_data</span><span class="p">],</span> <span class="n">ignore_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">y_t</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">]</span>
<span class="n">y_v</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">]</span>

<span class="n">fr_yn_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">&#39;N&#39;</span> <span class="p">:</span> <span class="mf">0.0</span><span class="p">,</span> <span class="s1">&#39;Y&#39;</span> <span class="p">:</span> <span class="mf">1.0</span>
<span class="p">}</span>

<span class="n">fr_yn_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">fr_yn_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">y_t</span><span class="o">=</span> <span class="n">y_t</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">fr_yn_func</span><span class="p">)</span>
<span class="n">y_v</span><span class="o">=</span> <span class="n">y_v</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">fr_yn_func</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>23
23
24
0
0
0
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>명목형 변수와 화재발생여부의 관계를 살피기 위함</p>
<p>이를 통해 명목형 변수를 4분위 수로 나타낼 수 있음(1, 2, 3, 4)</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="mi">1</span> <span class="k">if</span> <span class="n">x</span><span class="o">==</span><span class="s1">&#39;Y&#39;</span> <span class="k">else</span> <span class="mi">0</span> <span class="p">)</span>

<span class="n">column_name</span> <span class="o">=</span> <span class="s1">&#39;rgnl_ar_nm&#39;</span>
<span class="n">view</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">,</span> <span class="n">column_name</span><span class="p">]]</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="n">column_name</span><span class="p">],</span> <span class="n">as_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span><span class="o">/</span><span class="n">train_data</span><span class="p">[[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">,</span> <span class="n">column_name</span><span class="p">]]</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="n">column_name</span><span class="p">],</span> <span class="n">as_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">count</span><span class="p">()</span>
<span class="n">view</span> <span class="o">=</span> <span class="n">view</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">view</span><span class="p">[</span><span class="n">column_name</span><span class="p">]</span> <span class="o">=</span> <span class="n">view</span><span class="o">.</span><span class="n">index</span>
<span class="n">view</span> <span class="o">=</span> <span class="n">view</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">drop</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">view</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[2]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>fr_yn</th>
      <th>rgnl_ar_nm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>0.000000</td>
      <td>제1종전용주거지역</td>
    </tr>
    <tr>
      <td>1</td>
      <td>0.000000</td>
      <td>관리지역</td>
    </tr>
    <tr>
      <td>2</td>
      <td>0.033333</td>
      <td>제2종전용주거지역</td>
    </tr>
    <tr>
      <td>3</td>
      <td>0.035714</td>
      <td>유통상업지역</td>
    </tr>
    <tr>
      <td>4</td>
      <td>0.090186</td>
      <td>개발제한구역</td>
    </tr>
    <tr>
      <td>5</td>
      <td>0.101030</td>
      <td>보전관리지역</td>
    </tr>
    <tr>
      <td>6</td>
      <td>0.104052</td>
      <td>제1종일반주거지역</td>
    </tr>
    <tr>
      <td>7</td>
      <td>0.111469</td>
      <td>생산관리지역</td>
    </tr>
    <tr>
      <td>8</td>
      <td>0.111582</td>
      <td>자연환경보전지역</td>
    </tr>
    <tr>
      <td>9</td>
      <td>0.113816</td>
      <td>계획관리지역</td>
    </tr>
    <tr>
      <td>10</td>
      <td>0.127389</td>
      <td>보전녹지지역</td>
    </tr>
    <tr>
      <td>11</td>
      <td>0.133427</td>
      <td>농림지역</td>
    </tr>
    <tr>
      <td>12</td>
      <td>0.147355</td>
      <td>제2종일반주거지역</td>
    </tr>
    <tr>
      <td>13</td>
      <td>0.153508</td>
      <td>자연녹지지역</td>
    </tr>
    <tr>
      <td>14</td>
      <td>0.178827</td>
      <td>준주거지역</td>
    </tr>
    <tr>
      <td>15</td>
      <td>0.219457</td>
      <td>생산녹지지역</td>
    </tr>
    <tr>
      <td>16</td>
      <td>0.245342</td>
      <td>준공업지역</td>
    </tr>
    <tr>
      <td>17</td>
      <td>0.265607</td>
      <td>일반상업지역</td>
    </tr>
    <tr>
      <td>18</td>
      <td>0.268657</td>
      <td>근린상업지역</td>
    </tr>
    <tr>
      <td>19</td>
      <td>0.310058</td>
      <td>일반공업지역</td>
    </tr>
    <tr>
      <td>20</td>
      <td>0.330612</td>
      <td>제3종일반주거지역</td>
    </tr>
    <tr>
      <td>21</td>
      <td>0.471698</td>
      <td>중심상업지역</td>
    </tr>
    <tr>
      <td>22</td>
      <td>0.500000</td>
      <td>용도미지정</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>실수형 데이터와 화재발생여부와의 관계를 살피기 위해 상관관계 plot을 그림</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">18</span><span class="p">,</span><span class="mi">18</span><span class="p">))</span>
<span class="n">sns</span><span class="o">.</span><span class="n">heatmap</span><span class="p">(</span><span class="n">data</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[[</span><span class="s1">&#39;bldng_ar&#39;</span><span class="p">,</span>
 <span class="s1">&#39;ttl_ar&#39;</span><span class="p">,</span>
 <span class="s1">&#39;lnd_ar&#39;</span><span class="p">,</span>
 <span class="s1">&#39;dt_of_athrztn&#39;</span><span class="p">,</span>
 <span class="s1">&#39;ttl_grnd_flr&#39;</span><span class="p">,</span>
 <span class="s1">&#39;ttl_dwn_flr&#39;</span><span class="p">,</span>
 <span class="s1">&#39;tmprtr&#39;</span><span class="p">,</span>
 <span class="s1">&#39;wnd_spd&#39;</span><span class="p">,</span>
 <span class="s1">&#39;wnd_drctn&#39;</span><span class="p">,</span>
 <span class="s1">&#39;hmdt&#39;</span><span class="p">,</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">]]</span><span class="o">.</span><span class="n">corr</span><span class="p">(),</span> <span class="n">annot</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
           <span class="n">fmt</span><span class="o">=</span><span class="s1">&#39;.2f&#39;</span><span class="p">,</span><span class="n">linewidths</span><span class="o">=.</span><span class="mi">5</span><span class="p">,</span><span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;Blues&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[3]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x26d01ac8cc0&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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rYmIiIiIiIhIGClqH+bRZrbYzG4zM90PXkRERERERMq9IrUwO+d6mFkr4GZgiZktBl53zn1eprUTERERERERIDIfyxTpivxQTefc98DfgPuB3sDzZrbWzK4oq8qJiIiIiIiIhEqREmYzO8PMRgJrgAuAy5xzp3vvR5Zh/URERERERERCoqg3/XoJGAs84Jw7mD3QObfNzP5WJjUTERERERERCaGi9mHudYJxE8xsinPuytKrloiIiIiIiORm5ePpWBGlyH2YC9G8lOYjIiIiIiIiEhZKK2GO+Adoi4iIiIiIiORWWgmziIiIiIiISLlS1Jt+FUYX04uIiIiIiJQhPYc5+AptYTazymY2sZBi95dSfURERERERETCQqEJs3MuE0g0s1NOUObzUq2ViIiIiIiISIgV9ZLsH4F5ZvYRsD97oHPuubKolIiIiIiIiEionbCF2cwmeG8HAVO98tG5XiIiIiIiIhIEVg5ekaawFubOZvYLYDPwYhDqIyIiIiIiIhIWCkuYRwOfAs2AJbmGG4FnLzcvo3qJiIiIiIiIhNQJL8l2zr3gnDsdGOeca57r1cw5p2RZREREREREyq0i3fTLOfeHsq6IiIiIiIiInEAkdgKOcIU+VkpERERERESkIlLCLCIiIiIiIuKjqM9hFhERERERkRAyXZMddGphFhEREREREfGhhFlERERERETEhxJmERERERERER/qwywiIiIiIhIBTF2Yg04tzCIiIiIiIiI+lDCLiIiIiIiI+FDCLCIiIiIiIuJDfZhFREREREQigLowB59amEVERERERER8KGEWERERERER8aGEWURERERERMSH+jCLiIiIiIhEAnViDjq1MIuIiIiIiIj4UMIsIiIiIiIi4kMJs4iIiIiIiIgP9WEWERERERGJAKZOzEGnFmYRERERERERH0qYRURERERERHwoYRYRERERERHxoT7MIiIiIiIiEcDUhTno1MIsIiIiIiIi4sOcc8FYTlAWIiIiIiIi4qNctM0eyoj8vKp6lcj6XwQrYQ5rZjbUOTcm1PWIZIphySh+JaP4lZxiWDKKX8kofiWnGJaM4lcyip+UZ7okO2BoqCtQDiiGJaP4lYziV3KKYckofiWj+JWcYlgyil/JKH5SbilhFhEREREREfGhhFlERERERETEhxLmAPW5KDnFsGQUv5JR/EpOMSwZ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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>수치형 데이터를 가변수로 변환시켰을 경우 더 높은 정확률을 갖는지 실험하기 위함</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">name</span> <span class="o">=</span> <span class="s1">&#39;ttl_ar&#39;</span>
<span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">,</span><span class="s1">&#39;mlt_us_yn&#39;</span><span class="p">,</span><span class="s1">&#39;jmk&#39;</span><span class="p">],</span>
                                        <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;dump&#39;</span><span class="p">]</span><span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">qcut</span><span class="p">(</span><span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">],</span><span class="mi">4</span><span class="p">,</span><span class="n">duplicates</span><span class="o">=</span><span class="s1">&#39;drop&#39;</span><span class="p">)</span>
<span class="n">column_create</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;dump&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">unique</span><span class="p">())):</span>
    <span class="n">column_create</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">i</span><span class="p">))</span>
<span class="c1">#print(column_create)</span>
<span class="c1">#if name == &#39;fr_yn&#39;:</span>
<span class="c1">#    continue</span>
<span class="c1">#if len(column_create) &lt; 2:</span>
<span class="c1">#    train_data[&#39;dump&#39;]=pd.cut(train_data[name],[train_data[name].min(),train_data[name].mean(),train_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])</span>
<span class="c1">#    train_data[&#39;dump&#39;] = train_data[&#39;dump&#39;].astype(&#39;object&#39;)</span>
<span class="c1">#    train_data[&#39;dump&#39;]=  train_data[&#39;dump&#39;].fillna(&#39;0&#39;)</span>
<span class="c1">#    print(train_data[&#39;dump&#39;].isnull().sum())</span>
<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;dump&#39;</span><span class="p">]</span><span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">qcut</span><span class="p">(</span><span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">],</span><span class="mi">4</span><span class="p">,</span><span class="n">duplicates</span><span class="o">=</span><span class="s1">&#39;drop&#39;</span><span class="p">,</span> <span class="n">labels</span><span class="o">=</span><span class="n">column_create</span><span class="p">)</span>
<span class="n">train_data</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;dump&#39;</span><span class="p">])[</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">to_frame</span><span class="p">()</span><span class="o">.</span><span class="n">style</span><span class="o">.</span><span class="n">background_gradient</span><span class="p">(</span><span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;summer_r&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[4]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<style  type="text/css" >
    #T_ac103088_1d6d_11ea_ac36_0a152af2a404row0_col0 {
            background-color:  #ffff66;
            color:  #000000;
        }    #T_ac103088_1d6d_11ea_ac36_0a152af2a404row1_col0 {
            background-color:  #c3e166;
            color:  #000000;
        }    #T_ac103088_1d6d_11ea_ac36_0a152af2a404row2_col0 {
            background-color:  #abd566;
            color:  #000000;
        }    #T_ac103088_1d6d_11ea_ac36_0a152af2a404row3_col0 {
            background-color:  #008066;
            color:  #f1f1f1;
        }</style><table id="T_ac103088_1d6d_11ea_ac36_0a152af2a404" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >fr_yn</th>    </tr>    <tr>        <th class="index_name level0" >dump</th>        <th class="blank" ></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_ac103088_1d6d_11ea_ac36_0a152af2a404level0_row0" class="row_heading level0 row0" >0</th>
                        <td id="T_ac103088_1d6d_11ea_ac36_0a152af2a404row0_col0" class="data row0 col0" >0.0411473</td>
            </tr>
            <tr>
                        <th id="T_ac103088_1d6d_11ea_ac36_0a152af2a404level0_row1" class="row_heading level0 row1" >1</th>
                        <td id="T_ac103088_1d6d_11ea_ac36_0a152af2a404row1_col0" class="data row1 col0" >0.0980997</td>
            </tr>
            <tr>
                        <th id="T_ac103088_1d6d_11ea_ac36_0a152af2a404level0_row2" class="row_heading level0 row2" >2</th>
                        <td id="T_ac103088_1d6d_11ea_ac36_0a152af2a404row2_col0" class="data row2 col0" >0.120075</td>
            </tr>
            <tr>
                        <th id="T_ac103088_1d6d_11ea_ac36_0a152af2a404level0_row3" class="row_heading level0 row3" >3</th>
                        <td id="T_ac103088_1d6d_11ea_ac36_0a152af2a404row3_col0" class="data row3 col0" >0.281046</td>
            </tr>
    </tbody></table>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_data</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;dump&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>실수형 데이터중에서 null 데이터가 많은 데이터를 제거하여(변수선택) 정확도를 더 높임</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">test_list</span> <span class="o">=</span> <span class="p">[</span>
    <span class="s1">&#39;gas_engry_us_201401&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201401&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201402&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201402&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201403&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201403&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201404&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201404&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201405&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201405&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201406&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201406&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201407&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201407&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201408&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201408&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201409&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201409&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201410&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201410&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201411&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201411&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201412&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201412&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201501&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201501&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201502&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201502&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201503&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201503&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201504&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201504&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201505&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201505&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201506&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201506&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201507&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201507&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201508&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201508&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201509&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201509&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201510&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201510&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201511&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201511&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201512&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201512&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201601&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201601&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201602&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201602&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201603&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201603&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201604&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201604&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201605&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201605&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201606&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201606&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201607&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201607&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201608&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201608&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201609&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201609&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201610&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201610&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201611&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201611&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201612&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201612&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201701&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201701&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201702&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201702&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201703&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201703&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201704&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201704&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201705&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201705&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201706&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201706&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201707&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201707&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201708&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201708&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201709&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201709&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201710&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201710&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201711&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201711&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201712&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201712&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201801&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201801&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201802&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201802&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201803&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201803&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201804&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201804&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201805&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201805&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201806&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201806&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201807&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201807&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201808&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201808&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201809&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201809&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201810&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201810&#39;</span><span class="p">,</span><span class="s1">&#39;gas_engry_us_201811&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201811&#39;</span><span class="p">,</span>
<span class="s1">&#39;gas_engry_us_201812&#39;</span><span class="p">,</span><span class="s1">&#39;ele_engry_us_201812&#39;</span>
<span class="p">]</span>

<span class="c1">#train_data = train_data.drop(test_list, axis=&#39;columns&#39;)</span>
<span class="n">train_data</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">test_list</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">)</span>
<span class="n">submission_data</span> <span class="o">=</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">test_list</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Feature-Engineering">Feature Engineering<a class="anchor-link" href="#Feature-Engineering">&#182;</a></h1><p>실수형과 정수형 데이터에 있는 null 값을 ['emd_nm','mlt_us_yn','jmk']를 기준으로 채움</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_data</span><span class="o">.</span><span class="n">dt_of_athrztn</span> <span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">train_data</span><span class="o">.</span><span class="n">dt_of_athrztn</span><span class="p">,</span> <span class="n">errors</span><span class="o">=</span><span class="s1">&#39;coerce&#39;</span><span class="p">)</span> 

<span class="n">column_float</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">train_data</span><span class="o">.</span><span class="n">columns</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">train_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">dtypes</span> <span class="o">==</span> <span class="s1">&#39;float64&#39;</span><span class="p">:</span>
        <span class="n">column_float</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<span class="c1">#print(column_float)</span>
<span class="k">for</span> <span class="n">name</span> <span class="ow">in</span> <span class="n">column_float</span><span class="p">:</span>        
    <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">,</span><span class="s1">&#39;mlt_us_yn&#39;</span><span class="p">,</span><span class="s1">&#39;jmk&#39;</span><span class="p">],</span>
                                            <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">median</span><span class="p">()))</span>
    <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    
<span class="n">column_float</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">columns</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">dtypes</span> <span class="o">==</span> <span class="s1">&#39;float64&#39;</span><span class="p">:</span>
        <span class="n">column_float</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<span class="c1">#print(column_float)</span>
<span class="k">for</span> <span class="n">name</span> <span class="ow">in</span> <span class="n">column_float</span><span class="p">:</span>        
    <span class="n">submission_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">,</span><span class="s1">&#39;mlt_us_yn&#39;</span><span class="p">,</span><span class="s1">&#39;jmk&#39;</span><span class="p">],</span>
                                            <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">median</span><span class="p">()))</span>
    <span class="n">submission_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    

<span class="n">column_int</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">train_data</span><span class="o">.</span><span class="n">columns</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">train_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">dtypes</span> <span class="o">==</span> <span class="s1">&#39;int64&#39;</span><span class="p">:</span>
        <span class="n">column_int</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<span class="k">for</span> <span class="n">name</span> <span class="ow">in</span> <span class="n">column_int</span><span class="p">:</span>        
    <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">,</span><span class="s1">&#39;mlt_us_yn&#39;</span><span class="p">,</span><span class="s1">&#39;jmk&#39;</span><span class="p">],</span>
                                            <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">median</span><span class="p">()))</span>
    <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    
<span class="n">column_int</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">columns</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">dtypes</span> <span class="o">==</span> <span class="s1">&#39;int64&#39;</span><span class="p">:</span>
        <span class="n">column_int</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<span class="k">for</span> <span class="n">name</span> <span class="ow">in</span> <span class="n">column_int</span><span class="p">:</span>        
    <span class="n">submission_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">,</span><span class="s1">&#39;mlt_us_yn&#39;</span><span class="p">,</span><span class="s1">&#39;jmk&#39;</span><span class="p">],</span>
                                            <span class="n">sort</span><span class="o">=</span><span class="kc">False</span><span class="p">)[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">x</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">median</span><span class="p">()))</span>
    <span class="n">submission_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">name</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>명목형 변수를 4분위 수로 나눔</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">bldng_us_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;공공용시설&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;파출소&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;시장&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;판매및영업시설&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;단독주택&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;발전시설&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;창고시설&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;근린생활시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;노유자시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;동.식물 관련시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;위험물저장및처리시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;종교시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;제1종근린생활시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;제2종근린생활시설&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;교정및군사시설&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;교육연구및복지시설&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;묘지관련시설&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;숙박시설&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;문화및집회시설&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;방송통신시설&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;공장&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;위락시설&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;교육연구시설&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;운동시설&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;운수시설&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;업무시설&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;분뇨.쓰레기처리시설&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;공동주택&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;자동차관련시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;수련시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;의료시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;장례식장&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;판매시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;관광휴게시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">bldng_us_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">bldng_us_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>


<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;bldng_us&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;bldng_us&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_us_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;bldng_us&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;bldng_us&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_us_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;bldng_us&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;bldng_us&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_us_func</span><span class="p">)</span>

<span class="n">bldng_archtctr_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;통나무구조&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;석구조&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;벽돌구조&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;일반목구조&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;조적구조&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;목구조&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;기타조적구조&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;블록구조&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;일반목구조&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;통나무구조&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;강파이프구조&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;기타구조&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;경량철골구조&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;기타강구조&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;철근콘크리트구조&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;일반철골구조&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;프리케스트콘크리트구조&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;철골콘크리트구조&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;기타콘크리트구조&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;철골철근콘크리트구조&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">bldng_archtctr_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">bldng_archtctr_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;bldng_archtctr&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;bldng_archtctr&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_archtctr_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;bldng_archtctr&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;bldng_archtctr&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_archtctr_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;bldng_archtctr&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;bldng_archtctr&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_archtctr_func</span><span class="p">)</span>

<span class="n">bldng_us_clssfctn_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;주거용&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;기타&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;농수산용&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;상업용&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;문교사회용&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;공공용&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;공업용&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">bldng_us_clssfctn_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">bldng_us_clssfctn_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;bldng_us_clssfctn&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;bldng_us_clssfctn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_us_clssfctn_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;bldng_us_clssfctn&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;bldng_us_clssfctn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_us_clssfctn_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;bldng_us_clssfctn&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;bldng_us_clssfctn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">bldng_us_clssfctn_func</span><span class="p">)</span>

<span class="n">jmk_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;수&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;구&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;천&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;과&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;묘&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;도&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;임&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;전&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;답&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;제&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;유&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;대&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;목&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;창&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;종&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;철&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;원&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;잡&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;주&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;공&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;양&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;학&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;사&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;장&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;체&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;차&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span>
<span class="p">}</span>

<span class="n">jmk_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">jmk_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;jmk&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;jmk&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">jmk_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;jmk&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;jmk&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">jmk_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;jmk&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;jmk&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">jmk_func</span><span class="p">)</span>

<span class="n">rgnl_ar_nm_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;제1종전용주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;제2종전용주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;유통상업지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;개발제한구역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;보전관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;제1종일반주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;생산관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;자연환경보전지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;계획관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;보전녹지지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;농림지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;제2종일반주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;자연녹지지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;준주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;생산녹지지역&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;준공업지역&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;일반상업지역&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;근린상업지역&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;일반공업지역&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;제3종일반주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;중심상업지역&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;용도미지정&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">rgnl_ar_nm_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">rgnl_ar_nm_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rgnl_ar_nm_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rgnl_ar_nm_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rgnl_ar_nm_func</span><span class="p">)</span>

<span class="n">rgnl_ar_nm2_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;개발제한구역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;농림지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;생산녹지지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;제3종일반주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;계획관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;지정되지않음&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;일반상업지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;생산관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;일반공업지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;보전관리지역&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;준공업지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;제1종일반주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;제2종일반주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;자연녹지지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;준주거지역&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span>
<span class="p">}</span>

<span class="n">rgnl_ar_nm2_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">rgnl_ar_nm2_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rgnl_ar_nm2_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rgnl_ar_nm2_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rgnl_ar_nm2_func</span><span class="p">)</span>

<span class="n">lnd_us_sttn_nm_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;경마장&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;콘도미니엄&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;유원지&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;특수기타&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;스키장&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;발전소&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;도로등&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;조림&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;하천등&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;자연림&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;전&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;목장용지&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;토지임야&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;답&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;과수원&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;단독&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;주거나지&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span><span class="s2">&quot;임야기타&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;전기타&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;답기타&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;공원등&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;주거기타&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;주상나지&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;골프장 회원제&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;주상기타&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;다세대&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;연립&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;상주상용업기타&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;골프장 대중제&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;상업기타&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;공업기타&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;공원묘지&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;업무용&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;상업나지&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;공업나지&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;상업용&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span><span class="s2">&quot;주상용&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;기타&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;공업용&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;운동장등&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;위험시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;유해.혐오시설&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span><span class="s2">&quot;주차장등&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;아파트&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;여객자동차터미널&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;고속도로휴게소&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">lnd_us_sttn_nm_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">lnd_us_sttn_nm_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;lnd_us_sttn_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;lnd_us_sttn_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">lnd_us_sttn_nm_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;lnd_us_sttn_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;lnd_us_sttn_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">lnd_us_sttn_nm_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;lnd_us_sttn_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;lnd_us_sttn_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">lnd_us_sttn_nm_func</span><span class="p">)</span>

<span class="n">rd_sd_nm_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;세로한면(불)&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;맹지&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;세로각지(불)&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;세로각지(가)&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;세로한면(가)&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;소로각지&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;지정되지않음&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;소로한면&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;광대로한면&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;중로한면&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;광대세각&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;중로각지&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;광대소각&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">rd_sd_nm_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">rd_sd_nm_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;rd_sd_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;rd_sd_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rd_sd_nm_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;rd_sd_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;rd_sd_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rd_sd_nm_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;rd_sd_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;rd_sd_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">rd_sd_nm_func</span><span class="p">)</span>

<span class="n">emd_nm_mapping</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;경상남도 김해시 어방동&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span><span class="s2">&quot;경상남도 김해시 칠산서부동&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 대동면&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 동상동&quot;</span><span class="p">:</span><span class="s1">&#39;1&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 회현동&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 한림면&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 진영읍&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 불암동&quot;</span><span class="p">:</span><span class="s1">&#39;2&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 진례면&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 삼안동&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span><span class="s2">&quot;경상남도 김해시 생림면&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 상동면&quot;</span><span class="p">:</span><span class="s1">&#39;3&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 부원동&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 활천동&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 북부동&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 장유3동&quot;</span><span class="p">:</span><span class="s1">&#39;4&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 주촌면&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 내외동&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span> <span class="s2">&quot;경상남도 김해시 장유1동&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span><span class="p">,</span>
    <span class="s2">&quot;경상남도 김해시 장유2동&quot;</span><span class="p">:</span><span class="s1">&#39;5&#39;</span>
<span class="p">}</span>

<span class="n">emd_nm_func</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">x</span><span class="p">:</span><span class="n">emd_nm_mapping</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">x</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">emd_nm_func</span><span class="p">)</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">emd_nm_func</span><span class="p">)</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;emd_nm&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">emd_nm_func</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>실수형 데이터에 log를 취하여 스케일링을 진행함</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">train_data</span><span class="o">.</span><span class="n">columns</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">train_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">dtypes</span> <span class="o">==</span> <span class="s1">&#39;float64&#39;</span><span class="p">:</span>  
        <span class="n">train_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">i</span><span class="p">:</span> <span class="n">np</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="n">i</span><span class="p">)</span> <span class="k">if</span> <span class="n">i</span> <span class="o">&gt;</span> <span class="mi">0</span> <span class="k">else</span> <span class="mi">0</span><span class="p">)</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">submission_data</span><span class="o">.</span><span class="n">columns</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">dtypes</span> <span class="o">==</span> <span class="s1">&#39;float64&#39;</span><span class="p">:</span>  
        <span class="n">submission_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">i</span><span class="p">:</span> <span class="n">np</span><span class="o">.</span><span class="n">log</span><span class="p">(</span><span class="n">i</span><span class="p">)</span> <span class="k">if</span> <span class="n">i</span> <span class="o">&gt;</span> <span class="mi">0</span> <span class="k">else</span> <span class="mi">0</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>수치형 데이터를 4분위수로 나누어서 정확도를 높이려 했으나, 더 낮아지는 효과가 있으므로 주석처리</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">name_list = [&#39;ttl_dwn_flr&#39;,  &#39;ttl_ar&#39;]#,&#39;bldng_ar&#39;, &#39;lnd_ar&#39;, &#39;tmprtr&#39;, &#39;wnd_spd&#39;, &#39;wnd_drctn&#39;, &#39;hmdt&#39;, &#39;hm_cnt&#39;, &#39;bldng_ar_prc&#39;]</span>
<span class="sd">for name in name_list:</span>
<span class="sd">    try:</span>
<span class="sd">        #train_data[name] = pd.qcut(train_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])</span>
<span class="sd">        test_data[name] = pd.qcut(test_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])</span>
<span class="sd">        submission_data[name] = pd.qcut(submission_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])</span>
<span class="sd">    except ValueError:</span>
<span class="sd">        #train_data[name]=pd.cut(train_data[name],[train_data[name].min(),train_data[name].mean(),train_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])</span>
<span class="sd">        #train_data[name] = train_data[name].astype(&#39;object&#39;)</span>
<span class="sd">        #train_data[name]=  train_data[name].fillna(&#39;0&#39;)</span>
<span class="sd">        </span>
<span class="sd">        test_data[name]=pd.cut(test_data[name],[test_data[name].min(),test_data[name].mean(),test_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])</span>
<span class="sd">        test_data[name] = test_data[name].astype(&#39;object&#39;)</span>
<span class="sd">        test_data[name]=  test_data[name].fillna(&#39;0&#39;)</span>

<span class="sd">        submission_data[name]=pd.cut(submission_data[name],[submission_data[name].min(),submission_data[name].mean(),submission_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])</span>
<span class="sd">        submission_data[name] = submission_data[name].astype(&#39;object&#39;)</span>
<span class="sd">        submission_data[name]=  submission_data[name].fillna(&#39;0&#39;)</span>
<span class="sd">        continue</span>
<span class="sd">&#39;&#39;&#39;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[10]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&#34;\nname_list = [&#39;ttl_dwn_flr&#39;,  &#39;ttl_ar&#39;]#,&#39;bldng_ar&#39;, &#39;lnd_ar&#39;, &#39;tmprtr&#39;, &#39;wnd_spd&#39;, &#39;wnd_drctn&#39;, &#39;hmdt&#39;, &#39;hm_cnt&#39;, &#39;bldng_ar_prc&#39;]\nfor name in name_list:\n    try:\n        #train_data[name] = pd.qcut(train_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])\n        test_data[name] = pd.qcut(test_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])\n        submission_data[name] = pd.qcut(submission_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])\n    except ValueError:\n        #train_data[name]=pd.cut(train_data[name],[train_data[name].min(),train_data[name].mean(),train_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])\n        #train_data[name] = train_data[name].astype(&#39;object&#39;)\n        #train_data[name]=  train_data[name].fillna(&#39;0&#39;)\n        \n        test_data[name]=pd.cut(test_data[name],[test_data[name].min(),test_data[name].mean(),test_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])\n        test_data[name] = test_data[name].astype(&#39;object&#39;)\n        test_data[name]=  test_data[name].fillna(&#39;0&#39;)\n\n        submission_data[name]=pd.cut(submission_data[name],[submission_data[name].min(),submission_data[name].mean(),submission_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])\n        submission_data[name] = submission_data[name].astype(&#39;object&#39;)\n        submission_data[name]=  submission_data[name].fillna(&#39;0&#39;)\n        continue\n&#34;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">int_name = [&#39;fr_sttn_dstnc&#39;, &#39;fr_wthr_fclt_dstnc&#39;, &#39;bldng_cnt&#39;,&#39;tbc_rtl_str_dstnc&#39;,</span>
<span class="sd">               &#39;cctv_dstnc&#39;, &#39;no_tbc_zn_dstnc&#39;,&#39;sft_emrgnc_bll_dstnc&#39;,&#39;ahsm_dstnc&#39;,</span>
<span class="sd">               &#39;cctv_in_100m&#39;, &#39;fr_wthr_fclt_in_100m&#39;, &#39;bldng_cnt_in_50m&#39;]</span>
<span class="sd">&#39;&#39;&#39;</span>
<span class="sd">&#39;&#39;&#39;</span>
<span class="sd">for name in int_name:</span>
<span class="sd">    try:</span>
<span class="sd">        test_data[name] = pd.qcut(test_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])</span>
<span class="sd">        submission_data[name] = pd.qcut(submission_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])</span>
<span class="sd">    except ValueError:</span>
<span class="sd">        test_data[name]=pd.cut(test_data[name],[test_data[name].min(),test_data[name].mean(),test_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])</span>
<span class="sd">        test_data[name] = test_data[name].astype(&#39;object&#39;)</span>
<span class="sd">        test_data[name]=  test_data[name].fillna(&#39;0&#39;)</span>

<span class="sd">        submission_data[name]=pd.cut(submission_data[name],[submission_data[name].min(),submission_data[name].mean(),submission_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])</span>
<span class="sd">        submission_data[name] = submission_data[name].astype(&#39;object&#39;)</span>
<span class="sd">        submission_data[name]=  submission_data[name].fillna(&#39;0&#39;)</span>
<span class="sd">&#39;&#39;&#39;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[11]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&#34;\nfor name in int_name:\n    try:\n        test_data[name] = pd.qcut(test_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])\n        submission_data[name] = pd.qcut(submission_data[name], 4, labels=[&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;])\n    except ValueError:\n        test_data[name]=pd.cut(test_data[name],[test_data[name].min(),test_data[name].mean(),test_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])\n        test_data[name] = test_data[name].astype(&#39;object&#39;)\n        test_data[name]=  test_data[name].fillna(&#39;0&#39;)\n\n        submission_data[name]=pd.cut(submission_data[name],[submission_data[name].min(),submission_data[name].mean(),submission_data[name].max()], labels=[&#39;1&#39;,&#39;2&#39;])\n        submission_data[name] = submission_data[name].astype(&#39;object&#39;)\n        submission_data[name]=  submission_data[name].fillna(&#39;0&#39;)\n&#34;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>object 형식의 날짜 데이터를 시간과 계절로 나눔</p>
<p>실제로 가을과 겨울에 더 높은 확률로 화재가 발생하고</p>
<p>낮 시간과 저녁 시간에 화재가 더 많이 난다는 통계자료를 바탕으로 진행함</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">]</span>
<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">((</span><span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="mi">5</span><span class="p">:</span><span class="mi">7</span><span class="p">])</span><span class="o">%</span><span class="k">12</span> + 3)/3))
<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;object&#39;</span><span class="p">)</span>

<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">]</span>
<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">(</span><span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="mi">11</span><span class="p">:</span><span class="mi">13</span><span class="p">])</span><span class="o">/</span><span class="mi">6</span><span class="p">))</span>
<span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;object&#39;</span><span class="p">)</span>

<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">]</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">((</span><span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="mi">5</span><span class="p">:</span><span class="mi">7</span><span class="p">])</span><span class="o">%</span><span class="k">12</span> + 3)/3))
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;object&#39;</span><span class="p">)</span>

<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">]</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">(</span><span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="mi">11</span><span class="p">:</span><span class="mi">13</span><span class="p">])</span><span class="o">/</span><span class="mi">6</span><span class="p">))</span>
<span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;object&#39;</span><span class="p">)</span>

<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">]</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">((</span><span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="mi">5</span><span class="p">:</span><span class="mi">7</span><span class="p">])</span><span class="o">%</span><span class="k">12</span> + 3)/3))
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;season&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;object&#39;</span><span class="p">)</span>

<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">]</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">(</span><span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="mi">11</span><span class="p">:</span><span class="mi">13</span><span class="p">])</span><span class="o">/</span><span class="mi">6</span><span class="p">))</span>
<span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="s1">&#39;time&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;object&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#&#39;tmprtr&#39;,&#39;wnd_spd&#39;, &#39;fr_wthr_fclt_in_100m&#39;, &#39;cctv_dstnc&#39;,&#39;bldng_ar_prc&#39;,&#39;tbc_rtl_str_dstnc&#39;,&#39;ahsm_dstnc&#39;,&#39;cctv_in_100m&#39;,&#39;hm_cnt&#39;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>필요하지 않은 변수를 삭제함</p>
<p>rgnl_ar_nm2 같은 경우 포함시키면 오히려 정확도가 낮아져서 삭제함</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X_train</span> <span class="o">=</span> <span class="n">train_data</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s1">&#39;dt_of_fr&#39;</span><span class="p">,</span><span class="s1">&#39;fr_yn&#39;</span><span class="p">,</span><span class="s1">&#39;id&#39;</span><span class="p">,</span> <span class="s1">&#39;rgnl_ar_nm2&#39;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="s1">&#39;columns&#39;</span><span class="p">)</span>
<span class="c1">#X_validation = test_data.drop([&#39;dt_of_fr&#39;,&#39;fr_yn&#39;,&#39;id&#39;, &#39;rgnl_ar_nm2&#39;], axis=&#39;columns&#39;)</span>
<span class="n">x_submission</span> <span class="o">=</span> <span class="n">submission_data</span><span class="p">[</span><span class="n">X_train</span><span class="o">.</span><span class="n">columns</span><span class="p">]</span>

<span class="n">X_train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">get_dummies</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">dummy_na</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="c1">#X_validation = pd.get_dummies(X_validation, dummy_na=True)</span>
<span class="n">x_submission</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">get_dummies</span><span class="p">(</span><span class="n">x_submission</span><span class="p">,</span> <span class="n">dummy_na</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">X_train</span> <span class="o">=</span> <span class="n">X_train</span><span class="p">[</span><span class="n">x_submission</span><span class="o">.</span><span class="n">columns</span><span class="p">]</span>
<span class="c1">#X_validation = X_validation[x_submission.columns]</span>
<span class="n">X_columns</span> <span class="o">=</span> <span class="n">X_train</span><span class="o">.</span><span class="n">columns</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">X_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>
<span class="c1">#print(X_validation.shape[1])</span>
<span class="nb">print</span><span class="p">(</span><span class="n">x_submission</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>85
85
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>RobustScaler로 이상치를 제거하고</p>
<p>Imputer로 빠진 데이터를 채우고</p>
<p>StandardScaler로 정규화 시킴</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="k">import</span> <span class="n">RobustScaler</span>
<span class="n">X_train</span> <span class="o">=</span> <span class="n">RobustScaler</span><span class="p">()</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="c1">#X_validation = RobustScaler().fit_transform(X_validation)</span>
<span class="n">x_submission</span> <span class="o">=</span> <span class="n">RobustScaler</span><span class="p">()</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">x_submission</span><span class="p">)</span>

<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="k">import</span> <span class="n">Imputer</span>
<span class="n">imr</span> <span class="o">=</span> <span class="n">Imputer</span><span class="p">(</span><span class="n">missing_values</span><span class="o">=</span><span class="s1">&#39;NaN&#39;</span><span class="p">,</span> <span class="n">strategy</span><span class="o">=</span><span class="s1">&#39;median&#39;</span><span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">X_train</span> <span class="o">=</span><span class="n">imr</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="c1">#X_validation =imr.fit_transform(X_validation)</span>
<span class="n">x_submission</span> <span class="o">=</span><span class="n">imr</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">x_submission</span><span class="p">)</span>

<span class="kn">from</span> <span class="nn">xgboost</span> <span class="k">import</span> <span class="n">XGBClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="k">import</span> <span class="n">StandardScaler</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="k">import</span> <span class="n">train_test_split</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="k">import</span> <span class="o">*</span>

<span class="n">X_train</span> <span class="o">=</span> <span class="n">StandardScaler</span><span class="p">()</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="c1">#X_validation = StandardScaler().fit_transform(X_validation)</span>
<span class="n">x_submission</span> <span class="o">=</span> <span class="n">StandardScaler</span><span class="p">()</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">x_submission</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>C:\Anaconda\lib\site-packages\sklearn\utils\deprecation.py:66: DeprecationWarning: Class Imputer is deprecated; Imputer was deprecated in version 0.20 and will be removed in 0.22. Import impute.SimpleImputer from sklearn instead.
  warnings.warn(msg, category=DeprecationWarning)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Modeling">Modeling<a class="anchor-link" href="#Modeling">&#182;</a></h1><p>RandomizedSearchCV로 최적의 모델 파라미터를 찾음</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">from sklearn.metrics import mean_squared_error</span>
<span class="sd">from sklearn.metrics.scorer import make_scorer</span>

<span class="sd">def custom_loss(y_true, y_pred):</span>
<span class="sd">    most_big = 0</span>
<span class="sd">    idx = 0</span>
<span class="sd">    for i in np.arange(0.01, 0.7, 0.001):</span>
<span class="sd">        pred = pd.Series(y_pred).apply(lambda x: 1 if x &gt;= i else 0)</span>
<span class="sd">        loss = f1_score(y_true,pred, pos_label=1.0)</span>
<span class="sd">        if most_big &lt; loss:</span>
<span class="sd">            most_big = loss</span>
<span class="sd">            idx = i</span>
<span class="sd">    y_pred = pd.Series(y_pred).apply(lambda x: 1 if x &gt;= idx else 0)</span>
<span class="sd">    return f1_score(y_true,y_pred, pos_label=1.0)</span>
<span class="sd">def rmsew_loss(y_true, y_pred):</span>
<span class="sd">    value = mean_squared_error(y_true,y_pred,sample_weight = y_true)</span>
<span class="sd">    if value &lt; 0 :</span>
<span class="sd">        value = -value</span>
<span class="sd">    return value</span>
<span class="sd">scorer = make_scorer(custom_loss, greater_is_better=True)</span>

<span class="sd">################### test</span>
<span class="sd">from sklearn.model_selection import RandomizedSearchCV, KFold</span>
<span class="sd">import scipy as sp</span>
<span class="sd">import scipy.stats as stats</span>
<span class="sd">from xgboost import XGBRegressor</span>
<span class="sd">kfold = KFold(n_splits=10, shuffle=True, random_state=0)</span>
<span class="sd">clf_xgb = XGBRegressor( n_jobs=4)</span>
<span class="sd">               </span>
<span class="sd">param_dist = {&#39;n_estimators&#39;: stats.randint(150, 1500),</span>
<span class="sd">              &#39;objective&#39;:[&#39;reg:linear&#39;,&#39;reg:tweedie&#39;,&#39;reg:logistic&#39;],</span>
<span class="sd">              &#39;learning_rate&#39;: stats.uniform(0.001, 0.6),</span>
<span class="sd">              &#39;max_depth&#39;: [3, 4, 5, 6, 7, 8, 9,10,11,12,13],</span>
<span class="sd">              &#39;gamma&#39;: stats.uniform(0.01, 2.0),</span>
<span class="sd">              &#39;reg_lambda&#39;: stats.uniform(0.1, 50),</span>
<span class="sd">              &#39;reg_alpha&#39;: stats.uniform(0.1, 50),</span>
<span class="sd">              &#39;subsample&#39;: [0.5,0.6,0.7,0.8,0.9],</span>
<span class="sd">              &#39;colsample_bytree&#39;: [0.5,0.6,0.7,0.8,0.9],</span>
<span class="sd">              &#39;min_child_weight&#39;: stats.randint(1, 12)</span>
<span class="sd">             }</span>
<span class="sd">clf = RandomizedSearchCV(clf_xgb, param_distributions = param_dist, n_iter = 50, scoring = scorer, cv=kfold, error_score = 0, verbose = 5, n_jobs = 4, random_state=42)</span>

<span class="sd">clf.fit(X_validation, y_v)</span>

<span class="sd">best_score = clf.best_score_</span>
<span class="sd">best_params = clf.best_params_</span>
<span class="sd">best_estimator_ = clf.best_estimator_</span>
<span class="sd">print(&quot;Best score: {}&quot;.format(best_score))</span>
<span class="sd">print(&quot;Best params: {}&quot;.format(best_params))</span>
<span class="sd">print(&quot;Best estimator_: {}&quot;.format(best_estimator_))</span>
<span class="sd">################### test</span>

<span class="sd">pred = clf.predict(X_validation)</span>
<span class="sd">most_big = 0</span>
<span class="sd">idx = 0</span>
<span class="sd">for i in np.arange(0.1, 0.4, 0.01):</span>
<span class="sd">    pred_ = pd.Series(pred).apply(lambda x: 1 if x &gt;= i else 0)</span>
<span class="sd">    loss = f1_score(y_v,pred_, pos_label=1.0)</span>
<span class="sd">    if most_big &lt; loss:</span>
<span class="sd">        most_big = loss</span>
<span class="sd">        idx = i</span>
<span class="sd">print(&quot;condition : {0}, f1: {1}&quot;.format(idx, most_big)) </span>
<span class="sd">pred = clf.predict(X_validation)</span>
<span class="sd">pred = pd.Series(pred).apply(lambda x: 1 if x &gt;= idx else 0)</span>
<span class="sd">print(&#39;accuracy&#39;, accuracy_score(y_v,pred) )</span>
<span class="sd">print(&#39;precision&#39;, precision_score(y_v,pred, pos_label=1.0) )</span>
<span class="sd">print(&#39;recall&#39;, recall_score(y_v,pred, pos_label=1.0) )</span>
<span class="sd">print(&#39;f1&#39;, f1_score(y_v,pred, pos_label=1.0) )</span>
<span class="sd">&#39;&#39;&#39;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[17]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&#39;\nfrom sklearn.metrics import mean_squared_error\nfrom sklearn.metrics.scorer import make_scorer\n\ndef custom_loss(y_true, y_pred):\n    most_big = 0\n    idx = 0\n    for i in np.arange(0.01, 0.7, 0.001):\n        pred = pd.Series(y_pred).apply(lambda x: 1 if x &gt;= i else 0)\n        loss = f1_score(y_true,pred, pos_label=1.0)\n        if most_big &lt; loss:\n            most_big = loss\n            idx = i\n    y_pred = pd.Series(y_pred).apply(lambda x: 1 if x &gt;= idx else 0)\n    return f1_score(y_true,y_pred, pos_label=1.0)\ndef rmsew_loss(y_true, y_pred):\n    value = mean_squared_error(y_true,y_pred,sample_weight = y_true)\n    if value &lt; 0 :\n        value = -value\n    return value\nscorer = make_scorer(custom_loss, greater_is_better=True)\n\n################### test\nfrom sklearn.model_selection import RandomizedSearchCV, KFold\nimport scipy as sp\nimport scipy.stats as stats\nfrom xgboost import XGBRegressor\nkfold = KFold(n_splits=10, shuffle=True, random_state=0)\nclf_xgb = XGBRegressor( n_jobs=4)\n               \nparam_dist = {\&#39;n_estimators\&#39;: stats.randint(150, 1500),\n              \&#39;objective\&#39;:[\&#39;reg:linear\&#39;,\&#39;reg:tweedie\&#39;,\&#39;reg:logistic\&#39;],\n              \&#39;learning_rate\&#39;: stats.uniform(0.001, 0.6),\n              \&#39;max_depth\&#39;: [3, 4, 5, 6, 7, 8, 9,10,11,12,13],\n              \&#39;gamma\&#39;: stats.uniform(0.01, 2.0),\n              \&#39;reg_lambda\&#39;: stats.uniform(0.1, 50),\n              \&#39;reg_alpha\&#39;: stats.uniform(0.1, 50),\n              \&#39;subsample\&#39;: [0.5,0.6,0.7,0.8,0.9],\n              \&#39;colsample_bytree\&#39;: [0.5,0.6,0.7,0.8,0.9],\n              \&#39;min_child_weight\&#39;: stats.randint(1, 12)\n             }\nclf = RandomizedSearchCV(clf_xgb, param_distributions = param_dist, n_iter = 50, scoring = scorer, cv=kfold, error_score = 0, verbose = 5, n_jobs = 4, random_state=42)\n\nclf.fit(X_validation, y_v)\n\nbest_score = clf.best_score_\nbest_params = clf.best_params_\nbest_estimator_ = clf.best_estimator_\nprint(&#34;Best score: {}&#34;.format(best_score))\nprint(&#34;Best params: {}&#34;.format(best_params))\nprint(&#34;Best estimator_: {}&#34;.format(best_estimator_))\n################### test\n\npred = clf.predict(X_validation)\nmost_big = 0\nidx = 0\nfor i in np.arange(0.1, 0.4, 0.01):\n    pred_ = pd.Series(pred).apply(lambda x: 1 if x &gt;= i else 0)\n    loss = f1_score(y_v,pred_, pos_label=1.0)\n    if most_big &lt; loss:\n        most_big = loss\n        idx = i\nprint(&#34;condition : {0}, f1: {1}&#34;.format(idx, most_big)) \npred = clf.predict(X_validation)\npred = pd.Series(pred).apply(lambda x: 1 if x &gt;= idx else 0)\nprint(\&#39;accuracy\&#39;, accuracy_score(y_v,pred) )\nprint(\&#39;precision\&#39;, precision_score(y_v,pred, pos_label=1.0) )\nprint(\&#39;recall\&#39;, recall_score(y_v,pred, pos_label=1.0) )\nprint(\&#39;f1\&#39;, f1_score(y_v,pred, pos_label=1.0) )\n&#39;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">Best score: 0.5550077639609884</span>
<span class="sd">Best params: {&#39;colsample_bytree&#39;: 0.8, &#39;gamma&#39;: 1.3651287236845648, &#39;learning_rate&#39;: 0.01095269735671369, &#39;max_depth&#39;: 5, &#39;min_child_weight&#39;: 3, &#39;n_estimators&#39;: 1321, &#39;objective&#39;: &#39;reg:logistic&#39;, &#39;reg_alpha&#39;: 8.818321450249572, &#39;reg_lambda&#39;: 34.646886905123296, &#39;subsample&#39;: 0.6}</span>
<span class="sd">Best estimator_: XGBRegressor(base_score=0.5, booster=&#39;gbtree&#39;, colsample_bylevel=1,</span>
<span class="sd">             colsample_bytree=0.8, gamma=1.3651287236845648,</span>
<span class="sd">             importance_type=&#39;gain&#39;, learning_rate=0.01095269735671369,</span>
<span class="sd">             max_delta_step=0, max_depth=5, min_child_weight=3, missing=None,</span>
<span class="sd">             n_estimators=1321, n_jobs=4, nthread=None,</span>
<span class="sd">             objective=&#39;reg:logistic&#39;, random_state=0,</span>
<span class="sd">             reg_alpha=8.818321450249572, reg_lambda=34.646886905123296,</span>
<span class="sd">             scale_pos_weight=1, seed=None, silent=True, subsample=0.6)</span>
<span class="sd">condition : 0.2799999999999999, f1: 0.5812307842467426</span>
<span class="sd">accuracy 0.8701756509372589</span>
<span class="sd">precision 0.5150492994291646</span>
<span class="sd">recall 0.6669279874566021</span>
<span class="sd">f1 0.5812307842467426</span>
<span class="sd">&#39;&#39;&#39;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[18]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&#34;\nBest score: 0.5550077639609884\nBest params: {&#39;colsample_bytree&#39;: 0.8, &#39;gamma&#39;: 1.3651287236845648, &#39;learning_rate&#39;: 0.01095269735671369, &#39;max_depth&#39;: 5, &#39;min_child_weight&#39;: 3, &#39;n_estimators&#39;: 1321, &#39;objective&#39;: &#39;reg:logistic&#39;, &#39;reg_alpha&#39;: 8.818321450249572, &#39;reg_lambda&#39;: 34.646886905123296, &#39;subsample&#39;: 0.6}\nBest estimator_: XGBRegressor(base_score=0.5, booster=&#39;gbtree&#39;, colsample_bylevel=1,\n             colsample_bytree=0.8, gamma=1.3651287236845648,\n             importance_type=&#39;gain&#39;, learning_rate=0.01095269735671369,\n             max_delta_step=0, max_depth=5, min_child_weight=3, missing=None,\n             n_estimators=1321, n_jobs=4, nthread=None,\n             objective=&#39;reg:logistic&#39;, random_state=0,\n             reg_alpha=8.818321450249572, reg_lambda=34.646886905123296,\n             scale_pos_weight=1, seed=None, silent=True, subsample=0.6)\ncondition : 0.2799999999999999, f1: 0.5812307842467426\naccuracy 0.8701756509372589\nprecision 0.5150492994291646\nrecall 0.6669279874566021\nf1 0.5812307842467426\n&#34;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Model-Select-&amp;-Traing">Model Select &amp; Traing<a class="anchor-link" href="#Model-Select-&amp;-Traing">&#182;</a></h1><p>RandomForest, SVC, Neural Net, XGB, LGM 등 여러 가지 모델에 대해 성능평가를 진행하였지만</p>
<p>XGBRegressor를 이용한 예측이 가장 높은 F1_score를 얻을 수 있었다.</p>
<p>목적은 Classification이지만, Threshould를 조절하기 위해 Regressor를 사용하고</p>
<p>일정 기준 이상이면 1, 미만이면 0으로 치환하였다.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[23]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">xgboost</span> <span class="k">import</span> <span class="n">XGBRegressor</span>

<span class="n">xgb_r</span> <span class="o">=</span> <span class="n">XGBRegressor</span><span class="p">(</span><span class="n">objective</span> <span class="o">=</span> <span class="s1">&#39;reg:logistic&#39;</span> <span class="p">,</span> 
                     <span class="n">colsample_bytree</span> <span class="o">=</span> <span class="mf">0.8</span><span class="p">,</span>
                     <span class="n">gamma</span><span class="o">=</span><span class="mf">1.3651287236845648</span><span class="p">,</span>
                     <span class="n">learning_rate</span><span class="o">=</span><span class="mf">0.01095269735671369</span><span class="p">,</span> 
                     <span class="n">max_depth</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span>
                     <span class="n">min_child_weight</span> <span class="o">=</span> <span class="mi">3</span><span class="p">,</span>
                     <span class="n">n_estimators</span><span class="o">=</span><span class="mi">1421</span><span class="p">,</span>
                     <span class="n">reg_alpha</span><span class="o">=</span> <span class="mf">26.01648261818684</span><span class="p">,</span>
                     <span class="n">reg_lambda</span><span class="o">=</span><span class="mf">43.96865359639777</span><span class="p">,</span>
                     <span class="n">subsample</span><span class="o">=</span><span class="mf">0.6</span><span class="p">,</span><span class="n">n_jobs</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span>
<span class="n">xgb_r</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_t</span><span class="p">)</span>
<span class="n">pred</span> <span class="o">=</span> <span class="n">xgb_r</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="n">most_big</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">idx</span> <span class="o">=</span> <span class="mi">0</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="mf">0.1</span><span class="p">,</span> <span class="mf">0.4</span><span class="p">,</span> <span class="mf">0.01</span><span class="p">):</span>
    <span class="n">pred_</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">pred</span><span class="p">)</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="mi">1</span> <span class="k">if</span> <span class="n">x</span> <span class="o">&gt;=</span> <span class="n">i</span> <span class="k">else</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">loss</span> <span class="o">=</span> <span class="n">f1_score</span><span class="p">(</span><span class="n">y_t</span><span class="p">,</span><span class="n">pred_</span><span class="p">,</span> <span class="n">pos_label</span><span class="o">=</span><span class="mf">1.0</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">most_big</span> <span class="o">&lt;</span> <span class="n">loss</span><span class="p">:</span>
        <span class="n">most_big</span> <span class="o">=</span> <span class="n">loss</span>
        <span class="n">idx</span> <span class="o">=</span> <span class="n">i</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;condition : </span><span class="si">{0}</span><span class="s2">, f1: </span><span class="si">{1}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">idx</span><span class="p">,</span> <span class="n">most_big</span><span class="p">))</span> 

<span class="n">pred</span> <span class="o">=</span> <span class="n">xgb_r</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="n">pred</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">pred</span><span class="p">)</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="mi">1</span> <span class="k">if</span> <span class="n">x</span> <span class="o">&gt;=</span> <span class="n">idx</span> <span class="k">else</span> <span class="mi">0</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;accuracy&#39;</span><span class="p">,</span> <span class="n">accuracy_score</span><span class="p">(</span><span class="n">y_t</span><span class="p">,</span><span class="n">pred</span><span class="p">)</span> <span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;precision&#39;</span><span class="p">,</span> <span class="n">precision_score</span><span class="p">(</span><span class="n">y_t</span><span class="p">,</span><span class="n">pred</span><span class="p">,</span> <span class="n">pos_label</span><span class="o">=</span><span class="mf">1.0</span><span class="p">)</span> <span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;recall&#39;</span><span class="p">,</span> <span class="n">recall_score</span><span class="p">(</span><span class="n">y_t</span><span class="p">,</span><span class="n">pred</span><span class="p">,</span> <span class="n">pos_label</span><span class="o">=</span><span class="mf">1.0</span><span class="p">)</span> <span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;f1&#39;</span><span class="p">,</span> <span class="n">f1_score</span><span class="p">(</span><span class="n">y_t</span><span class="p">,</span><span class="n">pred</span><span class="p">,</span> <span class="n">pos_label</span><span class="o">=</span><span class="mf">1.0</span><span class="p">)</span> <span class="p">)</span>

<span class="n">submission_value</span> <span class="o">=</span> <span class="n">xgb_r</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_submission</span><span class="p">)</span> 
<span class="n">submission_value</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">submission_value</span><span class="p">)</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="s1">&#39;Y&#39;</span> <span class="k">if</span> <span class="n">x</span> <span class="o">&gt;=</span> <span class="n">idx</span> <span class="k">else</span> <span class="s1">&#39;N&#39;</span><span class="p">)</span>
<span class="n">submission_value</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">submission_value</span><span class="p">)</span>
<span class="n">submission_value</span><span class="o">.</span><span class="n">to_csv</span><span class="p">(</span><span class="s1">&#39;submission.csv&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">submission_value</span><span class="o">.</span><span class="n">value_counts</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>condition : 0.29999999999999993, f1: 0.5696919748635006
accuracy 0.8736099974280225
precision 0.5274201239866476
recall 0.6193302721469369
f1 0.5696919748635006
N    2375
Y     582
dtype: int64
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Validation">Validation<a class="anchor-link" href="#Validation">&#182;</a></h1><p>KFold로 교차 검증을 진행하여 overfitting이 일어났는지 확인하였다</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;from sklearn.model_selection import cross_val_score, KFold</span>
<span class="sd">from sklearn.metrics.scorer import make_scorer</span>

<span class="sd">def custom_loss(y_true, y_pred):</span>
<span class="sd">    most_big = 0</span>
<span class="sd">    idx = 0</span>
<span class="sd">    for i in np.arange(0.01, 0.4, 0.01):</span>
<span class="sd">        pred = pd.Series(y_pred).apply(lambda x: 1 if x &gt;= i else 0)</span>
<span class="sd">        loss = f1_score(y_true,pred, pos_label=1.0)</span>
<span class="sd">        if most_big &lt; loss:</span>
<span class="sd">            most_big = loss</span>
<span class="sd">            idx = i</span>
<span class="sd">    y_pred = pd.Series(y_pred).apply(lambda x: 1 if x &gt;= idx else 0)</span>
<span class="sd">    return f1_score(y_true,y_pred, pos_label=1.0)</span>

<span class="sd">scorer = make_scorer(custom_loss, greater_is_better=True)</span>

<span class="sd">kfold = KFold(n_splits=10)</span>
<span class="sd">scores= cross_val_score(xgb_r,X_train, y_t, cv=kfold, scoring=scorer,n_jobs=4)</span>
<span class="sd">print(scores.mean())&#39;&#39;&#39;</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Threshould에 따라 F1_score가 어떻게 변화하는지 확인하는 작업</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[20]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">list_test</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">most_big</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">idx</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">pred</span> <span class="o">=</span> <span class="n">xgb_r</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="mf">0.01</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.001</span><span class="p">):</span>
    
    <span class="n">pred_</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">pred</span><span class="p">)</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="mi">1</span> <span class="k">if</span> <span class="n">x</span> <span class="o">&gt;=</span> <span class="n">i</span> <span class="k">else</span> <span class="mi">0</span><span class="p">)</span>
    <span class="n">loss</span> <span class="o">=</span> <span class="n">f1_score</span><span class="p">(</span><span class="n">y_t</span><span class="p">,</span><span class="n">pred_</span><span class="p">,</span> <span class="n">pos_label</span><span class="o">=</span><span class="mf">1.0</span><span class="p">)</span>
    <span class="n">list_test</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">loss</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">most_big</span> <span class="o">&lt;</span> <span class="n">loss</span><span class="p">:</span>
        <span class="n">most_big</span> <span class="o">=</span> <span class="n">loss</span>
        <span class="n">idx</span> <span class="o">=</span> <span class="n">i</span>
        
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;condition : </span><span class="si">{0}</span><span class="s2">, f1: </span><span class="si">{1}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">idx</span><span class="p">,</span> <span class="n">most_big</span><span class="p">))</span> 
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>condition : 0.29899999999999977, f1: 0.5699897225077082
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[21]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="mf">0.01</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.001</span><span class="p">),</span> <span class="n">list_test</span><span class="p">,</span> <span class="s1">&#39;ro&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[21]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>[&lt;matplotlib.lines.Line2D at 0x26d1305dd30&gt;]</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>각 변수에 대한 중요도를 측정하여 특정 변수를 특별하게 스케일링 하려 하였지만</p>
<p>변수 전체를 스케일링 하는 것이 더 높은 정확도를 보였다.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">feature_importance</span> <span class="o">=</span> <span class="n">xgb_r</span><span class="o">.</span><span class="n">feature_importances_</span>
<span class="n">Series_feat_imp</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">feature_importance</span><span class="p">,</span> <span class="n">index</span><span class="o">=</span><span class="n">X_columns</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">15</span><span class="p">,</span> <span class="mi">20</span><span class="p">))</span>
<span class="n">Series_feat_imp</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">barh</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Feature importance&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Feature&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA94AAARwCAYAAAAc3Iw7AAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4yLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvOIA7rQAAIABJREFUeJzs3XuYnXV97/33hyCQmJhskGKg4iClUEgwyMI0EEqk8OABqiCUClsJW0wtUlEvqunj3hRKbeOpFETA4NZQkZZNEHYMR6EJQoDACiRMAEWF+ECILWiZAAmhST7PH/c9slxZs2bNZM7zeV0X19zrd7q/9wr/fNfvcMs2EREREREREdE/dhjsACIiIiIiIiJGsiTeEREREREREf0oiXdEREREREREP0riHREREREREdGPknhHRERERERE9KMk3hERERERERH9KIl3RERERERERD9K4h0RERERERHRj5J4R0RERERERPSjJN4RERERERER/WjHwQ4ghpc3v/nNbmtrG+wwIiIiIiIiBsWKFStesL17T/ok8Y4eaWtro1qtDnYYERERERERg0LSL3raJ0vNIyIiIiIiIvrRkJzxltQGLLY9pa58KXCe7Wpd+WygYvucAQqxqa7iL+tmA3fYfq5J/2nAnrZv6a8Ye6t9bQdtc28e7DAiIiIiImKEWjPv/YMdQp/LjPd2kNSbHy5mA3t202Ya8L4+vGdEREREREQMkqGcxO0o6WrgEOBJ4KO1lZLOBP4aWFfWbyrLFwDrgQrwFuBzthdK2gG4DDgKeJriR4dv217Y6OaSzgdOAMYC9wF/btvlrPt9wBHAIknXAFcCby+7/gXwHDBG0lXA4cBa4APA+8u4vidpIzADmAJcAryxfIZjgb8FxkqaCfwD8AcUyXob8AJwWoN4ZwN/AowD9gVutP25su4K4LDyWRba/puyfA1wdfmcbwBOsf3jRt9HRERERERE9M5QnvHeH5hv+2CKRPrszgpJk4ELKZLfY4ED6/pOBmYCxwPzyrKTKBLXqcBZFElvM5fZPqxcLj62HKvTJNtH2f4acClwt+13AO8EHivb7Ad8w/ZBwIvAh8okvwqcbnsasAW4Dji37H8M8ApwPnCd7Wm2ryvHOxT4gO1tku4a04BTy2c8VdJby/Iv2K4ABwNHSTq4ps8Ltt8JXAGc12hQSXMkVSVVt2zoaPadRURERERERJ2hnHg/Y3tZeX0NRSLdaTqw1Pbztl+jSF5r3WR7q+3HgT3KspnA9WX5L4El3dz/3ZKWS2oHjgYOqqmrvd/RFEkrtrfY7sxMn7a9srxeQZH019sfWGf7obL/etubu4hnke2N3cR8l+0O268CjwNvK8v/VNLDwCPlc9T+UPH9bmLE9nzbFduVMeMmdhNCRERERERE1BrKS83dw8+1NtVcq+5vtyTtAlxOcWDbM5IuAHapafJKC8PUxrCFYtZ8m1vR/Dlq9eaeO0rah2Im+zDb/1kuxd+lQZ8tDO3/HyIiIiIiIoaloZxo7S1phu37gQ8D91LsRQZYDlwiaTeKZeinAKu6Ge9e4Ixy3/juwCzg2i7adiamL0gaD5wMNNwLDtxFsa/7nySNodir3cxLwITy+sfAnpIOs/2QpAnAxro22+tNFEl7h6Q9gPcCS3s72NS9JlIdgacMRkRERERE9JehvNT8CYpE+VFgV8rl3AC21wEXAPcDdwIPtzDeDcCzwGrgmxTJe8MNy7ZfBK4C2oGbgIeajHsuxbL0dorl2gc1aQuwALhS0kpgDMWe7K9LWgX8kCLpXwIcKGmlpFNbeLYu2V5FscT8MeDbwLLmPSIiIiIiIqIvyW51pfPwJ2m87ZfLmfIHgSPK/d7Rokql4mq12n3DiIiIiIiIEUjSivLw6pYN5aXm/WGxpEnATsBFSbojIiIiIiKiv42qxNv2rPoySTcC+9QVf9727QMSVA9JOg74Ul3x07ZPHIx4IiIiIiIiorlRlXg3MtwS1vIHgSH5o0BERERERERsaygfrhYREREREREx7I36GW8ASW3AYttT6sqXAufZrtaVz6Z4x/c5AxTikNG+toO2uTcPdhgREREREdtYk9fexhCVGe+IiIiIiIiIfpTE+3U7Srpa0qOSFkoaV1sp6UxJT0q6GziipnyBpEsl3SfpKUknl+U7SLpc0mOSFku6pbOuEUlrJL25vK6Us+1IOqp8n/dKSY9ImtBF/1mSlpax/1jS9ySprDtf0kOSVkuaX1O+VNKXJD1YPtuR2/cVRkRERERERL0k3q/bH5hv+2BgPXB2Z4WkycCFFAn3scCBdX0nAzOB44F5ZdlJQBswFTgLmNHLuM4DPml7GnAksLFJ20OAT5fxvZ3XfyC4zPZh5VL6sWWcnXa0/a6y3980GlTSHElVSdUtGzp6+RgRERERERGjUxLv1z1je1l5fQ1FIt1pOrDU9vO2XwOuq+t7k+2tth8H9ijLZgLXl+W/BJb0Mq5lwD9K+hQwyfbmJm0ftP2s7a3ASorEH+DdkpZLageOBg6q6fP98u+Kmva/xfZ82xXblTHjJvbyMSIiIiIiIkanJN6vcw8/19pUc626v63azOv/Hrv85qb2PIoZ87HAA5IOaDGOLRTL53cBLgdOtj0VuKp2/Jo+W8hhexEREREREX0uidbr9pY0w/b9wIeBe4ETyrrlwCWSdqNYhn4KsKqb8e4FzpB0NbA7MAu4tkn7NcChwK3AhzoLJe1rux1olzQDOAD4cQ+eqzPJfkHSeOBkYGEP+v+WqXtNpJrTIiMiIiIiIlqWGe/XPUGRKD8K7Apc0Vlhex1wAXA/cCfwcAvj3QA8C6wGvkmRvDfbIH0hRXJ/D8Xsc6dPl4eiraLY331rqw9Uxv4ixSx3O3AT8FBP+kdERERERMT2kd1sBXVsD0njbb9czpQ/CBxR7vcetiqViqvVavcNIyIiIiIiRiBJK2xXetInS83712JJk4CdgIuGe9IdERERERERPZfEux/ZnlVfJulGYJ+64s/bvr2VMSVNBb5bV7zJ9vReBRkRERERERH9Kon3ALN94nb2bwem9VE4ERERERER0c+SeEePtK/toG3uzYMdRkREU2vy9oWIiIgYQvrtVHNJbZJWNyhfKmmbjeiSZku6rL/i6UuSFkg6uRf9/kXSo5I+00V9m6TTtj/CiIiIiIiIGCoy4z1AJL0FONz225o0awNOo/n7viMiIiIiImIY6e/3eO8o6epylnehpHG1lZLOlPSkpLuBI2rKF0i6VNJ9kp7qnF2WtIOkyyU9JmmxpFuazTxLWiPpzeV1RdLS8vooSSvL/x6RNKHJGJ+T1C5plaR5DernSXq8fMavlmWndL57W9KPyqZ3AL9T3vNISb8n6c6yzcOS9gXmAUeWbT5TrgL4vqTbJP1U0pebfdmSXpb0xXLMByTtUZafIGl5+ax31pRfIOnb5SqEpyR9qtn4ERERERER0XP9nXjvD8y3fTCwHji7s0LSZOBCioT7WODAur6TgZnA8RQJKcBJFLPCU4GzgBm9jOs84JO2pwFHAhsbNZL0XuCDwHTb7wC+XFe/K3AicFD5jH9XVp0PHFf2+ZOy7E+An9ueZvse4HvAN8o2hwPrgLnAPWWbi8t+04BTy2c+VdJbmzzXG4EHyjF/BHy8LL8X+EPbhwD/Cnyups8BwHHAu4C/kfSGBt/DHElVSdUtGzqa3D4iIiIiIiLq9Xfi/YztZeX1NRSJdKfpwFLbz9t+Dbiuru9NtrfafhzYoyybCVxflv8SWNLLuJYB/1jO8E6yvbmLdscA37G9AcD2r+vq1wOvAt+SdBKwoWb8BZI+DoypH7ScYd/L9o3luK923qOBu2x32H4VeBxotlT9NWBxeb2C4kcKgN8FbpfUDvwVcFBNn5ttb7L9AvAfvP5d/4bt+bYrtitjxk1scvuIiIiIiIio19+Jt3v4udammmvV/W3VZl5/xl1+c1N7HsWM+VjgAUkHdNFfzWIsE/Z3ATdQzIzfVpZ/AvifwFuBlZJ2azBuq2q/hy0035f/X7bdoO3XgctsTwX+nJrvoofjR0RERERERA/1d5K1t6QZtu8HPkyx5PmEsm45cEmZlK4HTgFWdTPevcAZkq4Gdgdm0fwgsjXAocCtwIc6CyXtW74Pu13SDIrl1j9u0P8O4HxJ19reIGnX2llvSeOBcbZvkfQA8LOa8ZcDyyWdQJGAv9jZz/Z6Sc9K+qDtmyTtTDEz/hLQ5X7z7TARWFten7E9A03dayLVvKYnIiIiIiKiZf094/0ERaL8KLArcEVnhe11wAXA/cCdwMMtjHcD8CywGvgmRfLebNPxhRTJ/T0Us7mdPt15+BnF/u5bG3W2fRuwCKhKWkmxN7zWBGBx+Xx3A52vCftKeSDbaoq91o1+UPgI8Kmy733AW4BHgc3l4WgNXznWSxcA15ffwwt9OG5ERERERER0Q6+vTB4eJI23/XI5U/4gcES53zsGQKVScbVaHewwIiIiIiIiBoWkFbYrPekzHPfzLpY0CdgJuChJd0RERERERAxlwy7xtj2rvkzSjcA+dcWft317K2NKmgp8t654k+3pvQqyn0laDuxcV/yRct96REREREREDCHDLvFuxPaJ29m/neJ92cPCUP1BICIiIiIiIrY1IhLv0aRcZn+a7csltQGH2762rJsFnGf7+P66f/vaDtrm3txfw0dslzU5cT8iIiIihqD+PtU8+t4k4Ozyug04rS8Hl5QfYyIiIiIiIvpQkqzhZx6wb/l6s/8Cfr+8vhp4pFlHSe8C/gkYS/EatTNt/0TSbOD9wC7AG4Gj+y/8iIiIiIiI0SWJ9/AzF5hie1r90vLyczM/Bv7I9mZJxwB/D3yorJsBHGz71/WdJM0B5gCMedPuffIQERERERERo0US79FlInC1pP0AA2+oqftho6QbwPZ8YD7AzpP3G14vfo+IiIiIiBhk2eM9ulwELLE9BTiBYml5p1cGJ6SIiIiIiIiRLYn38PMSMKHBdSsmAmvL69l9GFNERERERER0IUvNhxnbv5K0TNJq4IfAZkmrgAV0c7ga8GWKpeafBf6tN/efutdEqnllU0RERERERMtkZ8tutK5SqbharQ52GBEREREREYNC0grblZ70yVLziIiIiIiIiH6UpeYjkKQzgXPripfZ/uRgxBMRERERETGaJfEegWx/B/jOYMcRERERERERWWoeERERERER0a8y4z2AJLUBi8v3aNeWLwXOs12tK58NVGyfM0Ahdqt9bQdtc28e7DBiCFqT0+4jIiIiIhrKjHdsQ1J+kImIiIiIiOgjSbwH3o6Srpb0qKSFksbVVko6U9KTku4GjqgpXyDpUkn3SXpK0sll+Q6SLpf0mKTFkm7prGtE0vmSHpK0WtJ8SSrLl0r6+/K+9QezRURERERERC8l8R54+wPzbR8MrAfO7qyQNBm4kCLhPhY4sK7vZGAmcDwwryw7CWgDpgJnATO6uf9ltg8rl7uPLcfqNMn2Uba/VttB0hxJVUnVLRs6Wn7QiIiIiIiISOI9GJ6xvay8voYike40HVhq+3nbrwHX1fW9yfZW248De5RlM4Hry/JfAku6uf+7JS2X1A4cDRxUU1d/PwBsz7ddsV0ZM25i908YERERERERv5G9vAPPPfxca1PNter+dkvSLsDlFAe2PSPpAmCXmiavtDpWREREREREtCaJ98DbW9IM2/cDHwbuBU4o65YDl0jajWIZ+inAqm7Guxc4Q9LVwO7ALODaLtp2JtkvSBoPnAws7EnwU/eaSDWnV0dERERERLQsS80H3hMUifKjwK7AFZ0VttcBFwD3A3cCD7cw3g3As8Bq4JsUyXvDjdi2XwSuAtqBm4CHevsQERERERER0RrZzVY2x3Agabztl8uZ8geBI8r93n2uUqm4Wq123zAiIiIiImIEkrTCdqUnfbLUfGRYLGkSsBNwUX8l3REREREREdFzSbxHANuz6ssk3QjsU1f8edu3D0hQERERERERASTxHrFsnzjYMUREREREREQOV4uIiIiIiIjoVyNmxltSG7DY9pS68qXAebardeWzKd5nfc4AhdhUV/GXdbOBO2w/16T/NGBP27f08J5PAD8pix6w/YlmfdrXdtA29+ZWbxHdWJNXs0VEREREjHgjJvEeLiTtaHtzD7vNpnhdWJeJNzANqADbJN7d3PPntqf1MJ6IiIiIiIho0UhLvHeUdDVwCPAk8NHaSklnAn8NrCvrN5XlC4D1FInrW4DP2V4oaQfgMuAo4GmKpfnftr2w0c0lnQ+cAIwF7gP+3LbLWff7gCOARZKuAa4E3l52/QuKpHqMpKuAw4G1wAeA95dxfU/SRmAGMAW4BHhj+QzHAn8LjJU0E/gH4A+APYE24AXgtB59kxEREREREdEnRtoe7/2B+bYPpkikz+6skDQZuJAi+T0WOLCu72RgJnA8MK8sO4kicZ0KnEWR9DZzme3DyuXiY8uxOk2yfZTtrwGXAnfbfgfwTuCxss1+wDdsHwS8CHyoTPKrwOnlzPQW4Drg3LL/McArwPnAdban2b6uHO9Q4AO2myXd+0h6RNLdko5s1EDSHElVSdUtGzq6+QoiIiIiIiKi1khLvJ+xvay8voYike40HVhq+3nbr1Ekr7Vusr3V9uPAHmXZTOD6svyXwJJu7v9uScsltQNHAwfV1NXe72jgCgDbW2x3ZrNP215ZXq+gSPrr7Q+ss/1Q2X99k2Xki2xvbBLvOmBv24cAnwWulfSm+ka259uu2K6MGTexyXARERERERFRb6Ql3u7h51qbaq5V97dbknYBLgdOtj0VuArYpabJKy0MUxvDFhpvBRDNn6NW03va3mT7V+X1CuDnwO+3OHZERERERES0YKTt8d5b0gzb9wMfBu6l2HMNsBy4RNJuFMvQTwFWdTPevcAZ5b7x3YFZwLVdtO1Msl+QNB44GWi4Fxy4i2Jf9z9JGkOxV7uZl4AJ5fWPgT0lHWb7IUkTgI11bVoiaXfg17a3SHo7xVL3p5r1mbrXRKo5iTsiIiIiIqJlI23G+wmKRPlRYFfK5dwAttcBFwD3A3cCD7cw3g3AsxQnin+TInlvuMnZ9osUs9ztwE3AQ03GPZdiWXo7xZLyg5q0BVgAXClpJTAGOBX4uqRVwA8pkv4lwIGSVko6tYVnA/gj4NFynIXAJ2z/usW+ERERERER0QLZra5aHp0kjbf9cjlT/iBwRLnfe1SqVCquVqvdN4yIiIiIiBiBJK2wXelJn5G21Lw/LJY0CdgJuGg0J90RERERERHRc0m8u2F7Vn2ZpBuBfeqKP2/79gEJqockHQd8qa74adsnDkY8ERERERERo0kS714Ybglr+YPAkPxRICIiIiIiYqQbaYerRURERERERAwpmfEeIOU+8dNsXy5pT+BS2yf30712Bv4ZOBT4FXCq7TUN2r0HuITipPRv2Z7X3djtaztom3tz3wY8AqzJK9YiIiIiIqILmfEeOJOAswFsP9dfSXfpY8B/2v494GK23d9N+f7wbwDvBQ4EPizpwH6MKSIiIiIiYlRK4j1w5gH7lu/Zvl7SagBJsyXdJOkHkp6WdI6kz0p6RNIDknYt2+0r6TZJKyTdI+mAJvf6AHB1eb0Q+GNJqmvzLuBntp+y/Rrwr2W/iIiIiIiI6ENJvAfOXODntqcBf1VXNwU4jSIZ/iKwwfYhwP3AR8s284G/tH0ocB5weZN77QU8A2B7M9AB7NZVm9KzZdk2JM2RVJVU3bKho+lDRkRERERExG/LHu+hYYntl4CXJHUAPyjL24GDJY0HDgeur5m43rnJePWz2wDuRZui0J5Pkfiz8+T9GraJiIiIiIiIxpJ4Dw2baq631nzeSvFvtAPwYjlb3opngbcCz0raEZgI/LqLNp1+F3iuh3FHREREREREN5J4D5yXgAm96Wh7fbn/+xTb15f7tQ+2vaqLLouAMyiWqp8M/Jvt+pnqh4D9JO0DrAX+jGK5e1NT95pINSd4R0REREREtCx7vAeI7V8By8pD1b7SiyFOBz4maRXwGM0PQvvfwG6SfgZ8lmJ/OZL2lHRLGc9m4BzgduAJ4P/YfqwXcUVEREREREQT2nYiNKJrlUrF1Wp1sMOIiIiIiIgYFJJW2K70pE9mvCMiIiIiIiL6UfZ4D2OSvgCcUld8ve0vDkY8ERERERERsa0k3sNYmWAnyY6IiIiIiBjCknhHj7Sv7aBt7s2DHUa/WpNT2yMiIiIiog8N2z3ekj4l6QlJ3+uDsdoknVbzebaky7ZjvCMlPSZppaSxXbRZIOnk8vrTksb1YPym8UmaJul9PY88IiIiIiIi+tqwTbyBs4H32T69s0BSb2fw22jhHdb1JI3poup04Ku2p9ne2MJQnwZaTrxbMA1I4h0RERERETEEDMvEW9KVwNuBRZI6JM2XdAfwz120v0XSweX1I5LOL68vknQWMA84spyh/kzZbU9Jt0n6qaQv14z1sqS/lbQcmNHgXmcBfwqc3zkbL+lzktolrZI0r679p4A9gSWSljR55jMlPSnpbuCImvJTJK0ux/6RpJ2AvwVOLZ/nVEkXSPq2pKWSnirv2dn/o5IeLft/t6v7R0RERERERO8Myz3etj8h6T3Au4FzgBOAmU1ml39EkVivATbzeuI6E7gG+Blwnu3joVjKTTFrfAiwCfiJpK/bfgZ4I7Da9vldxPYtSTOBxbYXSnov8EFguu0Nknata3+ppM8C77b9QqMxJU0GLgQOBTqAJcAjZfX5wHG210qaZPu18oeFiu1zyv4XAAeU39eE8nmuAH4f+AJwhO0X6mOruf8cYA7AmDft3qhJREREREREdGFYzng3sKibJd33AH9EkWjfDIwv91S32f5JF33ust1h+1XgceBtZfkW4IYexHYM8B3bGwBs/7oHfTtNB5baft72a8B1NXXLgAWSPg50tfQd4Gbbm8rk/j+APYCjgYWdCX9Xsdmeb7tiuzJm3MRehB8RERERETF6DcsZ7wZe6ab+IaACPAX8EHgz8HFgRZM+m2qut/D6d/Wq7S09iE2Ae9C+Kw3HKGf/pwPvB1ZKmtZF/0bP01exRURERERERBdGSuLdVLn8+hmKvdcXAbsDXy3/A3iJYgl2f7iDYr/3tZ1LzRvMLHfev+FSc2A5cImk3YD1wCnAKgBJ+9peDiyXdALwVlp/nruAGyVdbPtXXcT2W6buNZFqXrcVERERERHRspGy1LwV9wD/Xi75vgf43fIvwKPA5vKAsc90NUBv2L4NWARUJa0EzmvQbD5wa1eHq9leB1wA3A/cCTxcU/2V8uC21RR72VdR7AE/sPNwtSaxPQZ8Ebhb0irgH3v6fBEREREREdGc7Kw0jtZVKhVXq9XBDiMiIiIiImJQSFphu9KTPqNpxjsiIiIiIiJiwI2oPd6SjgO+VFf8tO0T++l+NwL71BV/3vbt2zHmcmDnuuKP2G7v7ZgRERERERExeEZU4l0mvL1Oentxvz5P6G1Pb1YvqY3iHeFTtvde5fu9X7b91fLd5XfYfm57x42IiIiIiIjXjajEO7bLbGA10DTxbl/bQdvcmwckoP62JqezR0RERETEAMge7+FpjKSrJD0m6Q5JYyUtlXSxpB9JekLSYZK+L+mnkv6us6OkL0j6iaQ7gf3LspMp3nP+vfIk9LGD9FwREREREREjThLv4Wk/4Bu2DwJeBD5Ulr9m+4+AK4H/C3wSmALMlrSbpEOBPwMOAU4CDgOwvRCoAqfbnmZ744A+TURERERExAiWpebD09O2V5bXK4C28npR+bcdeKx8/zeSngLeChwJ3Fi+yxxJi2iBpDnAHIAxb9q9L+KPiIiIiIgYNTLjPTxtqrnewus/oHSWb61rs7WmTY9f3G57vu2K7cqYcRN72j0iIiIiImJUS+I9uvwIOLHcEz4BOKGm7iVgwuCEFRERERERMXJlqfkoYvthSdcBK4FfAPfUVC8ArpS0EZiRfd4RERERERF9Q3aPVx7HKFapVFytVgc7jIiIiIiIiEEhaYXtSk/6ZKl5RERERERERD9K4h0RERERERHRj5J4R0RERERERPSjJN4RERERERER/SiJd0REREREREQ/yuvEeklSG7DY9pS68qXAebardeWzgYrtcwYoxJZIug34Q+Be28d31759bQdtc2/u/8D62Jp57x/sECIiIiIiYpTKjHd8BfjIYAcRERERERExUiXx3j47Srpa0qOSFkoaV1sp6UxJT0q6GziipnyBpEsl3SfpKUknl+U7SLpc0mOSFku6pbOuEUlrJL25vK6Us+1IOkrSyvK/RyRN6GoM23cBL23XtxARERERERFdSuK9ffYH5ts+GFgPnN1ZIWkycCFFwn0scGBd38nATOB4YF5ZdhLQBkwFzgJm9DKu84BP2p4GHAls7OU4AEiaI6kqqbplQ8f2DBURERERETHqJPHePs/YXlZeX0ORSHeaDiy1/bzt14Dr6vreZHur7ceBPcqymcD1ZfkvgSW9jGsZ8I+SPgVMsr25l+MAYHu+7YrtyphxE7dnqIiIiIiIiFEniff2cQ8/19pUc626v63azOv/hrv85qb2PIoZ87HAA5IO6OG4ERERERER0Udyqvn22VvSDNv3Ax8G7gVOKOuWA5dI2o1iGfopwKpuxrsXOEPS1cDuwCzg2ibt1wCHArcCH+oslLSv7XagXdIM4ADgxz17tMam7jWRak4Ij4iIiIiIaFlmvLfPExSJ8qPArsAVnRW21wEXAPcDdwIPtzDeDcCzwGrgmxTJe7NN1RdSJPf3AFtqyj8tabWkVRT7u2/taoCy7/XAH0t6VtJxLcQZERERERERLZLdbDV0DDRJ422/XM6UPwgcUe73HhIqlYqr1Wr3DSMiIiIiIkYgSStsV3rSJ0vNh57FkiYBOwEXDaWkOyIiIiIiInouifcQY3tWfZmkG4F96oo/b/v2VsaUNBX4bl3xJtvTexVkREREREREtCyJ9zBg+8Tt7N8OTOujcCIiIiIiIqIHcrhaRERERERERD8aMTPektqAxban1JUvBc6zXa0rnw1UbJ8zQCE21VX8Zd1s4A7bzzXpPw3Y0/Ytvbj33sDjwAW2v9qsbfvaDto0ffgfAAAgAElEQVTm3tzTWwy4NXnlWUREREREDBGZ8R5gknrzY8dsYM9u2kwD3tfLe15Mk1eORURERERERO+NmBnv0o6SrgYOAZ4EPlpbKelM4K+BdWX9prJ8AbAeqABvAT5ne6GkHYDLgKOApyl+qPi27YWNbi7pfOAEYCxwH/Dntl3Out8HHAEsknQNcCXw9rLrXwDPAWMkXQUcDqwFPgC8v4zre5I2AjOAKcAlwBvLZzgW+FtgrKSZwD8Af0CRrLcBLwCndRHzB4GngFe6/FYjIiIiIiKi10bajPf+wHzbB1Mk0md3VkiaDFxIkfweCxxY13cyMBM4HphXlp1EkbhOBc6iSHqbucz2YeVy8bHlWJ0m2T7K9teAS4G7bb8DeCfwWNlmP+Abtg8CXgQ+VCb5VeB029OALcB1wLll/2MokubzgetsT7N9XTneocAHbHeVdL8R+Hz5vXRJ0hxJVUnVLRs6uvkKIiIiIiIiotZIS7yfsb2svL6GIpHuNB1Yavt5269RJK+1brK91fbjwB5l2Uzg+rL8l8CSbu7/bknLJbUDRwMH1dTV3u9o4AoA21tsd2azT9teWV6voEj66+0PrLP9UNl/ve3NXcSzyPbGJvFeCFxs++VmD2V7vu2K7cqYcRObNY2IiIiIiIg6I22puXv4udammmvV/e2WpF2AyykObHtG0gXALjVNWlnKXRvDFopZ821uRfPnqNXdPacDJ0v6MjAJ2CrpVduXtTh+REREREREdGOkJd57S5ph+37gw8C9FHuuAZYDl0jajWIZ+inAqm7Guxc4o9w3vjswC7i2i7adSfYLksYDJwMN94IDd1Hs6/4nSWMo9mo38xIwobz+MbCnpMNsPyRpArCxrk1LbB/ZeV3+UPByd0n31L0mUs2J4RERERERES0baUvNn6BIlB8FdqVczg1gex1wAXA/cCfwcAvj3QA8C6wGvkmRvDfc5Gz7ReAqoB24CXioybjnUixLb6dYUn5Qk7YAC4ArJa0ExgCnAl+XtAr4IUXSvwQ4UNJKSae28GwRERERERExAGS3ump5dJI03vbL5Uz5g8AR5X7vUalSqbharXbfMCIiIiIiYgSStMJ2pSd9RtpS8/6wWNIkYCfgotGcdEdERERERETPJfHuhu1Z9WWSbgT2qSv+vO3bBySoHpJ0HPCluuKnbZ84GPFERERERESMJkm8e2G4JazlDwJD8keBiIiIiIiIkS6Jd/RI+9oO2ubePNhhbGNNTlqPiIiIiIghaqSdaj4kSPqUpCckfW+wY2mFpFmSDh/sOCIiIiIiIkaizHj3j7OB99p+urNA0o62Nw9iTM3MAl4G7hvkOCIiIiIiIkacJN59TNKVwNuBRZL2Bq4D2oAXgNMatJ8NfJDi/dxTgK9RnKD+EWAT8D7bv5a0lOI94u8GJgEfs31PFzGMoThM7TjAwFW2vy5pDXA1cALwBuAU4FXgE8AWSf8d+Muuxo2IiIiIiIieS+Ldx2x/QtJ7KBLkcyiS3Jm2NzbpNgU4BNgF+BnFCemHSLoY+CjwT2W7HW2/S9L7gL8BjulivDkUp64fYnuzpF1r6l6w/U5JZwPn2T6r/LHgZdtfbTSYpDnlmIx50+7dfgcRERERERHxuuzx7n+Lukm6AZbYfsn280AH8IOyvJ1itrzT98u/K+rK6x0DXNm5tN32r3sxxm/Ynm+7YrsyZtzEVrpEREREREREKYl3/3ulhTabaq631nzeym+vSugs30Lz1QqiWGLe7F7djRERERERERF9IInXyHQH8AlJSzuXmtfNetd7CXhTKwNP3Wsi1by6KyIiIiIiomWZ8R6ZvgX8f8CjklbR4FC3Oj8ATpS0UtKR/R5dRERERETEKCK7qxXJEduqVCquVquDHUZERERERMSgkLTCdqUnfTLjHREREREREdGPssd7gEg6juLd2rWetn3iUBozIiIiIiIi+lYS7wFi+3bg9qE+ZkRERERERPStJN7bQdIk4DTbl0tqAw63fW1ZNws4z/bxAxjPy7bHN6n/CvA+4BaK15y9bPurPblH+9oO2ubevH2B9qE1OWE9IiIiIiKGuOzx3j6TgLPL6za6Pz28R1Toy3+jPwfeafuvmtwzP8ZERERERET0oSRZ22cesK+klcB/Ab9fXl8NPNKso6TdgWuB3YCHgPcAhwLjgVuBJcAM4IOSHgMuAY4HNgIfsP3vkvYpx9gRuK2b+y0C3ggsl/QPdXVLgfuAI4BFwNdafP6IiIiIiIjoRma8t89c4Oe2pwF/Bdxje5rti1vo+zfAv9l+J3AjsHdN3f7AP9s+xPYvKBLmB2y/A/gR8PGy3SXAFbYPA37Z7Ga2/wTYWMZ3XYMmk2wfZXubpFvSHElVSdUtGzpaeLSIiIiIiIjolMR78MwE/hXA9m3Af9bU/cL2AzWfXwMWl9crKJa1QzFD/S/l9Xe3M55GyThlfPNtV2xXxoybuJ23iYiIiIiIGF2SeA8eNal7pe7zf9l2eb2F394iYPpG/T0jIiIiIiKiDyTx3j4vARMaXLfiXuBPAST9P8B/68X9lwF/Vl6f3ov+ERERERER0c9yuNp2sP0rScskrQZ+CGyWtApYQDeHqwEXAv8i6VTgbmAdRfLe5evAGjgXuFbSucANPY2/N6buNZFqXuEVERERERHRMr2+gjkGkqSdgS22N0uaQXFI2rTBjqs7lUrF1Wp1sMOIiIiIiIgYFJJW2K70pE9mvAfP3sD/Kd/T/Rqvn1QeERERERERI0gS734m6UyKJeG1ltn+JHBIP9xvKtuecL7J9vS+vldERERERER0L4l3P7P9HeA7A3i/dmDIL1mPiIiIiIgYLXKqeUREREREREQ/yox3FyS1AYttTxnkUIaU9rUdtM29eVBjWJNT1SMiIiIiYhgZFTPeKgz4s0oaM9D3jIiIiIiIiKFlxCbektokPSHpcuBh4H9JelLSUklXSbqsbLdA0qWS7pP0lKSTezD+PZIeLv87vCyfJWmJpGuB9m5iu0rSY5LukDS2rFsq6WJJPyrbHCbp+5J+KunvWnjeRmN+XNJDklZJukHSuO159oiIiIiIiGjdiE28S/sD/wy8HzgT+EPgWOCAunaTgZnA8cC8Fsf+D+BY2+8ETgUural7F/AF2wc26b8f8A3bBwEvAh+qqXvN9h8BVwL/F/gkMAWYLWm3Xoz5fduH2X4H8ATwsZo+3T67pDmSqpKqWzZ0NLl9RERERERE1BvpifcvbD9AkQjfbfvXtv8LuL6u3U22t9p+HNijxbHfAFwlqb0crzbJftD20930f9r2yvJ6BdBWU7eo/NsOPGZ7ne1NwFPAW3sx5pRydr4dOB04qKZPt89ue77tiu3KmHETu3msiIiIiIiIqDXSD1d7pfyrbtptqrnurm2nzwD/DryD4geMVxvct9V7bgHGNqjbWtduK83/zboacwHwQdurJM0GZnXRp9Vnj4iIiIiIiBaN9MS704PAxZL+G/ASxRLshvuve2Ai8KztrZLOAIbyQWoTgHWS3kAx4722twNN3Wsi1ZwqHhERERER0bJRkXjbXivp74HlwHPA48D2bla+HLhB0inAElqb5R4s/4vi2X9B8YPDhMENJyIiIiIiYvSQ7cGOYUBIGm/7ZUk7AjcC37Z942DHNdxUKhVXq9XBDiMiIiIiImJQSFphu9KTPiP9cLVaF0haCawGngZuGuR4IiIiIiIiYhQYFUvNAWyf15t+ko4DvlRX/LTtE1vouxtwV4OqP7b9q17G0+djRkRERERERP8ZNYl3b9m+Hbi9l31/BUzr43j6fMyIiIiIiIjoP6NpqXlERERERETEgMuM9wCRNAk4zfblkvYELrV9cj/d67PAWcBm4Hngf9j+RYN2h1K843sscAtwrrs5ba99bQdtc2/u85hbtSavMouIiIiIiGEmM94DZxJwNoDt5/or6S49AlRsHwwsBL7cRbsrgDnAfuV/7+nHmCIiIiIiIkalJN4DZx6wr6SVkq6XtBpA0mxJN0n6gaSnJZ0j6bOSHpH0gKRdy3b7SrpN0gpJ90g6oKsb2V5ie0P58QHgd+vbSJoMvMn2/eUs9z8DH+zrh46IiIiIiBjtkngPnLnAz21PA/6qrm4KcBrwLuCLwAbbhwD3Ax8t28wH/tL2ocB5wOUt3vdjwK0NyvcCnq35/GxZtg1JcyRVJVW3bOho8bYREREREREB2eM9VCyx/RLwkqQO4AdleTtwsKTxwOHA9ZI6++zc3aCS/jtQAY5qVN2grOH+btvzKRJ/dp68X9M94BEREREREfHbkngPDZtqrrfWfN5K8W+0A/BiOVveEknHAF8AjrK9qUGTZ/ntJei/CzzXk6AjIiIiIiKie0m8B85LwITedLS9vtz/fYrt61VMex9se1Wj9pIOAb4JvMf2f3Qx5jpJL0n6Q2A5xZL2r3cXy9S9JlLNyeIREREREREtyx7vAWL7V8Cy8lC1r/RiiNOBj0laBTwGfKBJ268A4ymWpq+UtKizQtLKmnZ/AXwL+BnwcxrvBY+IiIiIiIjtoG5e2xzxWyqViqvV6mCHERERERERMSgkrbBd6UmfzHhHRERERERE9KPs8R7GJH0BOKWu+HrbXxyMeCIiIiIiImJbSbyHsTLBTpIdERERERExhGWpeUREREREREQ/GlIz3pLagMW2p9SVLwXOs12tK58NVGyfM0Ah9pqkBRTPtrCH/f4FOAj4ju2LG9S3AYfbvraXcd0GTKb4f+Ee4JO2t3TVvn1tB21zb+7NrbbbmrzGLCIiIiIihqHMeA9hkt5CkVQf3CjpLrUBp23Hbf7U9juAKcDubLtnPCIiIiIiIrbDUEy8d5R0taRHJS2UNK62UtKZkp6UdDdwRE35AkmXSrpP0lOSTi7Ld5B0uaTHJC2WdEtnXSOS1kh6c3ldKWfbkXRU+U7slZIekTShyRifk9QuaZWkeQ3q50l6vHzGr5Zlp0haXfb5Udn0DuB3ynseKen3JN1ZtnlY0r7APODIss1nJM2W9H1Jt0n6qaQvN/uyba/v/N6BnYC8Xy4iIiIiIqIPDaml5qX9gY/ZXibp28DZnRWSJgMXAocCHcAS4JGavpOBmcABwCJgIXASxazwVOB3gCeAb/cirvMolmEvkzQeeLVRI0nvBT4ITLe9QdKudfW7AicCB9i2pEll1fnAcbbX1pT9CcXy9Gll3+XAPNs3StqF4oeTuRTL8I8v28wGpgGHAJuAn0j6uu1nunowSbcD7wJupfjO6uvnAHMAxrxp96ZfUkRERERERPy2oTjj/YztZeX1NRSJdKfpwFLbz9t+Dbiuru9NtrfafhzYoyybSfGKra22f0mRrPfGMuAfJX0KmGR7cxftjqHYj70BwPav6+rXUyTt35J0ErChZvwFkj4OjKkftJxh38v2jeW4r3beo4G7bHfYfhV4HHhbswezfRzFjxY7A0c3qJ9vu2K7MmbcxGZDRURERERERJ2hmHjXL3Xu7nOtTTXXqvvbqs28/r3s8pub2vOAs4CxwAOSDuiiv5rFWCbs7wJuoJgZv60s/wTwP4G3Aisl7dZg3FbVfg9baGFlQ5mkLwI+0IP7RERERERERDeG4lLzvSXNsH0/8GHgXuCEsm45cEmZlK6nOAhsVTfj3QucIelqisPDZgHNTgBfQ7GU/VbgQ52Fkva13Q60S5pBsZz9xw363wGcL+nazqXmtbPe5TL1cbZvkfQA8LOa8ZcDyyWdQJGAv9jZz/Z6Sc9K+qDtmyTtTDEz/hLQ5X7zZspYJtheJ2lH4H0UJ5t3aepeE6nmdPGIiIiIiIiWDcUZ7ycoEuVHgV2BKzorbK8DLgDuB+4EHm5hvBuAZ4HVwDcpkveOJu0vpEju76GYLe706c7Dz4CNFIn5NmzfRjFzXJW0kmJveK0JwOLy+e4GPlOWf6U8kG018CMa/6DwEeBTZd/7gLcAjwKbywPXPtOgTzNvBBaV460C/gO4sodjRERERERERBOyR/4h1pLG2365nCl/EDii3O8dPVSpVFytVrtvGBERERERMQJJWmG70pM+Q3GpeX9YXJ4UvhNwUZLuiIiIiIiIGCijIvG2Pau+TNKNwD51xZ+3fXsrY0qaCny3rniT7em9CrKfla8i27mu+CPlvvWIiIiIiIjoJ6Mi8W7E9onb2b+d4n3Zw8JQ/UEgIiIiIiJipBu1iXf0TvvaDtrm3jzg912Tk9QjIiIiImKYGoqnmg97ktrK08nry5dK2mYTvqTZki4bmOgak/T/Dub9IyIiIiIiRqok3tEpiXdEREREREQ/SOLdf3aUdLWkRyUtlDSutlLSmZKelHQ3cERN+QJJl0q6T9JTkk4uy3eQdLmkxyQtlnRLZ10jkg4rx1gl6UFJE8qZ9e9Luk3STyV9uWw7DxgraaWk7/XP1xERERERETE6JfHuP/sD820fDKwHzu6skDQZuJAi4T4WOLCu72RgJnA8MK8sOwloA6YCZwEzurqxpJ2A64Bzbb8DOAbYWFZPA04txzlV0lttzwU22p5m+/QG482RVJVU3bKho/VvICIiIiIiIpJ496NnbC8rr6+hSKQ7TQeW2n7e9msUSXKtm2xvtf04sEdZNhO4viz/JbCkyb33B9bZfgjA9nrbm8u6u2x32H4VeBx4W3cPYnu+7YrtyphxE7trHhERERERETWSePcf9/BzrU0116r72wo1Gb927C3kZPuIiIiIiIh+laSr/+wtaYb9/7N37+F2VeXZ/7+3ASEcDIoWAVs3IgWBQJAFlKOIUE+ggPBS5VXCVUVBKvW9ouCJgkiFn7YKRcFAMVpipWBDIaGCIoESIGEFQjYnQUn8SaAq+hIOwQDJ/f4xxy6Lxd7rsA/Zyd7357py7bnGHOOZz5r561ljzDF9G/BB4BbgsHJuPnCepM2plqEfDdzdJt4twHGSvge8DjgQ+MEAfR8AtpK0h+07JG3Ki0vNB/K8pPVtP9+q0+StJ1HPq70iIiIiIiI6lhnvkXM/VaG8GHgNcGHfCduPAWcAtwE/Be7sIN6PgEeAe4DvUBXv/T5wXZavHwP8k6S7gZ8AG7aJPx1YnM3VIiIiIiIihpfsViueY20iaRPbT5eZ8gXAvuV57zWmVqu5Xq+vyUtGRERERESsNSQttF3rZkyWmq9bZkvaDHglcNaaLrojIiIiIiKieym81yG2D2xukzQL2Kap+VTb162RpCIiIiIiIqKlFN7rONtHjHYOERERERERMbB1svCW9LTtTbrofyAwzfahI5dVv9c9HHiwvI8bSVOB620/uibzaEfSHsDtwDG2r2zVt3fZcnpOm7NmEiuWZhf1iIiIiIhYh2VX85F1OLBjw+epwFajk0r/JE0AzgWyND0iIiIiImIErNOFt6QDJc2VdKWkByTNlKRy7l2l7RbgyDZxzpA0reHzPZJ6JG0saY6ku0vbMS1inCPpPkmLJX1d0j7A+4CvSVok6VSgBswsnydKWirpTEl3SuqVtEObHC8t3/dhSZ8q7T3le15Scpwp6WBJ8yQ9JGnPNrfxb6heVfbbNv0iIiIiIiJiENbJpeZNdgN2Ah4F5gH7SqoDFwMHAb8ALh9k7HcBj9p+L4CkSf11kvQa4AhgB9uWtJntJyRdDczuW74t6d1US97r5TPA47bfKukkYBrw0Rb57AC8HdgU+LmkvneDvxk4GjgBuAP4ELAfVeH/eaqZ9/7y3rrkfRCwx0AXlXRCic2EV72uRXoRERERERHRbJ2e8S4W2H7E9mpgEdBDVaAusf2QqxeVXzbI2L3AwZLOlbS/7eUD9HsS+CNwiaQjgRVdXOPfy9+FVLm3Msf2StuPU81Qb1Hal9juLffgXuCG8r1728T8JtUO6KtaXdT2dNs127UJG/X720NEREREREQMYCwU3isbjlfx4iy+u4jxAi+9FxsC2H4Q2J2qgP2qpNP7G2z7BWBPqiXbhwM/7uLaffk35t6ub3P/xvbVDZ9Xt4lZA34oaSlwFPDtsiFcREREREREDJOxsNS8Pw8A20ja1vYvgQ+26b8UOBRA0lsp78WWtBXwB9uXSXqaanO0l5G0CbCR7Wsl3U61vB3gKapl4QzweVTZ/p/3f0uaQbUs/qrRyygiIiIiImLsGZOFt+0/lueS50h6HLgF2LnFkB8BH5G0iOoZ6QdL+2SqzdFWA88DJw4wflPgPyRtCAj4dGn/IXBx2QjtKGAGcJGkZ4G9B/v9RtPkrSdRz+u9IiIiIiIiOqbqUeCIztRqNdfr9dFOIyIiIiIiYlRIWmi71s2YsfCMd0RERERERMRaa0wuNR+IpOOBU5qa59n+ZBcxZlGeAW9wqu3rhppfiT/kHNdEzIiIiIiIiOhMlppHV7LUPCIiIiIixrMsNY+IiIiIiIhYy4yrpeYjSdJUoGb75PIu7Adt3zfKabUk6e+BCbZPLZ/fCNwIvNX2E/2N6V22nJ7T5qyR/JZm9/SIiIiIiBgDMuM9Mg4HdhztJDpwFvB+SW8pn88DvjRQ0R0RERERERHdS+HdAUk9kh6QdImkeyTNlHSwpHmSHpK0Z0PffYD3Ub3/e5GkbQeIOVdSrRy/VtLScryTpAVl7GJJ2w0w/ixJpzR8PlvSpyQdWGJfWXKeKUn9xbD9LPB/gG9Lejewqe2Zg7tLERERERER0Z8U3p17M9WM8C7ADsCHgP2AacDn+zrZvhW4GviM7Sm2f9nldT4BnGd7ClADHhmg3z8DxwFIegXwV0Bf0bwb8LdUs+5vAvYd6GK2rwX+AHwfOKm/PpJOkFSXVF+1YnmXXyciIiIiImJ8yzPenVtiuxdA0r3ADbYtqRfoGcbr3AZ8QdIbgH+3/VB/nWwvlfR7SbsBWwB32f59mdxeYPuRkuuikt8tLa75LWCi7Z8PcK3pwHSADbbcLtvgR0REREREdCEz3p1b2XC8uuHzagb3A8YLvHj/N+xrtP0DqqXqzwLXSTqoRYxLgKnA8cClA+S6qoP8Vpd/ERERERERMcwy4z0yngI2bdNnKbA7sAA4qq9R0puAh22fX453AX42QIxZwJeB9amWvo+4yVtPop7dxiMiIiIiIjqWGe+R8UPgM5LuGmhzNeDrwImSbgVe29B+DHBPWSK+A9Wz1/2y/RzV67/+zfaq4Uk9IiIiIiIihpPsPLK7riqbqt0JHD3Qs+DDrVaruV6vr4lLRURERERErHUkLbRd62ZMZrzXUZJ2BH5BtcnbGim6IyIiIiIiont5xnuESfoWL3+d13m2v9vh+M2BG/o59Q7bb+oij1nANk3Np9q+rtMYERERERER0b0U3iPM9ieHOP73wJRhyOOIocaIiIiIiIiI7mWpeURERERERMQIyox3PyRNBa63/Wj5vBSo2X58NPNqJOlp25u0OP95238/3NftXbacntPmDHfYl1ia15VFRERERMQYkhnv/k0FthrtJIbo86OdQERERERERIzBwltSj6T7JV0s6V5J10uaKGmKpNslLZY0S9KrBxh/FFADZkpaJGliOfUZSQvKvzeXvluUWHeXf/sMEPMTJdYiSUsk3Vjan5Z0dhl7u6QtWnyvbSTdJukOSWc1tG8p6eYS+x5J+0s6B5hY2mYOdE/K+DdL+mnJ4c4W7x2PiIiIiIiIQRhzhXexHfAt2zsBTwAfAL5PtYv3LkAv8Hf9DbR9JVAHjrU9xfaz5dSTtvcELgC+WdrOB26yvSvwVuDeAWJeZHsKsAfwCPCP5dTGwO1l/M3Ax1p8p/OAC23vAfx3Q/uHgOtK/F2BRbZPA54t+R/b4p4AzCztuwL7AI81X1jSCZLqkuqrVixvkWJEREREREQ0G6uF9xLbi8rxQmBbYDPbN5W27wEHdBnzXxv+7l2ODwIuBLC9yna7qvQ84Ge2rymfnwNmN+TZ02Lsvg05/EtD+x3A8ZLOACbbfmqA8c33pEfSpsDWtmeV7/BH2yuaB9qebrtmuzZho0ktv2BERERERES81FgtvFc2HK8CNhuGmB7guCNlw7Y3Amc2ND9vuy/WKtpvdvey69q+mepHhGXAv0j6yABjm+/JeoDaZx4RERERERFDMV52NV8O/F9J+9v+L+DDwE0t+j8FbNrUdgxwTvl7W2m7ATgR+KakCcDGtp9sDiZpd2AasL/t1YP8DvOAvwIuA/qWjyPpjcAy2xdL2phqyfv3geclrW/7+YEC2n5S0iOSDrd9laQNgAn9zXr3mbz1JOrZdTwiIiIiIqJjY3XGuz/HAV+TtBiYAny5Rd8ZwEVNm6ttIGk+cArw6dJ2CvB2Sb1Uy7d3GiDeycBrgBtLzEsGkf8pwCcl3QE0rvc+EFgk6S6q57bPK+3TgcWSZraJ+2HgU+W+3Aq8fhC5RURERERExAD04krniPZqtZrr9fpopxERERERETEqJC20XetmzHia8Y6IiIiIiIhY48bLM979kvQtqt3CG51n+7uDjLc51XPfzd5h+/cdxvgCcHRT8xW2zx5MThERERERETG6stQ8upKl5hERERERMZ5lqXlERERERETEWmZcLzUfCkk9wGzbOze1zwWm2a43tU8FarZPXkMpdkzSq4D7gVnt8utdtpye0+aMaD5L87qyiIiIiIgYQzLjHQBn0fq95hERERERETFIKbyHZj1J35O0WNKVkjZqPCnpeEkPSrqJhk3cJM2QdL6kWyU9LOmo0v4KSd+WdK+k2ZKu7TvXH0lLJb22HNfKbDuS3lbeF75I0l2SNm0RY3dgC+D6odyIiIiIiIiI6F8K76HZHphuexfgSeCkvhOStgTOpCq4DwF2bBq7JbAfcChwTmk7EugBJgMfBfYeZF7TgE/angLsDzzbXydJrwD+AfhMq2CSTpBUl1RftWL5IFOKiIiIiIgYn1J4D82vbc8rx5dRFdJ99gLm2v6d7eeAy5vGXmV7te37qGacKeOvKO3/Ddw4yLzmAf8o6VPAZrZfGKDfScC1tnpLeZIAACAASURBVH/dKpjt6bZrtmsTNpo0yJQiIiIiIiLGp2yuNjTN72Jr97nRyoZjNf3t1Au8+OPJhv9zUfscSXOA9wC3SzrY9gP9jN8b2F/SScAmwCslPW37tC7ziIiIiIiIiAGk8B6aP5O0t+3bgA8CtwCHlXPzgfMkbU61DP1o4O428W4BjpP0PeB1wIHAD1r0XwrsDvwn8IG+Rknb2u4FeiXtDewAvKzwtn1sw5ipVLuutyy6J289iXp2HY+IiIiIiOhYlpoPzf1UhfJi4DXAhX0nbD8GnAHcBvwUuLODeD8CHgHuAb5DVby3eqj6TKri/r+AVQ3tfyvpHkl3Uz3f/Z+dfqGIiIiIiIgYXrJbrYaONU3SJrafLjPlC4B9y/Pea4VareZ6vd6+Y0RERERExBgkaaHtWjdjstR87TNb0mbAK4Gz1qaiOyIiIiIiIrqXwnstY/vA5jZJs4BtmppPtX1dJzElTQb+pal5pe29BpVkREREREREdCyF9zrA9hFDHN8LTBmmdCIiIiIiIqILKbyjK73LltNz2pwRi780O6ZHRERERMQYk13Nh0jSVEkXlOPDJe042jl1QtJcSfWGzzVJc0cxpYiIiIiIiDEphffwOhxYJwrv4k8kvXu0k4iIiIiIiBjLUni3IKlH0gOSLinvxZ4p6WBJ8yQ9JGnPhr77AO8DviZpkaRtB4g5V1KtHL9W0tJyvJOkBWXsYknbDTD+LEmnNHw+W9KnJB1YYl9Zcp4pSW2+4teAL3Z1UyIiIiIiIqIrKbzbezNwHrALsAPwIWA/YBrw+b5Otm8FrgY+Y3uK7V92eZ1PAOfZngLUgEcG6PfPwHEAkl4B/BUws5zbDfhbqln3NwH7trnmbcBKSW9v1UnSCZLqkuqrVizv5LtEREREREREkcK7vSW2e22vBu4FbrBtoBfoGcbr3AZ8XtKpwBttP9tfJ9tLgd9L2g34S+Au278vpxfYfqTkuqjD/L5Cm1lv29Nt12zXJmw0qbNvExEREREREUAK706sbDhe3fB5NYPbFf4FXrzvG/Y12v4B1VL1Z4HrJB3UIsYlwFTgeODSAXJd1Ul+tn9W8viLDnKPiIiIiIiILuV1YsPrKWDTNn2WArsDC4Cj+holvQl42Pb55XgX4GcDxJgFfBlYn2rp+1CdDVwEPNyu4+StJ1HPK78iIiIiIiI6lhnv4fVD4DOS7hpoczXg68CJkm4FXtvQfgxwj6RFVM+Sf3+gi9h+DrgR+Dfbq4aatO1rgd8NNU5ERERERES8nKrHlWNdUjZVuxM42vZDa/LatVrN9Xq9fceIiIiIiIgxSNJC27VuxmTGex0jaUfgF1SbvK3RojsiIiIiIiK6l2e8R4ikb/Hy13mdZ/u7HY7fHLihn1PvsP2mLvKYBWzT1Hyq7es6jRERERERERGDl8J7hNj+5BDH/x6YMgx5HDHUGBERERERETF4KbwHSVIPMNv2zk3tc4FptutN7VOBmu2T11CKbUmaAlwIvIrq9WNn27681ZjeZcvpOW3OiOSzNLulR0RERETEGJTCe3xbAXzE9kOStgIWSrrO9hOjnVhERERERMRYkc3VhmY9Sd+TtFjSlZI2ajwp6XhJD0q6iYbnvSXNkHS+pFslPSzpqNL+CknflnSvpNmSru071x9JSyW9thzXymw7kt4maVH5d5ekft8tbvvBvg3abD8K/BZ43dBuSURERERERDRK4T002wPTbe8CPAmc1HdC0pbAmVQF9yHAjk1jtwT2Aw4FziltRwI9wGTgo8Deg8xrGvBJ21OA/YFn2w2QtCfwSuCX/Zw7QVJdUn3ViuWDTCkiIiIiImJ8SuE9NL+2Pa8cX0ZVSPfZC5hr+3e2nwOan52+yvZq2/cBW5S2/YArSvt/AzcOMq95wD9K+hSwme0XWnUuPxL8C3C87dXN521Pt12zXZuw0aRBphQRERERETE+pfAeGnf5udHKhmM1/e3UC7z4f7jh/1zUPodqxnwicLukHQYKIOlVwBzgi7Zv7/L6ERERERER0UYK76H5M0l9y8E/CNzScG4+cKCkzSWtDxzdQbxbgA+UZ723AA5s038psHs5/kBfo6RtbffaPheoA/0W3pJeCcwCvm/7ig7yi4iIiIiIiC5lV/OhuR84TtJ3gIeoXs11GIDtxySdAdwGPAbcCUxoE+9HwDuAe4AHqYr3Vg9Vnwn8s6TPl759/lbS26leEXYf8J8DjP9fwAHA5uV1ZwBTbS8a6IKTt55EPa/9ioiIiIiI6JjsVquhY02TtIntpyVtDiwA9i3Pe68VarWa6/V6+44RERERERFjkKSFtmvdjMmM99pntqTNqHYYP2ttKrojIiIiIiKieym81zK2D2xukzQL2Kap+VTb13USU9Jkql3LG620vdegkoyIiIiIiIiOpfBeB9g+Yojje4Epw5ROREREREREdCG7mkdERERERESMoDEz4y2pB5hte+em9rnANNv1pvapQM32yWsoxZYGyr+cmwpcb/vRFuOnAFvZvraLax4CnEP1PPlzwGds/6zVmN5ly+k5bU6nl+jY0uyUHhERERERY1RmvNcwSYP5sWMqsFWbPlOA93R5zceBw2xPBo7j5c+BR0RERERExBCNmRnvYj1J3wN2o3oP9kcaT0o6Hvgc1Xu1HwRWlvYZwJNADXg98FnbV0p6BXAB8DZgCdUPFZfavrK/i0s6neo93hOBW4GP23aZdb8V2Be4WtJlwEXAm8rQE4FHgQmSLgb2AZYB7wfeW/KaKelZYG9gZ+A8YOPyHQ4BvgxMlLQf8FXgLVTFeg9Vgf2h5nxt39Xw8V5gQ0kb2F7Z792NiIiIiIiIro21Ge/tgem2d6EqpE/qOyFpS+BMquL3EGDHprFbAvsBh1ItvwY4kqpwnQx8lKrobeUC23uU5eITS6w+m9l+m+1/AM4HbrK9K/BWqqIXYDvgW7Z3Ap4APlCK/DpwrO0pwCrgcuCUMv5g4BngdOBy21NsX17i7Q683/bLiu5+fAC4q7+iW9IJkuqS6qtWLO8gVERERERERPQZa4X3r23PK8eXURXSffYC5tr+ne3nqIrXRlfZXm37PmCL0rYfcEVp/2/gxjbXf7uk+ZJ6gYOAnRrONV7vIOBCANurbPdVs0tsLyrHC6mK/mbbA4/ZvqOMf9L2CwPkc7XtZ9vkjKSdgHOBj/d33vZ02zXbtQkbTWoXLiIiIiIiIhqMtaXm7vJzo8aZXjX9bUvShsC3qTZs+7WkM4ANG7o800GYxhxWUc2av+xStP4ejdpeU9IbgFnAR2z/ssO4ERERERER0aGxVnj/maS9bd8GfBC4heqZa4D5wHmSNqdahn40cHebeLcAx5Xnxl8HHAj8YIC+fUX245I2AY4C+n0WHLiB6rnub0qaQPWsditPAZuW4weArSTtYfsOSZsCzzb16YikzYA5wOcaVgq0NHnrSdSzA3lERERERETHxtpS8/upCuXFwGsoy7kBbD8GnAHcBvwUuLODeD8CHgHuAb5DVbz3+5Cz7SeAi4Fe4CrgjhZxT6Falt5LtaR8pxZ9AWYAF0laBEwAjgH+SdLdwE+oiv4bgR0lLZJ0TAffDeBk4M3Al8q4RZL+pMOxERERERER0QHZna5aHp8kbWL76TJTvgDYtzzvPS7VajXX6/X2HSMiIiIiIsYgSQtt17oZM9aWmo+E2WVJ9iuBs8Zz0R0RERERERHdS+Hdhu0Dm9skzQK2aWo+1fZ1aySpLkl6J9Wu5Y2W2D5iNPKJiIiIiIgYT1J4D8K6VrCWHwTWyh8FIiIiIiIixrqxtrlaRERERERExFolM979kDSV6n3cJw8hxlxgmu0xtRNZ77Ll9Jw2Z1hjLs3rySIiIiIiYgzLjDegSu5FREREREREDLtxW2xK6pF0v6RvU73T+0uSHpR0E7Bvm7FHS7pH0t2Sbi5tEyX9UNJiSZcDE9vEeFrS2SXG7ZK2KO0zJF0o6UZJD0t6m6RLS64zBhnzMEnzJd0l6acN7WeU2HPLtT7V4e2LiIiIiIiIDo3bwrvYHvg+8B7gr6kK7kOAHduMOx14p+1dgfeVthOBFbZ3Ac4Gdm8TY2Pg9hLjZuBjDedeDRwEfBq4BvgGsBMwWdKUQcS8BfgL27sBPwQ+2zBmB+CdwJ7A30lavzmopBMk1SXVV61Y3uZrRURERERERKPxXnj/yvbtwF7AXNu/s/0ccHmbcfOAGZI+BkwobQcAlwHYXgwsbhPjOWB2OV4I9DScu8a2gV7gN7Z7ba8G7m3q12nMNwDXSeoFPkNVxPeZY3ul7ceB3wJbNAe1Pd12zXZtwkaT2nytiIiIiIiIaDTeC+9nGo7d6SDbnwC+CPwpsEjS5t3GAJ4vxTXAKl660d3K8nd1w3Hf51Yb4g0U85+AC2xPBj4ObNjPtfrLIyIiIiIiIoYoRVZlPnBeKaCfBI4G7h6os6Rtbc8H5ks6jKoAvxk4FrhR0s7ALiOfdscmAcvK8XFDCTR560nUswt5REREREREx1J4A7Yfk3QGcBvwGNVmaxNaDPmapO0AATdQFek/B74raTGwCFgwokl35wzgCknLgNuBbUY3nYiIiIiIiPFDL65MjmivVqu5Xh9TryaPiIiIiIjomKSFtmvdjBnvz3hHREREREREjKgsNW9B0heonvdudIXts7uIMR/YoKn5w7Z7h5DXsMeMiIiIiIiIkZHCu4VSYHdcZA8QY69hSmdEY0ZERERERMTIyFLziIiIiIiIiBGUGe9hImkqULN98hBizAWm2V4ju5dJ2gi4AtiW6h3e19g+rdWY3mXL6TltzrDlsDSvJouIiIiIiDEuM96DpMpYuH9ft70DsBuwr6R3j3ZCERERERERY0lmvLsgqQf4T+BGYG/gKknHUr37+0FgZYuxRwN/RzWzvNz2AZImAt8FdgTuBya2uf7TwHnAocCzwPtt/0bSjPJ5B+CNwPHAcSXH+ban9hfP9oryXbD9nKQ7gTe0uQ0RERERERHRhbEwY7umbQ98H3gP8NfAvsAhVMVzK6cD77S9K/C+0nYisML2LlSbuO3eJsbGwO0lxs3AxxrOvRo4CPg0cA3wDWAnYLKkKe2+lKTNgMOAG/o5d4KkuqT6qhXL24WKiIiIiIiIBim8u/cr27cDewFzbf/O9nPA5W3GzQNmSPoYMKG0HQBcBmB7MbC4TYzngNnleCHQ03DuGtsGeoHf2O61vRq4t6nfy0haD/hX4HzbDzeftz3dds12bcJGk9qkGBEREREREY1SeHfvmYZjdzrI9ieALwJ/CiyStHm3MYDnS3EN1ZL1xkcF+pa5r+alS95X0/6RgunAQ7a/2UUuERERERER0YE84z1484HzSgH9JHA0cPdAnSVta3s+MF/SYVQF+M3AscCNknYGdhn5tF+W11eAScBHO+k/eetJ1LMTeURERERERMdSeA+S7ccknQHcRrW52p28uIS8P1+TtB0gqueo7wZ+DnxX0mJgEbBgRJNuIukNwBeAB4A7JQFcYPuSNZlHRERERETEWKYXVy5HtFer1Vyvr5HXjEdERERERKx1JC20XetmTJ7xjoiIiIiIiBhBWWo+zCR9gep570ZX2D67ixjzgQ2amj9su3cIeQ17zIiIiIiIiGgvhfcwKwV2x0X2ADH2GqZ0RjRmREREREREtJfCO7rSu2w5PafNGZZYS7M7ekREREREjAPr5DPekp7usv+BkmaPVD4trnu4pB0bPk+VtNWazmMg5b4sl7So/Dt9tHOKiIiIiIgYazLjPbIOB2YD95XPU4F7gEdHK6F+/JftQ0c7iYiIiIiIiLFqnZzx7lNmbOdKulLSA5JmqryMWtK7StstwJFt4pwhaVrD53sk9UjaWNIcSXeXtmNaxDhH0n2SFkv6uqR9gPdRvb97kaRTgRows3yeKGmppDMl3SmpV9IObXK8tHzfhyV9qrT3lO95SclxpqSDJc2T9JCkPbu6qRERERERETGsxsKM927ATlSzyPOAfSXVgYuBg4BfAJcPMva7gEdtvxdA0qT+Okl6DXAEsINtS9rM9hOSrgZm276y9Hs3MM12vXwGeNz2WyWdBEwDPtoinx2AtwObAj+XdGFpfzPVTuonAHcAHwL2oyr8P0818z6QvSXdTXX/ptm+t5/vd0KJzYRXva5FqIiIiIiIiGi2Ts94FwtsP2J7NbAI6KEqUJfYfsi2gcsGGbsXOFjSuZL2t718gH5PAn8ELpF0JLCii2v8e/m7kCr3VubYXmn7ceC3wBalfYnt3nIP7gVuKN+7t03MO4E32t4V+Cfgqv462Z5uu2a7NmGjfn97iIiIiIiIiAGMhcJ7ZcPxKl6cxXcXMV7gpfdiQwDbDwK7UxWwXx1o8zHbLwB7Aj+iml3+cRfX7su/Mfd2fZv7N7avbvi8ulVM20/afrocXwusL+m1HeYdERERERERHRgLS8378wCwjaRtbf8S+GCb/kuBQwEkvRXYphxvBfzB9mVlJ/Wp/Q2WtAmwke1rJd1Otbwd4CmqZeEM8HlUSXo98JuyPH5Pqh8fft9qzOStJ1HPa8AiIiIiIiI6NiYLb9t/LM8lz5H0OHALsHOLIT8CPiJpEdUz0g+W9slUm6OtBp4HThxg/KbAf0jaEBDw6dL+Q+DishHaUcAM4CJJzwJ7D/b7DaOjgBMlvQA8C/xVWaIeERERERERw0Sps6IbtVrN9Xp9tNOIiIiIiIgYFZIW2q51M2YsPOMdERERERERsdYak0vNByLpeOCUpuZ5tj/ZRYxZlGfAG5xq+7qh5lfiDznHNREzIiIiIiIiOpOl5tGVLDWPiIiIiIjxbDBLzcfVjPdIkjQVqNk+eQgx5gLTbK+xyrZcc0uqzdUA/tL2bwfq37tsOT2nzRnydZdmZ/SIiIiIiBgnUngPkiRRrRhYPdq5DINj12SxHxERERERMZ6k8O6CpB7gP4EbqV4HdpWkY4HHqF5BtrLF2KOBvwNWActtHyBpIvBdYEfgfmBim+s/DZxH9c7xZ4H32/6NpBnl8w7AG4HjgeNKjvNtTx3UF46IiIiIiIghy67m3dse+D7wHuCvgX2BQ6iK51ZOB95pe1fgfaXtRGCF7V2As4Hd28TYGLi9xLgZ+FjDuVcDB1G9Q/wa4BvATsBkSVPaxP2upEWSvlRm8l9C0gmS6pLqq1YsbxMqIiIiIiIiGqXw7t6vbN8O7AXMtf07288Bl7cZNw+YIeljwITSdgBwGYDtxcDiNjGeA2aX44VAT8O5a1ztlNcL/MZ2b1kGf29Tv2bH2p4M7F/+fbi5g+3ptmu2axM2mtQmxYiIiIiIiGiUwrt7zzQcd7wlvO1PAF8E/hRYJGnzbmMAz/vFbehX8dJHBfqWua/mpUveV9PikQLby8rfp4AfAHt2kU9ERERERES0kcJ78OYDB0raXNL6wNGtOkva1vZ826cDj1MV4DcDx5bzOwO7jHDOzTmtJ+m15Xh9qmfH71mTOURERERERIx12VxtkGw/JukM4DaqzdXu5MUl5P35mqTtAAE3AHcDP6d6vnoxsAhYMKJJv9wGwHWl6J4A/BS4uNWAyVtPop5XgUVERERERHRML65cjmivVqu5Xs+bxyIiIiIiYnyStNB2rZsxWWoeERERERERMYKy1HyYSfoCL3/e+wrbZ3cRYz7VMvBGH7bdO4S8hj1mREREREREtJfCe5iVArvjInuAGHsNUzojGjMiIiIiIiLay1LziIiIiIiIiBE0Zma8JfUAs23v3NQ+F5hmu97UPhWo2T55DaXY0kD5l3NTgettP9pi/BRgK9vXdnHNPYHpfR+BM2zPajWmd9lyek6b0+kl+rU0u6JHRERERMQ4khnvNUzSYH7smAps1abPFOA9XV7zHqofH6YA7wK+M8j8IiIiIiIiYgBjrchaT9L3gN2AB4GPNJ6UdDzwOar3bj8IrCztM4AngRrweuCztq+U9ArgAuBtwBKqHyoutX1lfxeXdDpwGDARuBX4uG2XWfdbgX2BqyVdBlwEvKkMPRF4FJgg6WJgH2AZ8H7gvSWvmZKeBfYGdgbOAzYu3+EQ4MvAREn7AV8F3kJVrPcAjwMfas7X9oqGjxsCebdcRERERETEMBtrM97bA9Nt70JVSJ/Ud0LSlsCZVMXvIcCOTWO3BPYDDgXOKW1HUhWuk4GPUhW9rVxge4+yXHxiidVnM9tvs/0PwPnATbZ3Bd4K3Fv6bAd8y/ZOwBPAB0qRXweOLTPTq4DLgVPK+IOBZ4DTgcttT7F9eYm3O/B+2y8ruhvuy16S7gV6gU/YfqGfPidIqkuqr1qxvM0tiIiIiIiIiEZjrfD+te155fgyqkK6z17AXNu/s/0cVfHa6Crbq23fB2xR2vajehXYatv/DdzY5vpvlzRfUi9wELBTw7nG6x0EXAhge5Xtvmp2ie1F5XghVdHfbHvgMdt3lPFP9lcsF1fbfrZVwrbnl0J/D+Bzkjbsp8902zXbtQkbTWoVLiIiIiIiIpqMtcK7eal0u8+NVjYcq+lvW6Vg/TZwlO3JwMVUy7f7PNNBmMYcVtH/owCi8yXhnVwTANv3l/4v29wtIiIiIiIiBm+sPeP9Z5L2tn0b8EHgFqpnrgHmA+dJ2pxqGfrRwN1t4t0CHFeeG38dcCDwgwH69hXZj0vaBDgK6PdZcOAGque6vylpAtWz2q08BWxajh8AtpK0h+07JG0KPNvUpyOStqFaJfCCpDdSzaYvbTVm8taTqGdX8oiIiIiIiI6NtRnv+6kK5cXAayjLuQFsPwacAdwG/BS4s4N4PwIeodr9+ztUxXu/DznbfoJqlrsXuAq4o0XcU6iWpfdSLSnfqUVfgBnARZIWAROAY4B/knQ38BOqov9GYEdJiyQd08F3g2op/d0l7izgJNuPdzg2IiIiIiIiOiA7G1m3ImkT20+XmfIFwL7lee9xqVaruV6vt+8YERERERExBklaaLvWzZixttR8JMyWtBnwSuCs8Vx0R0RERERERPdSeLdh+8DmNkmzgG2amk+1fd0aSapLkt4JnNvUvMT2EaORT0RERERExHiSwnsQ1rWCtfwgsFb+KBARERERETHWjbXN1SIiIiIiIiLWKpnxHkaSeoDZttepd2GXV5rVgWW2D23Vt3fZcnpOmzOk6y3N68giIiIiImIcyYz3AFRZ4/enFMFr2ilUr2KLiIiIiIiIYZbCu4GkHkn3S/o21Xu+vyTpQUlzJV0s6YLSb4ak8yXdKulhSUd1Ef+/JN1Z/u1T2g+UdKOkH1C9B7xVbhdLulfS9ZImlnNzJX1D0s2lzx6S/l3SQ5K+0ianNwDvBS7p+EZFREREREREx1J4v9z2wPepitHjgb8ADgF2aOq3JbAfcChwToexfwscYvutwDHA+Q3n9gS+YHvHFuO3A75leyfgCeADDeees30AcBHwH8AngZ2BqeUd5AP5JvBZYPVAHSSdIKkuqb5qxfIWoSIiIiIiIqJZCu+X+5Xt26kK4Zts/8H288AVTf2usr3a9n3AFh3GXh+4WFJviddYZC+wvaTN+CW2F5XjhUBPw7mry99e4F7bj9leCTwM/Gl/wSQdCvzW9sJWF7U93XbNdm3CRpPapBgRERERERGNsrnayz1T/qpNv5UNx+369vk08BtgV6ofPf7Yz3U7veYqYGI/51Y39VvNwP/P+wLvk/QeYEPgVZIus/2/O8glIiIiIiIiOpDCe2ALgG9IejXwFNWy7n6fv+7CJOAR26slHQeMxkZq/8P254DPQfWcOTCtXdE9eetJ1LMreURERERERMey1HwAtpcBfw/MB34K3AcM9QHnbwPHSbod+HM6m+WOiIiIiIiIdZhsj3YOay1Jm9h+WtJ6wCzgUtuzRjuv0VSr1Vyv10c7jYiIiIiIiFEhaaHtWjdjMuPd2hmSFgH3AEuAq0Y5n4iIiIiIiFjH5BnvFmxPG8w4Se8Ezm1qXmL7iA7Gbg7c0M+pd9j+/SDzGfaYERERERER0ZkU3iPA9nXAdYMc+3tgyjDnM+wxIyIiIiIiojNZah4RERERERExgtaaGW9J+wMXAc8DHwR2s/2D0c1qeDS8quvQfs4tBWq2H5f0tO1NOow5A5ht+8oBzh8OPGj7vkEn3o/eZcvpOW3OoMcvzavIIiIiIiJinFmbZryPBb5uewqwBfChNXXhsmv5WHM4sONoJxERERERETHejUrhLWljSXMk3S3pHkmnAv8LOF3STOAcYH9JiyR9eoAYEyR9TdIdkhZL+nhpP1DSTZL+TdKDks6RdKykBZJ6JW1b+s2Q9I+SbgTOlfQ6ST+RdKek70j6laTXSuqRdL+kiyXdK+l6SRNLjDdL+mn5Hnf2xR7AqyTNknSfpIskdXXvVbmgjJ8D/EnDuXNK+2JJX5e0D/A+4GvlHm4raa6kc8t9eLCsMOi7j18v92axpL/pJq+IiIiIiIhobbRmet8FPGr7vQCSJgFvoSydbrU0u8FfA8tt7yFpA2CepOvLuV1LvD8ADwOX2N5T0inA3wB/W/r9OXCw7VWSLgB+Zvurkt4FnNBwre2AD9r+mKR/Az4AXAbMBM6xPUvShrT+IWNPqhnoXwE/Bo4E+l0mPoAjgO2ByVQrAu4DLpX0mnJuB9uWtJntJyRdTcNSdEkA65X78B7g74CDy/fchmpp/wsl3ktIOqHvfkx41eu6SDkiIiIiIiJGa6l5L3BwmYHd3/byQcT4S+Aj5T3b84HNqQpkgDtsP2Z7JfBLoK8g7wV6GmJcYXtVOd4P+CGA7R8D/7eh3xLbi8rxQqBH0qbA1rZnlTF/tL2iRb4LbD9crvev5XrdOAD4V9urbD8K/Ky0Pwn8EbhE0pFAqxz+vfE7lOODgYtsv1C+xx+aB9mebrtmuzZho0ldph0RERERETG+jUrhbftBYHeqQvirkk4fRBgBf2N7Svm3je2+AntlQ7/VDZ9X89JZ/meaNi+gBgAAIABJREFU4g2kMd6qEqNV//64zefBxKAUzHsCP6J6rvvHLcb3fY++7wDV9xhMLhEREREREdGBUVlqLmkr4A+2L5P0NDAVeKKhy1PApm3CXAecKOlntp+X9OfAsiGkdQvVc+bnSvpL4NWtOtt+UtIjkg63fVVZ7j6hxaz3npK2oVpqfgwwvcv8bgY+Lun7VM93vx34gaRNgI1sXyvpduAXpX8n9xCq1QCfkDS3b6l5f7PefSZvPYl6diaPiIiIiIjo2GgtNZ8MLCjLxL8AfKXp/GLghbJpWb+bqwGXUD3nfKeke4DvMLQfEs4E/lLSncC7gceoitdWPgx8StJi4Fbg9S363ka1adw9wBJgVpf5zQIeololcCFwU2nfFJhdcrgJ6LtfPwQ+I+muNpu+XQL8/8BiSXezBneTj4iIiIiIGA9kZ5UxQJmxXlVmffcGLiyvNosGtVrN9Xp9tNOIiIiIiIgYFZIW2q51M2Ysvr96sP4M+Lfymq/ngI+Ncj4RERERERExBqz1hbekdwLnNjUvsX3EcF7H9kPAbkOJIWky8C9NzStt77UmY0RERERERMTaY60vvG1fR7WR2lrPdi8wpOXpwxEjIiIiIiIi1h5rfeEda5feZcvpOW3OoMcvzY7oERERERExzozWrubRRNJcSV09oD/E620kaY6kByTdK+mcNXXtiIiIiIiI8SSF9/j2dds7UD3bvq+kd492QhEREREREWNNCu8hkvS/JS2QtEjSdyRNkPS0pHMlLZT0U0l7lhnthyW9r4ybKOmHkhZLuhyY2OY6T0s6u7zb/HZJW5T2GZIulHRjif82SZdKul/SjIHi2V5h+8Zy/BxwJ/CG4bovERERERERUUnhPQSS3gIcA+xb3vm9CjgW2BiYa3t34CngK8AhwBHAl8vwE4EVtncBzgZ2b3O5jYHbbe8K3MxLX3f2auAg4NPANcA3gJ2AyZLabtQmaTPgMOCGAc6fIKkuqb5qxfJ24SIiIiIiIqJBNlcbmndQFcx3SIJq1vq3VO8B/3Hp00v1OrDnJfUCPaX9AOB8ANuLJS1uc63ngNnleCFVId/nGtsu8X9TdkZH0r3leosGCippPeBfgfNtP9xfH9vTgekAG2y5ndvkGREREREREQ1SeA+NgO/Z/txLGqVptvsK1NXASgDbq0uh26ebIvb5hpireOn/3crmazV8bvd/PB14yPY3u8glIiIiIiIiOpTCe2huAP5D0jds/1bSa4BNOxx7M9Wy9Bsl7QzsMlJJDkTSV4BJwEc7HTN560nU80qwiIiIiIiIjuUZ7yGwfR/wReD6slT8J8CWHQ6/ENikjPsssGBksuyfpDcAXwB2BO4sm8N1XIBHREREREREZ/Ti6uWI9mq1muv1+minERERERERMSokLbRd62ZMZrwjIiIiIiIiRlCe8V7LSJoPbNDU/OG+ncrXlpgRERERERHRmRTeaxnbe60LMSMiIiIiIqIzKbzXYpKetr1JF/0PBKbZPnSkcupdtpye0+YMevzS7IgeERERERHjTJ7xjpdoes94REREREREDFEK73WApAMlzZV0paQHJM2UpHLuXaXtFuDINnH2lHSrpLvK3+1L+1RJV0i6Brh+5L9RRERERETE+JHZzXXHbsBOwKPAPGBfSXXgYuAg4BfA5W1iPAAcYPsFSQcDfw98oJzbG9jF9h+aB0k6ATgBYMKrXjcMXyUiIiIiImL8SOG97lhg+xEASYuAHuBpYInth0r7ZZQCeQCTgO9J2g4wsH7DuZ/0V3QD2J4OTAfYYMvt8uL3iIiIiIiILmSp+bpjZcPxKl780aSbQvgs4EbbOwOHARs2nHtmaOlFREREREREfzLjvW57ANhG0ra2fwl8sE3/ScCycjx1MBecvPUk6tmZPCIiIiIiomOZ8V6H2f4j1dLyOWVztV+1GfL/AV+VNA+YMNL5RUREREREBMjOI7vRuVqt5nq9PtppREREREREjApJC23XuhmTGe+IiIiIiIiIEZRnvMcgSccDpzQ1z7P9ydHIJyIiIiIiYjxL4T0G2f4u8N3RziMiIiIiIiKy1DwiIiIiIiJiRI2ZGW9JPcDs8o7qxva5wDTb9ab2qUDN9slrKMWWBsq/nJsKXG/70RbjpwBb2b62i2tuDlwJ7AHM6ORe9C5bTs9pczq9xEsszWvIIiIiIiJiHMqM9xomaTA/dkwFtmrTZwrwni6v+UfgS8C0QeQUERERERERHRgzM97FepK+B+wGPAh8pPFk2XTsc8Bj5fzK0j4DeBKoAa8HPmv7SkmvAC4A3gYsofqh4lLbV/Z3cUmnA4cBE4FbgY/bdpl1vxXYF7ha0mXARcCbytATgUeBCZIuBvYBlgHvB95b8pop6Vlgb2Bn4Dxg4/IdDgG+DEyUtB/wVeAtVMV6D/A48KHmfG0/A9wi6c2tb2tEREREREQM1lib8d4emG57F6pC+qS+E5K2BM6kKn4PAXZsGrslsB9wKHBOaTuSqnCdDPw/9u493M6yPvf99zYIJAQTUKSYohMRQUkgmiEUOYgIG2sRRWWxlaqhlWwQFsLerJqqRayyhGKlYBUFi0HRyhIEIUFQWYRIJIERTDLDQagQF0QqgjWAgQSSe//xPlOGgznHYR4yw8z9ua55zfd93ufwGyP55zefw/sRqqS3lX+1/aayXHx86avPZNtvsf3PwAXAzbb3Bt4I3Fnq7AZ82faewO+B95Ykvw4ca3s6sB64HPhYaX8o8AfgDOBy29NtX176mwG8y/bzku5uSJolqS6pvn7N6qF0FRERERERsdkZa4n3g7YXluvLqBLpPvsC823/1vY6quS10dW2N9i+C9ixlB0AfK+U/ydwU5vx3yppsaRe4BBgz4ZnjeMdAlwIYHu97b5s9gHbS8v1Eqqkv9nuwMO2by/tH7f97ADxXGP7qTYxt2X7Its127VxEyYNtbuIiIiIiIjNylhbau4u7xutbbhW0++2JG0NfIXqwLYHJZ0JbN1Q5Q8ddNMYw3qqWfPnDUXrz9GokzEjIiIiIiJiBI21xPuVkvazfSvwfuAWqj3XAIuB88tJ3o8DRwPL2vR3C/Dhsm98B+Bg4DsD1O1Lsh+VNBF4H9WJ4f25kWpf979IGke1V7uVJ4Bty/U9wCskvcn27ZK2BZ5qqjNipk2ZRD2nk0dERERERHRsrC01v5sqUV4ObE9Zzg1g+2HgTOBW4CfAHR30dyXwELAC+BpV8t7vJmfbvwcuBnqBq4HbW/T7Mapl6b1US8r3bFEXYA7wVUlLgXHAMcCXJC0DfkyV9N8EvF7SUknHdPDZAJC0EvgiMFPSQ5Ka975HRERERETEEMjudNXy5knSRNtPlpny24D9y37vzVKtVnO9Xm9fMSIiIiIiYgyStMR2rZs2Y22p+UiYK2kysCXw2c056Y6IiIiIiIjuJfFuw/bBzWWSrgJ2aSr+uO0bNkpQXZJ0OHBOU/EDto8ajXgiIiIiIiI2J0m8B+GFlrCWPwhskn8UiIiIiIiIGOvG2uFqEREREREREZuUF+SMt6QnbU/sov7BwOm2jxi5qPod993AvbbvKvczgR/Z/vXGjGMgkt4FfBbYADwLnGr7llZteletpmf2vK7HWplXkEVERERExGYqM94j691A4+u5ZgKvGJ1Q+nUjsLft6cDfAF8f5XgiIiIiIiLGnBd04i3pYEnzJV0h6R5J35ak8uztpewW4D1t+jlT0ukN9ysk9UjaRtI8SctK2YDvx5Z0tqS7JC2X9AVJbwaOBM4t79b+OFADvl3ux0taKekzku6Q1CtpjzYxXlI+7/2STinlPeVzfr3E+G1Jh0paKOk+SfsM1KftJ/3c++S2AfJuuYiIiIiIiGH2glxq3uQNwJ7Ar4GFwP6S6sDFwCHAfwCXD7LvtwO/tv1XAJIm9VdJ0vbAUcAeti1psu3fS7oGmGv7ilLvL6mWvNfLPcCjtt8o6aPA6cBHWsSzB/BWYFvgF5IuLOWvAY4GZgG3Ax8ADqBK/D9BNfPeL0lHAZ8HXg70ux5c0qzSN+NeskOL8CIiIiIiIqLZC3rGu7jN9kO2NwBLgR6qBPUB2/eVGd3LBtl3L3CopHMkHWh79QD1HgeeBr4u6T3Ami7G+H75vYQq9lbm2V5r+1HgEWDHUv6A7d7yHdwJ3Fg+d2+7Pm1fZXsPquT8swPUuch2zXZt3IR+//YQERERERERAxgLiffahuv1PDeL382y6Wf50+9iawDb9wIzqBLYz0s6o7/Gtp8F9gGupEpgr+9i7L74G2NvV7e5fmP5hob7DR30CYDtBcCukl7WSf2IiIiIiIjozFhYat6fe4BdJO1q+5fA+9vUXwkcASDpjcAu5foVwO9sXybpSarD0Z5H0kRggu3rJC2iWt4O8ATVsnAGuB9Vkl4D/LIsj38jsCXwWKs206ZMop4TyiMiIiIiIjo2JhNv20+XfcnzJD0K3AJMbdHkSuBDkpZS7ZG+t5RPozocbQPwDHDiAO23BX4gaWtAwGml/LvAxeUgtPcBc4CvSnoK2G+wn28YvZfqcz8DPAUc03DYWkRERERERAwDJc+KbtRqNdfr9dEOIyIiIiIiYlRIWmK71k2bsbDHOyIiIiIiImKTNSaXmg9E0nHAx5qKF9o+qYs+rqLsAW/wcds3DDW+0v+QY9wYfUZERERERERnstQ8upKl5hERERERsTkbzFLzzWrGO4aud9VqembP67rdypyEHhERERERm6ns8R4mkmZK+tch9jFfUld/ORkukq6RtGI0xo6IiIiIiBjLkngPkipj4vuT9B7gydGOIyIiIiIiYiwaE4njxiKpR9Ldkr4C3AH8g6R7Jd0M7N+m7dGSVkhaJmlBKRsv6buSlku6HBjfpo8nJZ1V+lgkacdSPkfShZJuknS/pLdIuqTEOqdNnxOB/xf4XMdfRERERERERHQsiXf3dge+CbwD+FuqhPsw4PVt2p0BHG57b+DIUnYisMb2XsBZwIw2fWwDLCp9LACOb3i2HXAIcBpwLXAesCcwTdL0Fn1+FvhnYM1AFSTNklSXVF+/ZnWbECMiIiIiIqJREu/u/cr2ImBfYL7t39peB1zept1CYI6k44Fxpewg4DIA28uB5W36WAfMLddLgJ6GZ9e6OqK+F/iN7V7bG4A7m+r9UUnIX2P7qlaD2r7Ids12bdyESW1CjIiIiIiIiEZJvLv3h4brjt/FZvsE4FPAzsBSSS/ttg/gGT/3/rf1/Omp9GvL7w0N1333A51evx8wQ9JK4BbgtZLmdxFPREREREREtJHXiQ3eYuD8kkA/DhwNLBuosqRdbS8GFkt6J1UCvgA4FrhJ0lRgr5EP+zm2LwQuLPH1AHNtH9yqzbQpk6jn1WAREREREREdS+I9SLYflnQmcCvwMNVha+NaNDlX0m6AgBupkvRfAN+QtBxYCtw2okFHRERERETERqfnVi5HtFer1Vyv10c7jIiIiIiIiFEhaYntWjdtssc7IiIiIiIiYgRlqfkwk/RJqv3ejb5n+6wu+lgMbNVU/EHbvUOIa9j7jIiIiIiIiPaSeA+zkmB3nGQP0Me+wxTOiPYZERERERER7SXx3kSU13idbnujbaAuY+4EPFWK/i/bj7Rq07tqNT2z53U1zsqcgh4REREREZuxJN5x7MZM9iMiIiIiIjY3OVxtiCT9taTbJC2V9DVJ4yQ9KekcSUsk/UTSPpLmS7pf0pGl3XhJ35W0XNLlwPg24zwp6SxJyyQtkrRjKZ8j6UJJN5X+3yLpEkl3S5oz8t9AREREREREtJLEewgkvQ44Btjf9nRgPXAssA0w3/YM4Angc8BhwFHAP5bmJwJrbO9FtSd8RpvhtgEW2d4bWAAc3/BsO+AQ4DTgWuA8YE9gmqTpbfr9RvmjwT9I0gCfc5akuqT6+jWr23QXERERERERjZJ4D83bqBLm2yUtLfevBtYB15c6vcDNtp8p1z2l/CDgMgDby4HlbcZaB8wt10sa+gG41tUL2XuB39jutb0BuLOpXrNjbU8DDiw/H+yvku2LbNds18ZNmNQmzIiIiIiIiGiUxHtoBFxqe3r52d32mcAzJREG2ACsBSjJcOO+etO5xj7XN/WztnmshvsB9/HbXlV+PwF8B9ini3giIiIiIiKiA0m8h+ZG4H2SXg4gaXtJr+qw7QKqZelImgrsNTIh9k/SFpJeVq5fDBwBrNiYMURERERERGwOcqr5ENi+S9KngB9JehHwDHBSh80vpNpfvRxYCtw2QmEOZCvghpJ0jwN+AlzcrtG0KZOo5/VgERERERERHdNzq5cj2qvVaq7X8/axiIiIiIjYPElaYrvWTZssNY+IiIiIiIgYQVlqvomRtJhqGXijD9ru3ZT6jIiIiIiIiM4k8d7E2N73hdBnREREREREdCZLzSMiIiIiIiJGUGa8ByDpFOBE4A7bxw6i/WTgA7a/Uu57gDfb/s4wxDYTqNk+eYDn04FX2L5uqGM16121mp7Z87pqszKnoEdERERExGYsM94D+yjwjsakW1I3f6iYXPro0wN8YHhCa2s68I6NNFZERERERES0kBnvfkj6KvBq4BpJrwQup0qcH6Wf5FnSnsA3gC2p/pjxXuCzwK6SlgI/Bg4EXlfuLwX+CzgSmADsClxl++9axHQc8PfAw8C9wNpSfjTwaWA9sBo4FPhHYLykA4DPA68DXlk+0yuBf7F9QWn/IeB0wMBy2x/s+guLiIiIiIiIASXx7oftEyS9HXgrcDLwTuAA208N0OQE4Hzb35a0JTAOmA1MtT0dQNLBwOm2jyj3M6lmpt9AlUT/QtKXbD/Y3LmknYDPADOokuubgJ+Xx2cAh9teJWmy7XWSzqBhKbqkM4E9yufZtox1IfBa4JPA/rYflbR9fx9O0ixgFsC4l+zQ9vuLiIiIiIiI52SpeWeuaZF0A9wKfELSx4FXtanb6Ebbq20/DdwFvGqAevsC823/1vY6qhn4PguBOZKOp0r4BzLP9lrbjwKPADsChwBXlDJs/66/hrYvsl2zXRs3YVKHHy0iIiIiIiIgiXen/tDqYTkw7UjgKeAGSYd02O/ahuv1tF6B4AHGPgH4FLAzsFTSS7sYSwP1GxEREREREcMjS82HgaRXA/fbvqBc7wUso1rW3eeJpvtuLAbOL0n148DRpX8k7Wp7MbBY0jupEvBOx7oRuErSebYfk7T9QLPefaZNmUQ9p5RHRERERER0LDPew+MYYEU5OG0P4Ju2HwMWSloh6VxgOfCspGWSTuumc9sPA2dSLWn/CXBHw+NzJfVKWgEsoErIbwJeL2mppGNa9HsncBZws6RlwBe7iSsiIiIiIiLak52VxtG5Wq3mer0+2mFERERERESMCklLbNe6aZMZ74iIiIiIiIgRlD3eXZB0OHBOU/EDto8axjEWA1s1FX/Qdu9wjREREREREREbTxLvLti+AbhhhMfYdyT7j4iIiIiIiI0rS80jIiIiIiIiRlBmvDcRkuYDp9veaCeXSboe2Inq/8FPgZNsr2/VpnfVanpmz+tqnJV5/VhERERERGzGMuO9eftvtvcGpgI7UL0fPCIiIiIiIoZREu8hkvTXkm4r78z+mqRxkp6UdI6kJZJ+ImkfSfMl3S/pyNJuvKTvSlou6XJgfJtxnpR0VnkP+CJJO5byOZIulHRT6f8tki6RdLekOa36tP14udwC2BLIu+UiIiIiIiKGWRLvIZD0OuAYYH/b04H1wLHANsB82zOAJ4DPAYcBRwH/WJqfCKyxvRdwFjCjzXDbAIvKDPUC4PiGZ9sBhwCnAdcC5wF7AtMkTW/zGW4AHilxXjFAnVmS6pLq69esbhNmRERERERENEriPTRvo0qYb5e0tNy/GlgHXF/q9AI3236mXPeU8oOAywBsLweWtxlrHTC3XC9p6AfgWtsu/f/Gdq/tDcCdTfWex/bhVPu8t6JK3vurc5Htmu3auAmT2oQZERERERERjZJ4D42AS21PLz+72z4TeKYkwgAbgLUAJRluPNCum6XdjX2ub+pnbfNYDfdtD9Cz/TRwDfCuLuKJiIiIiIiIDuRU86G5EfiBpPNsPyJpe2DbDtsuoFqWfpOkqcBeIxVkfyRNBLa1/bCkLYB3UJ1s3tK0KZOo55TyiIiIiIiIjiXxHgLbd0n6FPAjSS8CngFO6rD5hcA3JC0HlgK3jVCYA9kGuEbSVsA44H8DX93IMURERERERIx5em71ckR7tVrN9fpGe9V4RERERETEJkXSEtu1btpkj3dERERERETECMpS802MpMVUJ4w3+qDt3k2pz4iIiIiIiOhMEu9NjO19Xwh9RkRERERERGey1DwiIiIiIiJiBGXGexhJ6gHm2p46yqF0RNLOwDeBP6N65/dFts9v1aZ31Wp6Zs/reIyVefVYRERERERs5pJ4D0CSqE5937CRxx1ne/1GGu5Z4P+zfYekbYElkn5s+66NNH5ERERERMSYl6XmDST1SLpb0leAO4B/kHSvpPmSLpb0r6XeHEkXSPqZpPslva+L/n8q6Y7y8+ZSfrCkmyR9B+j3wLOG2C6WdKekH0kaX57Nl3SepAWlzpskfV/SfZI+N1A8th+2fUe5fgK4G5jSxVcWERERERERbSTxfr7dqZZf/xVwHPAXwGHAHk31dgIOAI4Azu6w70eAw2y/ETgGuKDh2T7AJ22/vkX73YAv294T+D3w3oZn62wfBHwV+AFwEjAVmCnppe0CK8vk3wAs7ufZLEl1SfX1a1a36yoiIiIiIiIaJPF+vl/ZXkSVCN9s+3e2nwG+11TvatsbyrLsHTvs+8XAxZJ6S3+NSfZtth9o0/4B20vL9RKgp+HZNeV3L3Bnmc1eC9wP7NyqU0kTgSuBU20/3vzc9kW2a7Zr4yZMahNiRERERERENMoe7+f7Q/mtNvXWNly3q9vnNOA3wN5Uf/R4up9xOx1zPTC+n2cbmuptoMW/s6QXUyXd37b9/Q5iiIiIiIiIiC4k8R7YbcB5krYDnqBa1t3v/usuTAIesr1B0oeBcUPsb0jKAXL/Btxt+4udtJk2ZRL1nFQeERERERHRsSw1H4DtVcD/pNrz/BPgLmCoG5y/AnxY0iLgtXQ2yz2S9gc+CBwiaWn5eccoxxQRERERETGmyPZox7DJkjTR9pOStgCuAi6xfdVoxzWaarWa6/X6aIcRERERERExKiQtsV3rpk1mvFs7U9JSYAXwAHD1KMcTERERERERLzDZ492C7dMH007S4cA5TcUP2D6qg7YvBW7s59HbbD82yHiGvc+IiIiIiIjoTBLvEWD7BuCGQbZ9DJg+zPEMe58RERERERHRmSTe0ZXeVavpmT2vo7orc/p5RERERERE9nh3Q9JkSR8dZNuapAsG2fYSSY9IWtFUvr2kH0u6r/zerpRL0gWS/kPScklvHMy4ERERERERMXRJvLszGRhU4m27bvuUQY47B3h7P+WzgRtt70a1h3t2Kf9LYLfyMwu4cJDjRkRERERExBAl8S4kfajMDi+T9C1JO0q6qtwvk/Rm4Gxg1/K+63MlXd743mtJcyS9d4D+D5Y0t1yfWWax50u6X1LLhNz2AuB3/Tx6F3Bpub4UeHdD+TddWQRMlrRTieFmSf9L0r2SzpZ0rKTbJPVK2rWb7ywiIiIiIiLayx5vQNKewCeB/W0/Kml7qlnim20fJWkcMJFqRnmq7eml3VHAMcB1krYE3gac2OGwewBvBbYFfiHpQtvPdBn6jrYfBrD9sKSXl/IpwIMN9R4qZQB7A6+jSuTvB75uex9JHwP+O3Bq8yCSZlHNnDPuJTt0GWJERERERMTmLTPelUOAK2w/CmD7d6XswnK/3vbqftr9EDhE0lZUy7sX2H6qwzHn2V5bxnwE2HGoH6KB+ilz+X277YdtrwV+CfyolPcCPf11Zvsi2zXbtXETJg1jmBEREREREWNfEu+KeC4x7Zjtp4H5wOFUM9/f7aL52obr9Qxu9cFvJO0EUH4/UsofAnZuqPfnwK/7GXdDw/2GQcYQERERERERLSTRqtwIXCXpPNuPlaXmN1ItG/+XstR8G+AJqqXhjb4LfASoATM3XsgAXAN8mGrv+YeBHzSUnyzpu8C+wOqyFH33oQ44bcok6nlNWERERERERMcy4w3YvhM4C7hZ0jLgi8DHgLdK6gWWAHvafgxYKGmFpHNL8x8BBwE/sb1uJOKT9O/ArcDukh6S9Lfl0dnAYZLuAw4r9wDXUe3f/g/gYgZ5EntEREREREQMneyuV1jHZqxWq7ler492GBEREREREaNC0hLbtW7aZMY7IiIiIiIiYgRlj/cwk3Q4cE5T8QO2j2rT7qVU+8qbva0scY+IiIiIiIgXoCTew8z2DcANg2j3GDB9+COKiIiIiIiI0dRR4i3ptVTvtN7R9lRJewFH2v7ccAYjqQeYa3tqU/l84HTb9abymUDN9snDGcdIkDSH6rNd0WW7fwf2BL5h+7x+nvcAb7b9nUHGdRbwIWA72xPb1e9dtZqe2fPa9rsyJ59HREREREQAne/xvhj4e+AZANvLgf97pIKKiqQ/o0qq9+ov6S56gA8MYZhrgX2G0D4iIiIiIiJa6DTxnmD7tqayZ4c7mGILSZdKWi7pCkkTGh9KOk7SvZJuBvZvKJ8j6QJJP5N0v6T3lfIXSfqKpDslzZV0Xd+z/khaKell5bpWZtuR9BZJS8vPzyU1v8+7sY+/k9QraZmks/t5fraku8pn/EIpO7q8pmyZpAWl6o+Al5cxD5T0Gkk/KXXukLQr1SvEDix1TpM0U9L3JV0v6T5J/9Tqy7a9yPbDrepERERERETE4HW6x/vRkuQZoCSuI5Ws7Q78re2Fki6h4R3UknYCPgPMAFYDNwE/b2i7E3AAsAdwDXAF8B6qWeFpwMuBu4FLBhHX6cBJJa6JwNP9VZL0l8C7gX1tr5G0fdPz7YGjgD1sW9JQKFgkAAAgAElEQVTk8ugM4HDbqxrKjqRanj69tF0MnG37KklbU/3hZDbVMvwjSp2ZVHvF3wCsBX4h6Uu2HxzEZ+6LeRYwC2DcS3YYbDcRERERERGbpU5nvE8CvgbsIWkVcCpwwgjF9KDtheX6MqpEus++wHzbv7W9Dri8qe3VtjfYvgvYsZQdAHyvlP8nVbI+GAuBL0o6BZhse6AZ/0Op9mOvAbD9u6bnj1Ml7V+X9B5gTUP/cyQdD4xr7rTMsE+xfVXp9+m+Mfpxo+3Vtp8G7gJe1fGn7Ifti2zXbNfGTZg0lK4iIiIiIiI2O20Tb0kvojrA7FBgB6qZ2gNs/2qEYnKX943WNlyr6XennuW572XrPw5qnw18BBgPLJK0xwDt1SrGkrDvA1xJNTN+fSk/AfgUsDOwtLxerLnfTjV+D+vJ6fURERERERGjpm3ibXsDcHK5/oPtJ0Y4pldK2q9cvx+4peHZYuBgSS+V9GLg6A76uwV4b9nrvSNwcJv6K6mWsgO8t69Q0q62e22fA9SplrP350fA3/TtTe9nqflEYJLt66hWDvQtI9/V9mLbZwCPUiXgf2T7ceAhSe8u9bcqYzwBDLjfPCIiIiIiIkZXpzOhP5Z0OtXS7j/0FfazjHo43A18WNLXgPuoXmP2zjLew5LOBG6l2mN+B/0sy25yJfA2YAVwL1XyvrpF/c8A/ybpE6Vun1MlvZVqBvku4If9NbZ9vaTpQF3SOuA64BMNVbYFflD2aAs4rZSfK2m3UnYjsIznLxH/IPA1Sf9IdcL80cBy4FlJy4A5wH+1+GzPUw5f+wAwQdJDwNdtnzlQ/WlTJlHPq8IiIiIiIiI6JrvVyu1SSXqgn2LbfvXwhzT8JE20/WRZvn0bsH/Z7x1dqtVqrtfr7StGRERERESMQZKW2K5106ajGW/buwwupE3G3HJS+JbAZ5N0R0RERERExMbSUeIt6UP9ldv+5vCGMzJsH9xcJukqoPkPCh+3fUMnfUqaBnyrqXit7X0HFeQIK68i26qp+IO2e0cjnoiIiIiIiM1Fp3u839RwvTXVnuk7gBdE4t0f20cNsX0v5WC0F4JN9Q8CERERERERY12nS83/e+O9pEk8f7Y3IiIiIiIiIpoM9v3Oa4DdhjOQFypJT9qeuJHH7AHm2p46wPPJwAdsf2W4x+5dtZqe2fPa1luZk88jIiIiIiKAzvd4Xwv0HX/+IuD1wPdGKqgYssnAR4FhT7wjIiIiIiKiO53OeH+h4fpZ4Fe2HxqBeDZpkq4Gdqba536+7YtK+VnAEcBTwLts/0bS0cCnqd77vdr2QZJmAu+mevf4VOCfqU5a/yCwFnjHQO9GlzQDuIRqtcEtDeV7At8o/bwIeC/wWWBXSUuBHwPzgDOBR8u4S4C/tm1JbwLOB7YpMbzN9hND/rIiIiIiIiICqBK1TrzD9s3lZ6HthySdM6KRbZr+xvYMoAacUt4Lvg2wyPbewALg+FL3DODwUn5kQx9TgQ8A+wBnAWtsvwG4Fej39PjiG8AptvdrKj+B6o8A00tcDwGzgV/anm77f5R6bwBOpVqt8Gpgf0lbApcDHytxHkr1x4M/IWmWpLqk+vo1q9t8RREREREREdGo08T7sH7K/nI4A3mBOEXSMmAR1cz3bsA6YG55vgToKdcLgTmSjqea4e5zk+0nbP8WWA1cW8p7G9r+iXKY3WTbN5eixoPtbgU+IenjwKtsPy9xLm6z/ZDtDcDSMtbuwMO2bwew/bjtZ5sb2r7Ids12bdyESQN0HxEREREREf1pmXhLOlFSL7C7pOUNPw8AyzdOiJsGSQdTzQjvV2aHf0615PwZ233739dTlu/bPgH4FFWCvrTMjkO1nLvPhob7DQy89F88t8f+T9j+DtWM+lPADZIOGaCPxnH74hyw34iIiIiIiBge7fZ4fwf4IfB5quXLfZ4YaC/yGDYJ+C/bayTtAfxFq8qSdrW9GFgs6Z1UCfig2P69pNWSDrB9C3BswzivBu63fUG53gtYBmzbQdf3AK+Q9Cbbt0vaFniqv1nvPtOmTKKeE8sjIiIiIiI61nLG2/Zq2yttv9/2r6hmVQ1MlPTKjRLhpuN6YAtJy6kOL1vUpv65knolraDa+71siOMfB3xZ0q386T7sY4AV5SC1PYBv2n4MWChphaRzB+rQ9rrS/ktlCf2PqWbxIyIiIiIiYpjouVXSLSpVM7ZfBF4BPAK8Crjb9p4jG15samq1muv1+miHERERERERMSokLbFd66ZNp4erfY5qafW9tncB3kZ1eFhEREREREREtNBp4v1MWb78Ikkvsn0TMH0E49psSfqypKVNP8eNdlwRERERERExOO0OV+vze0kTgZ8C35b0CDDgAVwxeLZPGu0YIiIiIiIiYvh0OuP9LmANcCrVIWO/BN45UkFFREREREREjBUdzXjb/oOkVwG72b5U0gRg3MiGtvmQ1APMtT11FMd/c3kneEu9q1bTM3te2z5X5pVjERERERERQIcz3pKOB64AvlaKpgBXj1RQsdH1AB8Y7SAiIiIiIiLGok6Xmp8E7A88DmD7PuDlIxXUZmqcpIsl3SnpR5LGS5ov6TxJCyTdLelNkr4v6T5Jn2vVmaQPSVouaZmkb5WyOZIukPQzSfdLel+pfjZwYDnI7bSR/qARERERERGbk04PV1tre50kACRtAbR/AXh0Yzfg/baPl/S/gPeW8nW2D5L0MeAHwAzgd8AvJZ1XTpv/E5L2BD4J7G/7UUnbNzzeCTgA2AO4hmolw2zgdNtH9BeYpFnALIBxL9lhGD5qRERERETE5qPTGe+bJX0CGC/pMOB7wLUjF9Zm6QHbS8v1Eqrl31AlxwC9wJ22H7a9Frgf2HmAvg4BrrD9KIDt3zU8u9r2Btt3ATt2Epjti2zXbNfGTZjU+SeKiIiIiIiIjhPv2cBvqZK//we4DvjUSAW1mVrbcL2e51Yj9JVvaKqzgYFXLIiBVySsbaoXERERERERI6jlUnNJr7T9f2xvAC4uP7HpuxG4qm8puqTtm2a9mz0BbNtJx9OmTKKeE8sjIiIiIiI61m7G+48nl0u6coRjiWFi+07gLKotAsuAL7Zpshx4thzElsPVIiIiIiIihpHsgc9Ik/Rz229ovo7NV61Wc71eH+0wIiIiIiIiRoWkJbZr3bRpN+PtAa4jIiIiIiIiogPtXie2t6THqQ7hGl+uKfe2/ZIRjS5akvRSqv3czd7W32vGIiIiIiIiYuNrmXjbHrexAonuleR6+mjHEREREREREQPr9HViERERERERETEI7ZaaxwAk9QBzbU9tKp8PnG673lQ+E6jZPnkjhdiWpFcB3wfGAS8GvmT7q63a9K5aTc/seW37XplXjkVERERERABJvDd3DwNvtr1W0kRghaRrbP96tAOLiIiIiIgYK7LUfGi2kHSppOWSrpA0ofGhpOMk3SvpZmD/hvI5ki6Q9DNJ90t6Xyl/kaSvSLpT0lxJ1/U964+klZJeVq5rZbYdSW+RtLT8/FzStv21t73O9tpyuxX5/xARERERETHskmgNze7ARbb3Ah4HPtr3QNJOwGeoEu7DgNc3td0JOAA4Aji7lL0H6AGmAR8B9htkXKcDJ9meDhwIPDVQRUk7S1oOPAic099st6RZkuqS6uvXrB5kSBEREREREZunJN5D86DtheX6MqpEus++wHzbv7W9Dri8qe3VtjfYvgvYsZQdAHyvlP8ncNMg41oIfFHSKcBk288OVNH2g+UPB68BPixpx37qXGS7Zrs2bsKkQYYUERERERGxeUriPTTu8r7R2oZrNf3u1LM892+49R8Htc+mmjEfDyyStEe7jspM951UM+QRERERERExTHK42tC8UtJ+tm8F3g/cAryzPFsMnC/ppVTL0I8GlrXp7xaqWedLgR2Ag4HvtKi/EpgB/BB4b1+hpF1t9wK9kvYD9gDuaW4s6c+Bx2w/JWk7qmXxX2wV4LQpk6jnxPKIiIiIiIiOZcZ7aO6mSpSXA9sDF/Y9sP0wcCZwK/AT4I4O+rsSeAhYAXyNKnlvtan6M1TJ/U+B9Q3lp0paIWkZ1f7uHw7Q/nXA4lLvZuALJWGPiIiIiIiIYSK71Wro2NgkTbT9ZJkpvw3Yv+z33iTUajXX6/X2FSMiIiIiIsYgSUts17ppk6Xmm565kiYDWwKf3ZSS7oiIiIiIiOheEu9NjO2Dm8skXQXs0lT8cds3dNKnpGnAt5qK19red1BBRkRERERERMeSeL8A2D5qiO17genDFE5ERERERER0IYl3dKV31Wp6Zs9rW29lTj6PiIiIiIgAxtip5pImS/pouT5Y0txh7n+6pHc03M+U9K9D6WOQccyXNOBm/hLXK4YyRkRERERERAyPMZV4A5OBj45Ex5K2oFquPaSkuVUfZYzhMBNI4h0REREREbEJGGtLzc8GdpW0FHgGeKocTLY7sAD4qO0Nkt4O/E9gHPCo7bf115mkM6kS2B7gUeAAYLykA4DPtwtG0tHAp6nesb0aOBT4x6Y+Xtc0xgf66Wc88A3g9VTvDh9fyscB/wbUAAOXAA+W+29LegrYr7S5FHgn8GLgaNv3SJoIfKmh/WdsX9nuc0VERERERETnxlriPRuYanu6pIOB66mS1V+V6/dIuhm4GDjI9gOStm/T5wzgANtPSZoJ1GyfDNWS7jZtzwAOt71K0mTb6ySd0dTHmY1jDNDPicAa23tJ2gu4o5RPB6bYnlr6mmz795JOBk63XS/lUP2B4Y1lKf7pwEeAfwBW255W6m3X3+CSZgGzAMa9ZIc2HzkiIiIiIiIajbWl5s1us32/7fXAv1PNWP8FsMD2AwC2f9emj2taJMTtLATmSDqeanZ9sGMcBFwGYHs5sLyU3w+8WtKXyiz+4y36+H75vYRqdh2qGfgv91Ww/V/9NbR9ke2a7dq4CZNaDBERERERERHNxnri7X7u1U95K38Y9OD2CcCngJ2BpZJeOoQxnhdzSZT3BuYDJwFfb9F+bfm9nudWOnT7XURERERERESXxtpS8yeAbRvu95G0C9VS82OAi4BbgS9L2qVvqXkHs94D9d+SpF1tLwYWS3onVQLeVR/FAuBY4CZJU4G9Sv8vA9bZvlLSL4E5Xcb5I+Bk4NTS33YDzXr3mTZlEvW8KiwiIiIiIqJjY2rG2/ZjwEJJK4BzqZLss4EVwAPAVbZ/S7Vf+fuSlgGXdzHETcDrJS2VdEwH9c+V1FviWQAsG0QfABcCEyUtB/4OuK2UTwHml8Pk5gB/X8rnAF8tY4xv0e/ngO0krSjfxVs7jCciIiIiIiI6JDsrjaNztVrN9Xp9tMOIiIiIiIgYFZKW2K5102ZMzXhHREREREREbGrG2h7vQZF0HPCxpuKFtk/qsP0ngaObir9n+6wu4zgcOKep+AHbR3XTT0RERERERGw6stQ8upKl5hERERERsTkbzFLzzHiPUZKuB3ai+jf+KXBSeZ95Yx0B5wPvANYAM23f0arf3lWr6Zk9r+34K3PyeUREREREBJA93mPZf7O9NzAV2IHnL4UH+Etgt/Izi+r09IiIiIiIiBhGSbwHSdI2kuZJWlZex3WMpBmSbpa0RNINknYqdY+XdHupe6WkCaX86L5XeUlaUMq2lvSN8hqyn0t6aymfKen7kq6XdJ+kf2oVn+3Hy+UWwJZAf3sK3gV805VFwOS+mCMiIiIiImJ4JPEevLcDv7a9t+2pwPXAl4D32Z4BXAL0Ha72fdtvKjPQdwN/W8rPAA4v5UeWspMAbE8D3g9cKmnr8mw6cAwwDThG0s6tApR0A/AI8ARwRT9VpgAPNtw/VMqa+5klqS6pvn7N6lZDRkRERERERJMk3oPXCxwq6RxJBwI7Uy3r/rGkpcCngD8vdadK+qmkXuBYYM9SvhCYI+l4YFwpOwD4FoDte4BfAa8tz260vdr208BdwKtaBWj7cKp93lsBh/RTRf0166efi2zXbNfGTZjUasiIiIiIiIhoksPVBsn2vZJmUB1M9nngx8Cdtvfrp/oc4N22l0maCRxc+jhB0r7AXwFLJU2n/2S4z9qG6/V08O9n+2lJ11AtK/9x0+OHqP5g0OfPgV+36zMiIiIiIiI6lxnvQZL0CmCN7cuALwD7AjtI2q88f7GkvpntbYGHJb2Yasa7r49dbS+2fQbwKFUSvKCvjqTXAq8EftFlbBMb9pdvQfXHgXv6qXoN8CFV/gJYbfvhbsaKiIiIiIiI1jLjPXjTgHMlbQCeAU4EngUukDSJ6rv9F+BO4B+AxVTLxnupEnFK+92oZrlvBJZRJchfLcvSn6V6xdfa6s1fHdsGuEbSVlRL2P838FUASScA2P4qcB1VUv4fVK8TO67th54yiXpeFRYREREREdEx2f0ddh3Rv1qt5nq9PtphREREREREjApJS2zXummTpeYRERERERERIyhLzV/gJC2mOrW80Qdt945GPBEREREREfGnkni/wNned7RjiIiIiIiIiIFlqXlERERERETECMqM9yBJ6gHm2p7aVD4fON12val8JlCzffJGCrEjktZTnbQO8H9sH9mqfu+q1fTMnteyz5U59TwiIiIiIuKPknjHU7anj3YQERERERERY1WWmg/NFpIulbRc0hWSJjQ+lHScpHsl3Qzs31A+R9IFkn4m6X5J7yvlL5L0FUl3Spor6bq+Z/2RtFLSy8p1rcy2I+ktkpaWn59L2nagPiIiIiIiImJkJfEemt2Bi2zvBTwOfLTvgaSdgM9QJdyHAa9varsTcABwBHB2KXsP0ANMAz4C7DfIuE4HTioz2QcCT7Wou7WkuqRFkt7dXwVJs0qd+vo1qwcZUkRERERExOYpiffQPGh7Ybm+jCqR7rMvMN/2b22vAy5vanu17Q227wJ2LGUHAN8r5f8J3DTIuBYCX5R0CjDZ9rMt6r6yvPz9A8C/SNq1uYLti2zXbNfGTZg0yJAiIiIiIiI2T0m8h8Zd3jda23Ctpt+depbn/g23/uOg9tlUM+bjgUWS9hioA9u/Lr/vB+YDb+gyhoiIiIiIiGghh6sNzSsl7Wf7VuD9wC3AO8uzxcD5kl5KtQz9aGBZm/5uAT4s6VJgB+Bg4Dst6q8EZgA/BN7bVyhpV9u9QK+k/YA9gHuaG0vaDlhje23ZK74/8E+tApw2ZRL1nFoeERERERHRscx4D83dVInycmB74MK+B7YfBs4EbgV+AtzRQX9XAg8BK4CvUSXvrTZVf4Yquf8psL6h/FRJKyQto9rf/cMB2r8OqJd6NwFnl6XvERERERERMUxkt1oNHRubpIm2nywz5bcB+5f93puEWq3mer3evmJERERERMQYJGlJOSerY1lqvumZK2kysCXw2U0p6Y6IiIiIiIjuJfHexNg+uLlM0lXALk3FH7d9Qyd9SpoGfKupeK3tfQcVZERERERERHQsifcLgO2jhti+F5g+TOFEREREREREF3K4WkRERERERMQI2iRmvCU9aXtiF/UPBk63fcTIRdXvuO8G7u07+VvSTOBHfe/C3hz0rlpNz+x5LeuszOvGIiIiIiIi/igz3t15N/D6hvuZwCtGJ5SIiIiIiIh4IdikEm9JB0uaL+kKSfdI+rYklWdvL2W3AO9p08+Zkk5vuF8hqUfSNpLmSVpWyo5p0cfZku6StFzSFyS9GTgSOFfSUkkfB2rAt8v9eEkrJX1G0h2SeiXt0SbGS8rnvV/SKaW8p3zOr5cYvy3pUEkLJd0naZ9u+yzPrpa0RNKdkmY1lD8p6azynSyStGOr7zYiIiIiIiK6s0kl3sUbgFOpZpZfDewvaWvgYuCdwIHAnw2y77cDv7a9t+2pwPX9VZK0PXAUsKftvYDP2f4ZcA3wP2xPt30OUAeOLfdPleaP2n4jcCFwen/9N9gDOBzYB/i0pBeX8tcA5wN7lTofAA4o/X1ikH3+je0ZVH8sOKW8JxxgG2CR7b2BBcDx/XwfsyTVJdXXr1ndZviIiIiIiIhotCkm3rfZfsj2BmAp0EOVTD5g+z7bBi4bZN+9wKGSzpF0oO2BssjHgaeBr0t6D7CmizG+X34voYq9lXm219p+FHgE6JttfsB2b/kO7gRuLJ+7dwh9niJpGbAI2BnYrZSvA+a2itn2RbZrtmvjJkxqM3xEREREREQ02hQT77UN1+t57gA4d9HHs/zpZ9sawPa9wAyqBPbzks7or7HtZ6lmjK+k2tfd78z4APrib4y9Xd3m+o3lGxruNwymz3IY3aHAfmVm++eU7wR4piT1ncYcERERERERXXihJFn3ALtI2tX2L4H3t6m/EjgCQNIbgV3K9SuA39m+TNKTVIejPY+kicAE29dJWgT8R3n0BLBtQ9Xm+03VJOC/bK8p+87/YrAdTZsyiXpOLY+IiIiIiOjYCyLxtv10ORBsnqRHgVuAqS2aXAl8SNJS4Hbg3lI+jepwtA3AM8CJA7TfFvhB2Vsu4LRS/l3g4nJo2fuAOcBXJT0F7DfYz7cRXA+cIGk58Auq5eYRERERERGxEei5VcYR7dVqNdfr9dEOIyIiIiIiYlRIWmK71k2bTXGPd0RERERERMSY8YJYaj4QSccBH2sqXmj7pC76uIqyB7zBx23fMNT4Sv9DjnFj9BkREREREREjI0vNoytZah4REREREZuzLDWPiIiIiIiI2MS8oJeab0okzQRqtk8eQh/zgdNtb7QpZUlnAR8CtrM9sV393lWr6Zk9r2WdlXndWERERERExB9lxnuQVBkL39+1wD6jHURERERERMRYlRnvLkjqAX4I3ET13u6rJR0LPEz1rvC1LdoeDXwaWA+stn2QpPHAN4DXA3cD49uM/yRwPnAE8BTwLtu/kTSn3O8BvAo4DvhwiXGx7ZkD9Wl7Uem75WePiIiIiIiIwRkLM7Yb2+7AN4F3AH8L7A8cRpU8t3IGcLjtvYEjS9mJwBrbewFnATPa9LENsKj0sQA4vuHZdsAhwGlUs9jnAXsC0yRN7+yj9U/SLEl1SfX1a1YPpauIiIiIiIjNThLv7v2qzBLvC8y3/Vvb64DL27RbCMyRdDwwrpQdBFwGYHs5sLxNH+uAueV6CdDT8OxaV0fU9wK/sd1rewNwZ1O9rtm+yHbNdm3chElD6SoiIiIiIuL/Z+/ew+Su6zTvv2+jAjGYDIoIUWmMKEoC0ZSwnASVXQ/jARAWhQcnjJhRQJS5GMmMDgvDMBuR0VFX0MhCGIEBCeCDCQIDD+EQIFCBJM0ZweySiDMq2oCRAMn9/PH7NlSKqupDutOd5H5dV67+1ff8K/jnU9/TZieB98D9seG533ex2f4C8HXgzcASSa8baBvA837p/rc1rLtVoHeZ+1rWXfK+lmwpiIiIiIiIGDEJyAZvEfCdEkA/BRwGLG1XWNIk24uARZI+ThWA3wwcCdwoaTKw2/APe/1MmTieek4tj4iIiIiI6LfMeA+S7SeAU4HbgeuBu/uo8k1J3ZLupQq4lwLnAOMkLQO+Ctw5fCNuTdKZklYAYyWtkHTqhh5DRERERETEpkwvrVyO6FutVnO9vsGuGY+IiIiIiBhVJC22XRtIncx4R0RERERERAyj7PEeYpK+RrXfu9Flts8YQBuLgC2ako+y3b0e4xryNiMiIiIiIqJvCbyHWAmw+x1kt2ljzyEazrC2GREREREREX1L4B0D0r2yh66Z8zuWWZ5TzyMiIiIiIl6UPd59kHSqpJMkTZe0wyDb2E/SfZKWSNpqAPUmSDq24fMBkuYNZgyl/kGS3jXY+hERERERETFwCbz7bzowqMCb6q7us2xPtf2nAdSbABzbZ6kmksa0yToISOAdERERERGxASXwbkHS1yQ9JOl64B0luQZc1GnWWtIHJd1T7us+T9IWko4B/jtwiqSL2tQbJ+kGSXeXup8sWbOASaXPb5a0cZLmSnpQ0kWSVNpYLukUSbcCh5c6vf/WSNof+ATVfeJLJE2StEDSNyTdKelhSfsNyRcYERERERERL8oe7yaSpgGfBt5N9f3cDSwG6sBJtlteYi1pS2AO8EHbD0v6V+CLtv9F0r7APNtz23T7LHCw7ackvR64Q9JVwExgsu2ppY8Dyrh2BX4FLAT2AW7tbcf2vuX54lLnOGB/2zeVNl8cR4nZX2l7D0kfBf4HcGCLd5sBzAAY89ptO35/ERERERERsa7MeL/cfsCVtlfZfgq4qp/13gH80vbD5fMFwPv6WVfAP0laBlwPTAS2a1P2TtsrbK8FlgBdDXmXrtOotA9wDPCXHfq+ovxd3NTWi2zPtl2zXRszdnwfrxIRERERERGNMuPdmgdRR+vR35HAtsA0289LWg5s2abs6obnNaz73/CPLw5G2h7438AnbD/Toe/e9prbioiIiIiIiCGQQOvlbgbmSJpF9f18HPgh8DSwdYd6DwJdkt5m+xfAUcBN/exzPPCfJeh+P7BjSe+rz5YkvQr4CXBywwz8oNtrNGXieOq5LiwiIiIiIqLfstS8ie27qZZsLwEuB24pWXOAH7Q7XM32s8DRwGWSuoG1wA/62e1FQE1SnWr2+8HS5u+AhZLubThcrT/2Bt4LnNZwwNoOwCXA35QD4CYNoL2IiIiIiIgYJNmDWVUdm6tareZ6veX5chEREREREZs8SYtt1wZSJzPeEREREREREcMoe7wHQdKVwE5NySfbvraPelOAHzclr7a951COLyIiIiIiIkaPBN6DYPvgQdbrBqYO8XAiIiIiIiJiFEvg3YakLmCe7clN6QuAk2zXm9KnAzXbx2+gIY6I7pU9dM2c3zZ/eU48j4iIiIiIWEf2eG/kJA36x5P1qRsRERERERH9k8C7s1dKukDSMklzJY1tzJR0tKSHJd0E7NOQPkfSdyXdJukxSYeW9FdIOlvSfZLmSbq6N68VSadIuqtcJzZbkkr6Akn/VPr9cpu6cyT9QNItZYwfK+nTJV0m6WfAdSXtq3Vc42EAACAASURBVJK6JS0t95dHRERERETEEMmMZ2fvAD5ne6Gk84BjezMkbQ+cBkwDeoAbgXsa6m4P7AvsAlwFzAUOAbqAKcAbgAeA8zr0/79s/0Pp78fAx4CflbwJtvfvY/xdwP7AJOBGSW8r6XsBu9l+UtJHgIOAPW2vkrRNcyOSZgAzAMa8dts+uoyIiIiIiIhGmfHu7HHbC8vzhVSBdK89gQW2f2P7OeDSpro/tb3W9v3AdiVtX+Cykv5rqmC9k/dLWiSpG/gAsGtDXnN/rfyk9PUI8BjVjwAA/277yfJ8IHC+7VUADekvsj3bds12bczY8f3oNiIiIiIiInplxrszD/Bzo9UNz2r62ydJWwJnUx3Y9rikU4EtG4r8sR/NtBtvY121KBcRERERERFDJDPenb1F0l7l+TPArQ15i4ADJL1O0quAw/rR3q3Ap8pe7+2AAzqU7Q2yfytpHNB2L3gHh5W+JgFvBR5qUeY64C9796+3WmoeERERERERg5cZ784eAP5C0g+BR4BzgI8D2H6izELfDjwB3A2M6aO9y4EPAvcCD1MF7z2tCtr+g6QfAd3AcuCuQYz/IeAmqqXuX7D9bDmfrbGfayRNBeqSngOuBv6uXYNTJo6nnivDIiIiIiIi+k12VhlvSJLG2X5G0uuAO4F9yn7voe5nDtU95HOHst1areZ6vd53wYiIiIiIiE2QpMW2awOpkxnvDW+epAnAq4HThyPojoiIiIiIiNEjgfcGZvuA5jRJVwI7NSWfbPvavtqT9DVevr/8MtvTBzvGiIiIiIiIGDoJvEcB2wevR90zgDOGcDgRERERERExhHKqeURERERERMQwyoz3RkbSM7bHDUO7XVSHsU3uVK57ZQ9dM+e3zV+eE88jIiIiIiLWkRnviIiIiIiIiGGUwHsDkfRVSSeU529L+v/K8wclXSjpGUlnSFoq6Q5J25X8nSTdLukuSaf30cf2km6WtETSvZL2K+nPSPpnSXdLukHStiV9WunvduC4Yf0CIiIiIiIiNlMJvDecm4H9ynMNGCfpVcC+wC3Aa4A7bO9eyn6+lP0OcI7t9wJ9XT12BHCt7anA7sCSkv4a4G7b7wFuAv5HST8fOMH2Xp0alTRDUl1Sfc2qnv69bURERERERAAJvDekxcA0SVsDq4HbqQLw/agC7+eAeQ1lu8rzPsC/lecf99HHXcDRkk4Fpth+uqSvBS4tzxcC+0oaD0ywfVNfbduebbtmuzZm7Pi+3jMiIiIiIiIaJPDeQGw/DywHjgZuowq23w9MAh4AnrftUnwN6x58Z/rB9s3A+4CVwI8lfbZdUUD9bTciIiIiIiIGL6eab1g3AycBfwl0A98CFtu2pHZ1FgKfppqpPrJT45J2BFba/pGk1wDvAf6V6geWQ4FLqJaj32r7D5J6JO1r+9a+2u41ZeJ46jm5PCIiIiIiot8y471h3QJsD9xu+z+AZ0taJ18GjpN0F9DXOu8DgCWS7gE+RbU/HOCPwK6SFgMfAP6hpB8NfL8crvanAb5LRERERERE9INeWt0cm6qhvPu7Vqu5Xq8PRVMREREREREbHUmLbdcGUicz3hERERERERHDKHu8N0KSpvDyU8hX296zVfmhmu2OiIiIiIiIgUvgvRGy3Q1MHelxRERERERERN+y1DwiIiIiIiJiGI2qGW9JXcA825Ob0hcAJ9muN6VPB2q2j99AQxw0SXOo3m3uAOv9G7ArcL7tb7fI7wL2tn3xIMe1gOqk9d5Tzf+b7f9sV757ZQ9dM+e3bW95rhqLiIiIiIhYx6gKvGNdkt5IFVTv2KFYF9Xd3IMKvIsjm3/UiIiIiIiIiKExGpeav1LSBZKWSZoraWxjpqSjJT0s6SZgn4b0OZK+K+k2SY9JOrSkv0LS2ZLukzRP0tW9ea1IWi7p9eW5VmaEkbS/pCXl3z2Stu7QxlcldUtaKmlWi/xZku4v73hWSTtM0r2lzs2l6HXAG0qf+0l6m6TrS5m7JU0CZgH7lTInSpou6QpJ10h6RNKZ/fvaIyIiIiIiYjiMxhnvdwCfs71Q0nnAsb0ZkrYHTgOmAT3AjcA9DXW3B/YFdgGuAuYCh1DNCk8B3gA8AJw3iHGdBBxXxjUOeLZVIUkfAQ4C9rS9StI2TfnbAAcDu9i2pAkl6xTgQ7ZXNqR9gmp5+tRSdxEwy/aVkrak+uFkJtUy/I+VMtOpDl57N7AaeEjS92w/3uHdzpe0Brgc+Ec3Xe4uaQYwA2DMa7ft42uKiIiIiIiIRqNxxvtx2wvL84VUgXSvPYEFtn9j+zng0qa6P7W91vb9wHYlbV/gspL+a6pgfTAWAt+SdAIwwfYLbcodSLUfexWA7Seb8p+iCtrPlXQIsKqh/TmSPg+MaW60zLBPtH1laffZ3j5auMF2j+1ngfuBTkvVj7Q9Bdiv/DuquYDt2bZrtmtjxo7v0FREREREREQ0G42Btwf4udHqhmc1/e2vF3jpe9nyxU7tWcAxwFbAHZJ2aVNfncZYAvY9qGaXDwKuKelfAL4OvBlYIul1Ldrtr8bvYQ0dVjbYXln+Pk21T3yPAfQTERERERERfRiNS83fImkv27cDnwFuBT5e8hYB3ylB6VPAYcDSPtq7FfgLSRcA2wIH0PkgsuVUS9l/DnyqN1HSpHJ/drekvaiWsz/Yov51wCmSLu5dat44612WqY+1fbWkO4BfNLS/CFgk6eNUAfgfeuvZfkrSCkkH2f6ppC2oZsafBtruN+9E0iupZu9/K+lVwMeA6zvVmTJxPPWcXB4REREREdFvo3HG+wGqQHkZsA1wTm+G7SeAU4HbqQLEu/vR3uXACuBe4IdUwXtPh/KnUQX3t1DNFvf6Su/hZ1RXb/28VWXb11DtL69LWkK1N7zR1sC88n43ASeW9G+WA9nuBW6m9Q8KRwEnlLq3AW8ElgEvlAPXTmxRp5MtgGtLe0uAlcCPBthGREREREREdKCmc7Q2SZLG2X6mzJTfCexT9nvHANVqNdfruXksIiIiIiI2T5IW264NpM5oXGo+HOaVk8JfDZyeoDsiIiIiIiI2lM0i8LZ9QHOapCuBnZqST7Z9bX/alDQF+HFT8mrbew5qkMOsXEW2RVPyUWXfekRERERERAyTzSLwbsX2wetZv5vqvuyNwmj9QSAiIiIiImJTt9kG3jE43St76Jo5v23+8px4HhERERERsY7ReKr5JkvSBEnHDlFbCyS13dAvabqkHYair4iIiIiIiBi8BN4b1gRgSALvfpgOJPCOiIiIiIgYYQm8h4ikz0paVu7T/rGk7SRdWT4vlbQ3MAuYJGmJpG9KulTSRxvamCPpU23a30rSJaWPS4GtSvqYUu/ecg/4iZIOBWrARaWvrSQtl3SapLtLuV1K/XGSzi9py9r1HxEREREREYOTPd5DQNKuwNeo7gf/raRtgHOAm2wfLGkMMA6YCUy2PbXUOxg4HLha0quBDwJfbNPNF4FVtneTtBtwd0mfCky0Pbm0OcH2HyQdD5xku17SAX5r+z1luftJwDHA3wM9tqeUcn/W4v1mADMAxrx228F/UREREREREZuhzHgPjQ8Ac23/FsD2kyXtnPJ5je2eFvV+DnxA0hbAR4Cbbf+pTR/vAy4s7S0DlpX0x4C3SvqepA8DT3UY5xXl72KgqzwfCHy/t4Dt3zdXsj3bds12bczY8R2aj4iIiIiIiGYJvIeGAA+0ku1ngQXAh6hmvi/pq0qLNn4P7F7aOQ44t0P91eXvGl5a7TCosUdERERERET/ZKn50LgBuFLSt23/riw1v4Fqefi/lKXmrwGeBrZuqnsJ1ZLvGtWBaO3cDBwJ3ChpMrAbgKTXA8/ZvlzSo8CcUr5VX61cBxwPfKW092etZr17TZk4nnquDIuIiIiIiOi3zHgPAdv3AWcAN0laCnwL+DLwfkndVEu7d7X9O2BhOQjtm6X6dVTLyK+3/VyHbs4BxklaBnwVuLOkTwQWSFpCFXT/bUmfA/yg93C1Du3+I/BnZUxLgfcP5N0jIiIiIiKiM9lZZRz9V6vVXK/XR3oYERERERERI0LSYtu1gdTJjHdERERERETEMMoe71FG0oeAbzQl/9L2wSMxnoiIiIiIiFg/CbxHGdvXAteO9DgiIiIiIiJiaCTwHiUkLQBOsr3BN1BLugp4q+3JfZXtXtlD18z5bfOX58TziIiIiIiIdWSP92ZO0iHAMyM9joiIiIiIiE1VAu/1JOn/kXRnubbrh5LGSHpG0jckLZZ0vaQ9JC2Q9JikT5R6W0m6RNIySZcCna78orR5hqSlku6QtF1JnyPpHEk3lvb3l3SepAckzemjzXHAX1NdKRYRERERERHDIIH3epD0TuBwYB/bU4E1wJHAa4AFtqcBT1MFtv8VOBj4h1L9i8Aq27tR3QE+rY/uXgPcYXt34Gbg8w15fwZ8ADgR+BnwbWBXYIqkqR3aPB34Z2BVH+85Q1JdUn3Nqp4+hhkRERERERGNEnivnw9SBcx3SVpSPr8VeA64ppTpBm6y/Xx57irp7wMuBLC9DFjWR1/PAfPK8+KGdgB+5upC9m7gP2x3214L3NdU7kUlIH+b7Sv7eknbs23XbNfGjB3fV/GIiIiIiIhokMPV1o+AC2z/7TqJ0kklEAZYC6wGsL1WUuN3bvrv+YY217Duf7vVzX01fG7333gvYJqk5aXMGyQtsH3AAMYUERERERERfciM9/q5AThU0hsAJG0jacd+1r2Zalk6kiYDuw3PEFuzfY7tHWx3AfsCDyfojoiIiIiIGHqZ8V4Ptu+X9HXgOkmvAJ4Hjutn9XOA8yUtA5YAdw7TMIfUlInjqefKsIiIiIiIiH7TS6uXI/pWq9Vcr2/wq8YjIiIiIiJGBUmLbdcGUidLzSMiIiIiIiKGUZaajzKSFgFbNCUfZbt7NLUZERERERER/ZPAe5SxvefG0GZERERERET0T5aaj1KSJkg6dpja7pJ0xHC0HREREREREevKjPfoNQE4Fjh7KBst94h3AUcAF7fKt/1Cu/rdK3vomjm/bfvLc+J5RERERETEOhJ4j16zgEmSllBdU7YK+A9gKnAF0A18GdgKOMj2o5LmAM8CuwLbAX9te56k6cCfA1sCrwHGAu8sbV8A/L4p/wMb6B0jIiIiIiI2eQm8R6+ZwGTbUyUdAPwUeCfwJPAYcK7tPSR9GfgS8JVSrwvYH5gE3CjpbSV9L2A320+W9k6y/TGAEpi/mL8B3i0iIiIiImKzkT3eG4+7bD9hezXwKHBdSe+mCrZ7/cT2WtuPUAXou5T0f+8jqG6bL2mGpLqk+ppVPev3FhEREREREZuZBN4bj9UNz2sbPq9l3ZULbqrX+/mPfbTfNt/2bNs127UxY8f3Z6wRERERERFRJPAevZ4Gth5EvcMkvULSJOCtwEND2HZEREREREQMUPZ4j1K2fydpoaR7gT9RHazWHw8BN1EdrvYF289Kai6zDHhB0lJgDtXhav0yZeJ46jm5PCIiIiIiot9kN69Mjo1VOdV8nu25w9VHrVZzvV4fruYjIiIiIiJGNUmLbdcGUidLzSMiIiIiIiKGUZaab0JsTx/pMURERERERMS6MuMdERERERERMYwSeEdEREREREQMowTeEREREREREcNoRPd4SzoB+CJwt+0j17OtLmBv2xeXz9OBmu3jB9nefsAPgOeBvWz/qUWZOZRTxCV9BZhte1WHNq8GjrD9hwGO5TDgVOCdwB626w15fwt8DlgDnGD72pL+YeA7wBjgXNuzBtJnO90re+iaOb9t/vJcNRYREREREbGOkZ7xPhb4aGPQLWmwPwZ0AUcMtJKkMW2yjgTOsj21VdDdwleAsZ0K2P7oQIPu4l7gEODmxkRJ7wI+DewKfBg4W9KY8k7fBz4CvAv4TCkbERERERERG9iIBd6SfgC8FbhKUo+k2ZKuA/61TfmrJe1Wnu+RdEp5Pl3SMcAsYD9JSySdWKrtIOkaSY9IOrOhrWck/YOkRcBeLfo6BvjvwCmSLippX5XULWmppFlN5U8AdgBulHRjh3deLun1krokPSDpR5Luk3SdpK3a1bP9gO2HWmR9ErjE9mrbvwR+AexR/v3C9mO2nwMuKWV7x/BPkm6XVJf0HknXSnpU0hfajSEiIiIiIiIGZ8QCb9tfAH4FvB/4NjAN+KTtdrPWN1MF1q8FXgD2Ken7ArcAM4Fbygz1t0veVOBwYApwuKQ3l/TXAPfa3tP2rS3Gdi5wFfA3to+U9BHgIGBP27sDZzaV/27vu9h+fz+/gp2B79veFfgD8Kl+1ms0EXi84fOKktYuvdfjtvei+t7mAIcC/wX4h1adSJpRgvT6mlU9gxhmRERERETE5mukl5o3uqqPJd23AO+jCrTnA+MkjQW62swGA9xgu8f2s8D9wI4lfQ1w+QDGdiBwfu/+bdtPDqBuO7+0vaQ8L6ZaKj9QapHmDum9rip/u4FFtp+2/RvgWUkTXlbRnm27Zrs2Zuz4QQwzIiIiIiJi8zWih6s1+WMf+XcBNeAx4N+B1wOfpwpa21nd8LyGl973WdtrBjA2sW7gOhSax9Z2qXkHK4A3N3x+E9XMOx3SG/te2zSOtYyu/yciIiIiIiI2ehtNkGX7OUmPU+29Ph3YFjir/AN4Gth6mLq/jmq/98W2V0napsWsd2//vx2mMbRyFXCxpG9R7THfGbiT6oeCnSXtBKykOoBtwAfPtTJl4njqObk8IiIiIiKi30bTUvP+uAX4j7Lk+xaqmdxbSt4y4IVy+NmJ7RoYDNvXUAW5dUlLgJNaFJsN/LzT4WqDJelgSSuoDoKbL+naMq77gJ9QLaO/BjjO9hrbLwDHA9cCDwA/KWUjIiIiIiJiA5M91CuoY1NWq9Vcr9f7LhgREREREbEJkrTYdm0gdTa2Ge+IiIiIiIiIjcqo2+Mt6UPAN5qSf2n74GHq70pgp6bkk21fux5tLgK2aEo+ynZ3H/W+z0vXpPX6ju3zBzuWiIiIiIiIGFmjLvAuAe+gg95B9DfkAb3tPQdZ77ihHktERERERESMrCw1j4iIiIiIiBhGo27GO15O0m229+5n2TnAPNtz+1H2Iqq70Z+nuobsr2w/36lO98oeumbOb5u/PFeNRURERERErCMz3huB/gbdg3ARsAswBdgKOGaY+omIiIiIiNhsJfDeCEh6RtIBkm6S9BNJD0uaJelISXdK6pY0qUW90yXNkdTyv7Ptq11QzXi/abjfJSIiIiIiYnOTwHvjsjvwZaoZ6qOAt9veAzgX+FJjQUlnAm8Ajra9tlOjkl5V2rumTf4MSXVJ9TWretb/LSIiIiIiIjYjCbw3LnfZfsL2auBR4LqS3g10NZT7e2CC7b8qs9l9ORu42fYtrTJtz7Zds10bM3b8egw/IiIiIiJi85PAe+OyuuF5bcPntax7UN5dwDRJ2/TVoKT/AWwL/PVQDTIiIiIiIiJeklPNN03XUN2FPl/Sf7P9dKtCko4BPgR8sK/l6L2mTBxPPSeXR0RERERE9FtmvDcO/Vkuvm4F+zLgR8BVkrZqU+wHwHbA7ZKWSDplPcYYERERERERLah/W4BjpEh6HXC37R1HeiwAtVrN9Xp9pIcRERERERExIiQttl0bSJ3MeI9iknYAbgfOGumxRERERERExOBkj/coZvtXwNvXtx1JVwI7NSWfbPva9W07IiIiIiIiOkvgvRmwffBIjyEiIiIiImJzlcA7BqR7ZQ9dM+e3zV+eE88jIiIiIiLWkT3eG4ikCZKOLc87SJo7jH19QVJ3Oan8VknvalPuw5IekvQLSTOHazwRERERERGbswTeG84E4Fio9m7bPnQY+7rY9hTbU4EzgW81F5A0Bvg+8BHgXcBn2gXoERERERERMXhZar7hzAImSVoCPAK80/ZkSdOBg4AxwGTgn4FXA0cBq4GP2n5S0iSqQHlbYBXwedsPturI9lMNH19D63vA9wB+YfsxAEmXAJ8E7l/fF42IiIiIiIiXZMZ7w5kJPFpmof+mKW8ycARVMHwGsMr2u6muEvtsKTMb+JLtacBJwNmdOpN0nKRHqWa8T2hRZCLweMPnFSWtVVszJNUl1des6unUbURERERERDRJ4D063Gj7adu/AXqAn5X0bqBL0jhgb+CyMmP+Q2D7Tg3a/r7tScDJwNdbFFGram3amm27Zrs2Zuz4/r1RREREREREAFlqPlqsbnhe2/B5LdV/o1cAfyiz5QN1CXBOi/QVwJsbPr8J+NUg2o+IiIiIiIgOEnhvOE8DWw+mou2nJP1S0mG2L5MkYDfbS1uVl7Sz7UfKxz+n2lPe7C5gZ0k7ASuBT1Mtd+9oysTx1HNlWERERERERL8l8N5AbP9O0kJJ9wIPDKKJI4FzJH0deBXVTHbLwBs4XtKBwPPA74G/gOoaM+Bc2x+1/YKk44FrqQ52O8/2fYMYV0RERERERHQgu+W23oiWarWa6/X6SA8jIiIiIiJiREhabLs2kDo5XC0iIiIiIiJiGGWp+UZM0teAw5qSL7N9xkiMJyIiIiIiIl4ugfdGrATYCbIjIiIiIiJGsQTemyhJZwCfBf7M9rgO5f4W+BywBjjB9rWd2u1e2UPXzPlt85fnxPOIiIiIiIh1ZI/3putnwB6dCkh6F9U1YrsCHwbOljRmA4wtIiIiIiJis5HAe5AkvUbSfElLJd0r6XBJ0yTdJGmxpGslbV/Kfl7SXaXs5ZLGlvTDSt2lkm4uaVtKOl9St6R7JL2/pE+XdIWkayQ9IunMTuOzfYftJ/p4jU8Cl9hebfuXwC/oI1iPiIiIiIiIgUngPXgfBn5le3fbk4FrgO8Bh9qeBpzHS/uvr7D9Xtu7U93h/bmSfgrwoZL+iZJ2HIDtKcBngAskbVnypgKHA1OAwyW9eT3fYSLweMPnFSVtHZJmSKpLqq9Z1bOeXUZERERERGxessd78LqBsyR9A5gH/B6YDPy7JIAxQO+M82RJ/whMAMYBvfuoFwJzJP0EuKKk7UsVwGP7QUn/B3h7ybvBdg+ApPuBHVk3cB4otUh72cXutmcDswG22H7nXPweERERERExAAm8B8n2w5KmAR8F/ifw78B9tvdqUXwOcJDtpZKmAweUNr4gaU/gz4ElkqbSOhjutbrheQ3r/99vBdA4a/4m4Ffr2WZEREREREQ0yFLzQZK0A7DK9oXAWcCewLaS9ir5r5K0aym+NfCEpFcBRza0Mcn2ItunAL+lCoJv7i0j6e3AW4CHhuk1rgI+LWkLSTsBOwN3DlNfERERERERm6XMeA/eFOCbktYCzwNfBF4AvitpPNV3+y/AfcDfA4uA/0O1RH3r0sY3Je1MNct9A7AUeBD4gaTu0t5026vL8vV+K4evHQGMlbQCONf2qZI+AdRsn2L7vrLM/f7S13G213R86YnjqefKsIiIiIiIiH6TnS270X+1Ws31en2khxERERERETEiJC22XRtInSw1j4iIiIiIiBhGWWq+kZO0CNiiKfko290jMZ6IiIiIiIhYVwLvjZztPUd6DBEREREREdFelppHREREREREDKONcsZb0jO2xw2g/AHASbY/NnyjatnvQcDDtu8vn6cD19keFXdlSzoSOLl8fAb4ou2lnep0r+yha+b8tvnLc+J5RERERETEOjLjPbwOAt7V8Hk6sMPIDKWlXwL7294NOB2YPcLjiYiIiIiI2ORs1IG3pAMkLZA0V9KDki5SufBa0odL2q3AIX20c6qkkxo+3yupS9JrJM2XtLSkHd6hjVmS7pe0TNJZkvYGPkF1V/cSSScDNeCi8nkrScslnSbpbkndknbpY4znlfd9TNIJJb2rvOe5ZYwXSTpQ0kJJj0jao12btm+z/fvy8Q7gTZ2+p4iIiIiIiBi4jXKpeZN3A7sCvwIWAvtIqgM/Aj4A/AK4dJBtfxj4le0/B5A0vlUhSdsABwO72LakCbb/IOkqYJ7tuaXcR6iWvNfLZ4Df2n6PpGOBk4BjOoxnF+D9wNbAQ5LOKelvAw4DZgB3AUcA+1IF/n9HNfPel88BP2/zfjNK24x57bb9aCoiIiIiIiJ6bdQz3sWdtlfYXgssAbqoAtRf2n7EtoELB9l2N3CgpG9I2s92T5tyTwHPAudKOgRYNYA+rih/F1ONvZP5tlfb/i3wn8B2Jf2XtrvLd3AfcEN57+5+tImk91MF3ie3yrc923bNdm3M2Ja/PUREREREREQbm0LgvbrheQ0vzeJ7AG28wLrfxZYAth8GplEFsP9T0imtKtt+AdgDuJxqdvmaAfTdO/7GsfdVtrl8Y/rahs9r+2pT0m7AucAnbf+uPwOOiIiIiIiI/tsUlpq38iCwk6RJth8FPtNH+eXAxwAkvQfYqTzvADxp+0JJz1AdjvYyksYBY21fLekOquXtAE9TLQunzecRJektVDPuR5UfGfo0ZeJ46jm5PCIiIiIiot82ycDb9rNlX/J8Sb8FbgUmd6hyOfBZSUuo9kj3BqFTqA5HWws8D3yxTf2tgf9X0paAgBNL+iXAj8pBaIcCc4AfSPoTsNdg328InQK8Dji77Dd/wXZtZIcUERERERGxaVG1FTiif2q1muv1+kgPIyIiIiIiYkRIWjzQCctNYY93RERERERExKi1SS41b0fS0cCXm5IX2j5uAG1cSdkD3uBk29eu7/hK++s9xg3RZkRERERERPRPlprHgGSpeUREREREbM6y1DwiIiIiIiJilBlVS80ldQHzbE9uSl8AnGS73pQ+HajZPn4DDXHQJM2here5A6z3b8CuwPm2v90ivwvY2/bF6zm+q4C3Nn/3zbpX9tA1c37LvOW5ZiwiIiIiIuJlRlXgHeuS9EaqoHrHDsW6gCOAQQfekg4Bnhls/YiIiIiIiGhvNC41f6WkCyQtkzRX0tjGTElHS3pY0k3APg3pcyR9V9Jtkh6TdGhJf4WksyXdJ2mepKt781qRm0pKIgAAIABJREFUtFzS68tzrcy2I2l/SUvKv3skbd2hja9K6pa0VNKsFvmzJN1f3vGsknaYpHtLnZtL0euAN5Q+95P0NknXlzJ3S5oEzAL2K2VOlDRd0hWSrpH0iKQzO33ZksYBfw38Y6dyERERERERMTijccb7HcDnbC+UdB5wbG+GpO2B04BpQA9wI3BPQ93tgX2BXYCrgLnAIVSzwlOANwAPAOcNYlwnAceVcY0Dnm1VSNJHgIOAPW2vkrRNU/42wMHALrYtaULJOgX4kO2VDWmfoFqePrXUXQTMsn2lpC2pfjiZSbUM/2OlzHRgKvBuYDXwkKTv2X68zXudDvwzsKrdi0uaAcwAGPPabdsVi4iIiIiIiBZG44z347YXlucLqQLpXnsCC2z/xvZzwKVNdX9qe63t+4HtStq+wGUl/ddUwfpgLAS+JekEYILtF9qUO5BqP/YqANtPNuU/RRW0n1uWePcGvAuBOZI+D4xpbrTMsE+0fWVp99nePlq4wXaP7WeB+4GWS9UlTQXe1ttmO7Zn267Zro0ZO75T0YiIiIiIiGgyGgPv5vvN+vrcaHXDs5r+9tcLvPS9bPlip/Ys4BhgK+AOSbu0qa9OYywB+x7A5VQz49eU9C8AXwfeDCyR9LoW7fZX4/ewhvYrG/YCpklaDtwKvL13aX1EREREREQMjdG41PwtkvayfTvwGaqA8OMlbxHwnRKUPgUcBizto71bgb+QdAGwLXAAnQ8iW061lP3nwKd6EyVNst0NdEvai2o5+4Mt6l8HnCLp4t6l5o2z3mWZ+ljbV0u6A/hFQ/uLgEWSPk4VgP+ht57tpyStkHSQ7Z9K2oJqZvxpoO1+805snwOcU/rvolrWfkCnOlMmjqee08sjIiIiIiL6bTTOeD9AFSgvA7ahBIYAtp8ATgVuB64H7u5He5cDK4B7gR9SBe89HcqfRhXc30I1W9zrK72HnwF/ogrMX8b2NVT7y+uSllDtDW+0NTCvvN9NwIkl/ZvlQLZ7gZtp/YPCUcAJpe5twBuBZcAL5cC1E1vUiYiIiIiIiBEku9PK7U2DpHG2nykz5XcC+5T93jFAtVrN9Xq974IRERERERGbIEmLbdcGUmc0LjUfDvPKSeGvBk5P0B0REREREREbymYReLfatyzpSmCnpuSTbV/bnzYlTQF+3JS82vaegxrkMCtXkW3RlHxU2bceERERERERw2SzCLxbsX3wetbvprove6MwWn8QiIiIiIiI2NSNxsPVIiIiIiIiIjYZm+2M94ZW9pgfYftsSTsA37V96DD19T7gX4DdgE/bntum3DRgDtXd5FcDX3Yfp+11r+yha+b8lnnLc81YRERERETEy2TGe8OZABwLYPtXwxV0F/8XmE7n+8qhuqptBrBz+ffhYRxTRERERETEZikz3hvOLGBSudv7EeCdtidLmg4cBIwBJgP/THX6+lHAauCjtp+UNAn4PrAtsAr4vO0HW3VkezmApLXtBiNpe+C1tm8vn/+1jKPl/eQRERERERExOJnx3nBmAo/angr8TVPeZOAIYA/gDGCV7XcDtwOfLWVmA1+yPQ04CTh7PcczEVjR8HlFSXsZSTMk1SXV16zqWc9uIyIiIiIiNi+Z8R4dbrT9NPC0pB7gZyW9G9hN0jhgb+AySb11mq8GGyi1SGu5v9v2bKrAny2237njHvCIiIiIiIhYVwLv0WF1w/Pahs9rqf4bvQL4Q5ktHyorgDc1fH4T8KshbD8iIiIiIiJI4L0hPQ1sPZiKtp+S9EtJh9m+TNW09262lw52MLafkPS0pP8CLKJa0v69vupNmTieek4vj4iIiIiI6Lfs8d5AbP8OWCjpXuCbg2jiSOBzkpYC9wGfbFdQ0nslrQAOA34o6b6GvCUNRb8InAv8AniUHKwWEREREREx5NTHtc0R66jVaq7X6yM9jIiIiIiIiBEhabHt2kDqZMY7IiIiIiIiYhhlj/dGTNLXqJaTN7rM9hkjMZ6IiIiIiIh4uQTeG7ESYCfIjoiIiIiIGMUSeMeAdK/soWvm/JZ5y3PaeURERERExMuMqj3ekrrKqd/N6QskvWzzuqTpkv7Xhhnd+pE0R9Khg6j3b5KWSTqxTX6XpCMGOaaxkuZLelDSfZJmDaadiIiIiIiIaG9UBd6xLklvBPa2vZvtb7cp1gUMKvAuzrK9C/BuYB9JH1mPtiIiIiIiIqLJaAy8XynpgjLLO1fS2MZMSUdLeljSTcA+DelzJH1X0m2SHuudXZb0CklnlxndeZKu7jTzLGm5pNeX55qkBeV5f0lLyr97JG3doY2vSuqWtLTVLLKkWZLuL+94Vkk7TNK9pc7Npeh1wBtKn/tJepuk60uZuyVNAmYB+5UyJ5ZVAFdIukbSI5LObDdO26ts31ienwPuBt7UrnxEREREREQM3Gjc4/0O4HO2F0o6Dzi2N0PS9sBpwDSgB7gRuKeh7vbAvsAuwFXAXOAQqlnhKcAbgAeA8wYxrpOA48q4xgHPtipUZowPAva0vUrSNk352wAHA7vYtqQJJesU4EO2VzakfQKYZ3tqqbsImGX7SklbUv1wMhM4yfbHSpnpwFSqGezVwEOSvmf78U4vV/r8OPCdFnkzgBkAY167badmIiIiIiIioslonPF+3PbC8nwhVSDda09gge3flBnaS5vq/tT2Wtv3A9uVtH2prthaa/vXVMH6YCwEviXpBGCC7RfalDsQON/2KgDbTzblP0UVtJ8r6RBgVUP7cyR9HhjT3GiZYZ9o+8rS7rO9fbRwg+0e288C9wM7dnoxSa8E/g34ru3HmvNtz7Zds10bM3Z8p6YiIiIiIiKiyWgMvD3Az41WNzyr6W9/vcBL38uWL3ZqzwKOAbYC7pC0S5v66jTGErDvAVxONTN+TUn/AvB14M3AEkmva9FufzV+D2voe2XDbOAR2/8ygD4iIiIiIiKiH0bjUvO3SNrL9u3AZ4BbqZZAAywCvlOC0qeAw4ClfbR3K/AXki4AtgUOAC7uUH451VL2nwOf6k2UNMl2N9AtaS+q5ewPtqh/HXCKpIt7l5o3znqXZepjbV8t6Q7gFw3tLwIWSfo4VQD+h956tp+StELSQbZ/KmkLqpnxp4G2+837IukfgfFUPyr0acrE8dRzbVhERERERES/jcYZ7weoAuVlwDbAOb0Ztp8ATgVuB66nOgysL5cDK4B7gR9SBe89HcqfRhXc30I1W9zrK72HnwF/ogrMX8b2NVT7y+uSllDtDW+0NTCvvN9NQO81Yd8sB7LdC9xM6x8UjgJOKHVvA94ILANeKAeutbxyrB1JbwK+BrwLuLsc0NavADwiIiIiIiL6R3anldubBknjbD9TZsrvBPYp+71jgGq1muv1+kgPIyIiIiIiYkRIWmy7NpA6o3Gp+XCYV07tfjVweoLuiIiIiIiI2FA2i8Db9gHNaZKuBHZqSj7Z9rX9aVPSFODHTcmrbe85qEEOs3IV2RZNyUeVfesRERERERExTDaLwLsV2wevZ/1uqvuyNwqj9QeBiIiIiIiITd1mG3hvbCTdZnvvfpadA8yzPbcfZf83UKO6ruxhYLrtZ9qV717ZQ9fM+S3zlue084iIiIiIiJcZjaeaRwv9DboH4UTbu9veDfi/wPHD1E9ERERERMRmKYH3RkLSM5IOkHSTpJ9IeljSLElHSrqzXEU2qUW90yXNkdTyv7Xtp0o5AVsBm/4x9xERERERERtQAu+Nz+7Al4EpVPd6v932HsC5wJcaC0o6E3gDcLTtte0alHQ+8GtgF+B7LfJnSKpLqq9Z1ekK9IiIiIiIiGiWwHvjc5ftJ2yvBh4Frivp3UBXQ7m/BybY/iv3cVm77aOBHYAHgMNb5M+2XbNdGzN2/FC8Q0RERERExGYjgffGZ3XD89qGz2tZ97C8u4BpkrbpT6O21wCXAp8aikFGREREREREJYH3pusaYBYwX9LWrQqo8rbeZ+DjwIMbbogRERERERGbvlwntvEY8KFnti8rQfdVkj5q+09NRQRcIOm15Xkp8MVObU6ZOJ56rg2LiIiIiIjoN/Wx/TdGAUmvA+62veNIj6VWq7ler4/0MCIiIiIiIkaEpMW2awOpk6Xmo5ykHYDbgbNGeiwRERERERExcFlqPsrZ/hXw9vVtR9KVwE5NySfbvnZ9246IiIiIiIj2EnhvJmwfPNJjiIiIiIiI2BxlqXlERERERETEMNroZrwldQHzbE9uSl8AnGS73pQ+HajZPn4DDfFlJP2d7X/qo8xttvceRNtzgP2BnpI03faScj3Yd4CPAqtK+t0Dbb9Z98oeumbOb5m3PKedR0REREREvExmvDeMv+urwGCC7gZ/Y3tq+bekpH0E2Ln8mwGcsx7tR0RERERExCBtrIH3KyVdIGmZpLmSxjZmSjpa0sOSbgL2aUifI+m7km6T9JikQ0v6KySdLek+SfMkXd2b14qk95Y2lkq6U9LWkqZLukLSNZIekXRmKTsL2ErSEkkXdWjzmfL3AEkLyns9KOmiMns9UJ8E/tWVO4AJkrYv7d8k6SflO5ol6cjyHt2SJg2ir4iIiIiIiGhjYw283wHMtr0b8BRwbG+GpO2B06gC7v8KvKup7vbAvsDHgFkl7RCgC5gCHAPs1a5jSa8GLgW+bHt34EDgTyV7KnB4aedwSW+2PRP4U5mNPrKf7/du4Ctl7G+l4ceDNs4oP0J8W9IWJW0i8HhDmRUlDWB34MtlnEcBb7e9B3Au8KUW7zxDUl1Sfc2qnubsiIiIiIiI6GBjDbwft72wPF9IFUj32hNYYPs3tp+jCpIb/dT2Wtv3A9uVtH2By0r6r4EbO/T9DuAJ23cB2H7K9gsl7wbbPbafBe4Hdhzk+91pe4XttcASqh8F2vlbYBfgvcA2wMklvdUsucvfu2w/YXs18Cjw/7N379F2lfX979+fRuT+C4qRIgKhFKRCJJhlqKgURcV6hQoHlfoTjke8YLV2UKU/q8UqiujvUPHa4MHoUauiYBFawCI3uQRWMLC5CQrhlMsQxBpBJGD29/yxZsrKzr6sfcvKzn6/xsjYcz3zeb7zu9aeY8F3P8+c88KmfWC4Y1XVkqpqVVVrzlZzx/teJEmSJGlWm6mFd43zdbfVXdsZ8rMXGSV+d+w1TPzmdT3HaQroaororwCLm113Azt3dX0mcO8w8Qe7Xg9OImdJkiRJ0jBmapG1S5LnV9VVwBuBHwOvafYtAz6TZHs6y9CPAK4fI96Pgbck+SowDzgI+OYIfW8FnpHkeVV1bZJteWKp+UgeT7JZVT0+1hsbryQ7VtV9zXXghwI3NrvOAd6d5Ft0VgGsavo9azLHW7DTXNrevVySJEmSejZTC+9b6BTK/wzcTueO3a+BzgxwkhOBq4D7gOuAOWPE+x5wMJ2i9TY6xfuwFzNX1WNJjgQ+m2RLOkX3S8eIvwS4Icl147jOu1ffSDKPzkz8CuAdTfu/0XmU2M/oPE7smCk+riRJkiSpB6kabVX27JFkm6p6uJkpvwZ4QXO9t7q0Wq1qt9tjd5QkSZKkTVCS5VXVGs+YmTrjPR3OTbId8GTgoxbdkiRJkqSpYOHdqKqDhrYlORvYbUjzB6rqgokco5lNv2iYXQdX1YNjjJ3SXCRJkiRJG4aF9yiq6rApjvcgnWd99z0XSZIkSdKGMVMfJyZJkiRJ0ozgjPdGJMnDVbVNj32XAudW1Xd77D8fOKCqRnpMWk8G7lnF/BPOG3bfSh8zJkmSJEnrccZ7E5NkpEenzQfetAFTkSRJkiThjPeUSPJ+4NGqOi3JqcC+VfWSJAfTeX72ocBngFfTee7366rqF0l2A75J5/dw/hjHCPBZ4CXAnXSe271230rgDODlwOeStIEvAfOANcARwMnAnyRZAXwV+C/gtcBWwO7A2VX1/in4OCRJkiRJXZzxnhqXAS9qtlvANkk2A14IXA5sDVxdVfs2fd/W9P0M8MWqeh4w1uPLDgOeBSxoxh8wZP+jVfXCqvoW8A3g883xDgDuA04ALq+qhVV1ajNmIXBkE/PIJDsPd+AkxyZpJ2mveWTVWJ+FJEmSJKmLhffUWA4sSrItsBq4ik4B/iI6hfdjwLldfec32y8A/qXZ/n/HOMaBwL9U1Zqquhf40ZD93wZoctipqs4GqKpHq+qREWJeVFWrqupR4GZg1+E6VdWSqmpVVWvOVnPHSFOSJEmS1M2l5lOgqh5vlnsfA1wJ3AC8mM4S7luAx6uqmu5rWPdzL3o3Wt/fNj8zSp+hVndtD81LkiRJkjQFLLSmzmXA8cD/CQwA/zewvKqqc3n2sK4A3gB8HTiqh/hvT/I14Ol0Cvv17lBeVb9JcneSQ6vq+0k2B+YADwHbjv9trWvBTnNpe/dySZIkSeqZS82nzuXAjsBVVfUL4NGmbTTvBY5Lci0w1hrus4Hb6RT1XwQuHaXvm4H3JLmBzgz8H9KZhf99kuuTvG+sNyNJkiRJmhp5YgW0NLZWq1XtdrvfaUiSJElSXyRZXlWt8YxxxluSJEmSpGnkNd4bmSQLWP8O56urav9+5CNJkiRJmhwL741MVQ3Qeb62JEmSJGkT4FJzSZIkSZKmkTPem7gk5wB/VFX7DLMvwGeAVwKPAEdX1XWjxRu4ZxXzTzhv2H0rfcyYJEmSJK3HGe9NWJK/AB4epcufA3s0/46l85gySZIkSdIUsvCeoCRbJzmveS72jUmOTLIoyaVJlie5IMmOTd+3Jbm26fu9JFs17Uc0Y69PclnTtkWSryQZSPKTJC9u2o9OclaS85PcnuSUMfLbBvgb4GOjdHsd8LXquBrYbm3OkiRJkqSpYeE9ca8A7q2qfZtl3OcDnwUOr6pFwBnASU3fs6rqeVW1L3AL8Nam/cPAIU37a5u24wCqagHwRuCrSbZo9i0EjgQWAEcm2XmU/D4K/G86S8hHshPwn12v727a1pHk2CTtJO01j6waJZwkSZIkaSgL74kbAF6a5JNJXgTsDOwD/DDJCuDvgWc2ffdJcnmSAeAoYO+m/QpgaZK3AXOathfSPE6sqm4F7gL2bPZdVFWrqupR4GZg1+ESS7IQ+OOqOnuM95Bh2mq9hqolVdWqqtacreaOEVKSJEmS1M2bq01QVd2WZBGdG5N9AvghcFNVPX+Y7kuBQ6vq+iRHAwc1Md6RZH/gVcCKpmAerhhea3XX9hpG/v09H1iUZGXT5+lJLqmqg4b0u5vOHwzWeiZw7yjHlyRJkiSNk4X3BCV5BvCrqvp6kofp3JxsXpLnV9VVSTYD9qyqm4BtgfuatqOAe5oYu1fVMmBZktfQKYIva/r8KMmewC7AT4Hn9ppbVX2R5kZpSeYD5w5TdAOcA7w7ybeA/YFVVXXfaLEX7DSXtncvlyRJkqSeWXhP3ALgU0kGgceBdwK/B05LMpfOZ/tPwE3Ah4BldJaND9ApxGnG70Fnlvsi4HrgVuBLzbL039N5xNfqzpO/Ji/JOwCq6kvAv9GZsf8ZnWvBj5mSg0iSJEmS/luq1rukVxpRq9Wqdrvd7zQkSZIkqS+SLK+q1njGeHM1SZIkSZKmkUvNZ7gky4DNhzS/uaoG+pGPJEmSJGldFt4zXFXt3+8cJEmSJEkjs/DWuAzcs4r5J5y3XvtK73QuSZIkScPyGu+NRJJLkozrAv0pOOZJSf6zeRyaJEmSJGkaWHjPbj8AFvc7CUmSJEnalFl4T1KSv0xyTZIVSf45yZwkDyf5ZJLlSf4jyeJmRvuOJK9txm2Z5FtJbkjybWDLMY7zcDNDfX2Sq5Ps0LQvTfLFJBc38f8syRlJbkmydLSYVXV1Vd03VZ+FJEmSJGl9Ft6TkORPgCOBF1TVQmANcBSwNXBJVS0CHgI+BrwMOAz4x2b4O4FHquo5wEnAojEOtzVwdVXtC1wGvK1r31OAlwDvozOLfSqwN7AgycIpeJ/HJmknaa95ZNVkw0mSJEnSrOLN1SbnYDoF87VJoDNrfT/wGHB+02cAWF1VjycZAOY37QcCpwFU1Q1JbhjjWI8B5zbby+kU8mv9oKqqif+LtY8SS3JTc7wVE32DTX5LgCUAm++4R00mliRJkiTNNhbekxPgq1X1d+s0JsdX1doCdRBYDVBVg0m6P/PxFLGPd8Vcw7q/u9VDj9X12t+xJEmSJPWRRdnkXAT8a5JTq+r+JE8Ftu1x7GV0lqVfnGQf4DnTleRUWrDTXNo+OkySJEmSeuY13pNQVTcDfw9c2CwV/yGwY4/Dvwhs04x7P3DN9GQ5siSnJLkb2CrJ3UlO3NA5SJIkSdKmLk+sXpbG1mq1qt1u9zsNSZIkSeqLJMurqjWeMc54S5IkSZI0jbzGeyOTZBmw+ZDmN6+9U/nGElOSJEmS1BsL741MVe0/E2JKkiRJknpj4b0JSrIVcCawO51Hj/2gqk4Yoe/fAW9t+r2nqi4YLfbAPauYf8J567Wv9E7nkiRJkjQsr/HedH26qvYC9gNekOTPh3ZI8mzgDcDewCuALySZs2HTlCRJkqRNm4X3BCXZOsl5Sa5PcmOSI5MsSnJpkuVJLkiyY9P3bUmubfp+r5mRJskRzdjrk1zWtG2R5CtJBpL8JMmLm/ajk5yV5Pwktyc5ZaTcquqRqrq42X4MuA545jBdXwd8q6pWV9WdwM+AxVP5OUmSJEnSbGfhPXGvAO6tqn2rah/gfOCzwOFVtQg4Azip6XtWVT2vqvYFbqGztBvgw8AhTftrm7bjAKpqAfBG4KtJtmj2LQSOBBYARybZeawkk2wHvAa4aJjdOwH/2fX67qZtaIxjk7STtNc8smqsQ0qSJEmSuniN98QNAJ9O8kngXOC/gH2AHyYBmAPc1/TdJ8nHgO2AbYC111FfASxN8h3grKbthXQKeKrq1iR3AXs2+y6qqlUASW4GdmXdwnkdSZ4E/AtwWlXdMVyXYdrWe7B7VS0BlgBsvuMePvhdkiRJksbBwnuCquq2JIuAVwKfAH4I3FRVzx+m+1Lg0Kq6PsnRwEFNjHck2R94FbAiyUKGL4bXWt21vYaxf39LgNur6p9G2H830D1r/kzg3jFiSpIkSZLGwaXmE5TkGcAjVfV14NPA/sC8JM9v9m+WZO+m+7bAfUk2A47qirF7VS2rqg8Dv6RTBF+2tk+SPYFdgJ9OIL+PAXOBvx6l2znAG5JsnmQ3YA/gmvEeS5IkSZI0Mme8J24B8Kkkg8DjwDuB3wOnJZlL57P9J+Am4EPAMuAuOkvUt21ifCrJHnRmuS8CrgduBb6UZKCJd3RVrW6Wr/ckyTOBDzaxrmvGfq6qvpzktUCrqj5cVTc1y9xvbo51XFWtGfVN7zSXto8OkyRJkqSepcpLdtW7VqtV7Xa732lIkiRJUl8kWV5VrfGMcam5JEmSJEnTyKXmM1ySZcDmQ5rfXFUD/chHkiRJkrQuC+8Zrqr273cOkiRJkqSRudRckiRJkqRp5Iz3DJDkyqo6oMe+S4Fzq+q7Pfb9M2BV03R0Va0YbczAPauYf8J567Wv9E7nkiRJkjQsC+8ZoNeie4L+tpciXZIkSZI0MS41nwGSPJzkoCSXJvlOktuSnJzkqCTXJBlIsvsw4z6aZGkSf8+SJEmS1CcWZDPLvsB7gQXAm4E9q2ox8GXgr7o7JjkFeDpwTFUNjhLzpCQ3JDk1ydC7o6+NdWySdpL2mkdWDddFkiRJkjQCC++Z5dqquq+qVgM/By5s2geA+V39PgRsV1Vvr6oaJd7fAXsBzwOeCnxguE5VtaSqWlXVmrPV3Mm+B0mSJEmaVSy8Z5bVXduDXa8HWfd6/WuBRUmeOlqwpoivppD/CrB4KpOVJEmSJHlztU3V+cAFwHlJXl5VDw3XKcmOVXVfkgCHAjeOFXjBTnNpewdzSZIkSeqZhffMMNpy8eEHVJ2ZZFvgnCSvrKrfDdPtG0nmAQFWAO+YZJ6SJEmSpCEy+iXA6rck2wPXVdWu/c4FoNVqVbvd7ncakiRJktQXSZZXVWs8Y7zGeyOW5BnAVcCn+52LJEmSJGliXGq+Eauqe4E9JxsnydnAbkOaP1BVF0w2tiRJkiRpdBbes0BVHdbvHCRJkiRptnKpuSRJkiRJ08gZ7ymUZD5wblXt0+dUepZkJfAQsAb4/Vg3CRi4ZxXzTzhvvfaVPmJMkiRJkoZl4T2C5tnWqarBDXzcOVW1ZkMeE3hxVf1yAx9TkiRJkmYFl5p3STI/yS1JvgBcB3woyW1JLklyepLPNf2WJjktyZVJ7khy+DjiX57kuubfAU37QUkuTvJNYGCM3E5PclOSC5Ns2ey7JMmpSS5r+jwvyVlJbk/ysSn5cCRJkiRJE2Lhvb5nAV8DXgUcA/wp8DJgryH9dgReCLwaOLnH2PcDL6uq5wJHAqd17VsMfLCqnj3K+D2Az1fV3sCvgdd37Xusqg4EvgT8K3AcsA9wdPMs8JEUcGGS5UmOHa5DkmOTtJO01zyyaoy3KEmSJEnq5lLz9d1VVVcnORS4tKp+BZDkTNZ9tNf3m2XoNyfZocfYmwGfS7KQzjXV3fGuqao7xxh/Z1WtaLaXA/O79p3T/BwAbqqq+5q87wB2Bh4cIeYLqureJE8Hfpjk1qq6rLtDVS0BlgBsvuMeNUaOkiRJkqQuzniv77fNz4zRb3XX9lh913of8AtgX6AFPHmY4/Z6zDWs+4eTtfsGh/QbZJQ/sDTPCqeq7gfOpjPzLkmSJEmaIs54j+wa4NQkT6Fz1+/XM8L11+MwF7i7qgaTvAWYM8l4k5Jka+APquqhZvvlwD+ONmbBTnNpewdzSZIkSeqZhfcIquqeJB8HlgH3AjcDk73A+QvA95IcAVxMb7Pc02kH4OzODdx5EvDNqjq/vylJkiRJ0qYlVV6yO5Ik21TVw0meRGcZ9hlVdXa/8+qnVqtV7Xa732lIkiRJUl8kWV5VrfGM8Rrv0Z2YZAVwI3An8P0+5yNJkiRJmmFcaj6Kqjo4IrlLAAAgAElEQVR+IuOSHAJ8ckjznVV1WA9jtwcuGmbXwVU10p3JN3hMSZIkSVJvLLynQVVdAFwwwbEPAgunOJ8pjylJkiRJ6o1LzSVJkiRJmkbOeE+RJEcDrap69yRiXAIcX1Ub7O5lSc4HdqRzLlwOHFdVa0bqP3DPKuafcN567St9xJgkSZIkDcsZ7wlKx6bw+f0fVbUvsA8wDziiz/lIkiRJ0ibFGe9xSDIf+Hc6z+B+PvD9JEcB9wG3AatHGXsE8A/AGmBVVR2YZEvgK8CzgVuALcc4/sPAZ4BXA78DXldVv0iytHm9F7ArcAzwlibHZVV19Egxq+o3zeaTgCcDPl9OkiRJkqbQpjBju6E9C/ga8ErgrcALgJfRKZ5H82HgkGZ2+bVN2zuBR6rqOcBJwKIxYmwNXN3EuAx4W9e+pwAvAd4H/AA4FdgbWJBk1BurJbkAuB94CPjuMPuPTdJO0l7zyKoxUpQkSZIkdbPwHr+7qupqYH/gkqp6oKoeA749xrgrgKVJ3gbMadoOBL4OUFU3ADeMEeMx4Nxmezkwv2vfD6qqgAHgF1U1UFWDwE1D+q2nqg6hc5335nSK96H7l1RVq6pac7aaO0aKkiRJkqRuFt7j99uu7Z6XZVfVO4C/B3YGVjTP1h5XDODxpriGzpL17ksF1i5zH2TdJe+D9HBJQVU9CpwDvG4c+UiSJEmSxuA13hO3DPhMU0D/hs5Nya4fqXOS3atqGbAsyWvoFOCXAUcBFyfZB3jO9Ke9Tk7bANtW1X1JnkRn+fzlo41ZsNNc2t7BXJIkSZJ6ZuE9QU2xeiJwFZ2bq13HE0vIh/OpJHsAAS6iU6T/FPhKkhuAFcA105r0+rYGzkmyOZ3cfwR8aQPnIEmSJEmbtDyxclkaW6vVqnZ7gz1mXJIkSZI2KkmWV1VrPGO8xluSJEmSpGnkUvMpluSDdK737nZmVZ00jhjL6NxhvNubq2pgEnlNeUxJkiRJ0tgsvKdYU2D3XGSPEGP/KUpnWmNKkiRJksZm4a1xGbhnFfNPOG+99pXe6VySJEmShuU13lMoyfwkN/Y7j14l2SLJNUmuT3JTko/0OydJkiRJ2tQ44z2CJKFz1/fBDXzcOVW1ZgMdbjXwkqp6OMlmwI+T/HtVXb2Bji9JkiRJmzxnvLs0M9a3JPkCnedyfyjJbUkuSXJ6ks81/ZYmOS3JlUnuSHL4OOJfnuS65t8BTftBSS5O8k1g2JuddeV2ejM7fWGSLZt9lyQ5NcllTZ/nJTkrye1JPjZSPtXxcPNys+bfes+XS3JsknaS9ppHVvXyViVJkiRJDQvv9T0L+BrwKuAY4E+BlwF7Dem3I/BC4NXAyT3Gvh94WVU9FzgSOK1r32Lgg1X17FHG7wF8vqr2Bn4NvL5r32NVdSDwJeBfgeOAfYCjk2w/UsAkc5KsaHL7YVUtG9qnqpZUVauqWnO2mtvTG5UkSZIkdVh4r++uZqn1YuDSqvpVVT0OnDmk3/erarCqbgZ26DH2ZsDpSQaaeN1F9jVVdecY4++sqhXN9nJgfte+c5qfA8BNVXVfVa0G7gB2HilgVa2pqoXAM4HFSfbp8b1IkiRJknpg4b2+3zY/M0a/1V3bY/Vd633AL4B9gRbw5GGO2+sx17DuNfpr9w0O6TdID9fyV9WvgUuAV/SQhyRJkiSpR95cbWTXAKcmeQrwEJ1l3cNefz0Oc4G7q2owyVuAOZOMNylJ5gGPV9Wvm+vFXwp8crQxC3aaS9tHh0mSJElSzyy8R1BV9yT5OLAMuBe4GZjsncW+AHwvyRHAxfQ2yz2ddgS+mmQOndUP36mqc/uckyRJkiRtUlK13k2s1UiyTfOorScBZwNnVNXZ/c6rn1qtVrXb7X6nIUmSJEl9kWR5VbXGM8ZrvEd3YnPH7xuBO4Hv9zkfSZIkSdIM41LzUVTV8RMZl+QQ1r9W+s6qOqyHsdsDFw2z6+CqenCC+Ux5TEmSJElSbyy8p0FVXQBcMMGxDwILpzifKY8pSZIkSeqNhfcMkeTKqjqgx75LgXOr6rvjiP9Z4Jiq2ma0fgP3rGL+Ceet177SO51LkiRJ0rC8xnuG6LXonogkLWC76YovSZIkSbOZhfcMkeThJAcluTTJd5LcluTkJEcluSbJQJLdhxn30SRLkwz7u24eJfYp4P3T/R4kSZIkaTay8J559gXeCywA3gzsWVWLgS8Df9XdMckpwNPpLCEfHCHeu4Fzquq+kQ6Y5Ngk7STtNY9M9lHmkiRJkjS7WHjPPNdW1X1VtRr4OXBh0z4AzO/q9yFgu6p6e43wsPYkzwCOAD472gGraklVtaqqNWeruZN+A5IkSZI0m1h4zzyru7YHu14Psu7N8q4FFiV56iix9gP+GPhZkpXAVkl+NoW5SpIkSdKs513NN13n03mk2XlJXl5VDw3tUFXnAX+49nWSh6vqj0cLumCnubS9g7kkSZIk9czCe+YYdrn4qAOqzkyyLXBOkldW1e+mIS9JkiRJ0igywuW/2ogk2R64rqp27XcurVar2u12v9OQJEmSpL5IsryqWuMZ4zXeG7nmBmhXAZ/udy6SJEmSpPFzqflGrqruBfacbJwkZwO7DWn+QFVdMNnYkiRJkqSRWXjPElV1WL9zkCRJkqTZyKXmkiRJkiRNIwvvKZBkuyTvarbnJ3lT176Dkpw7jlgrkzxtGnKcl2RZkp8kedF0HUeSJEmStC4L76mxHfCuZns+8KaRu/bNwcCtVbVfVV0+XId0eE5IkiRJ0hSyyJoaJwO7J1kBfAp4UZIVSd431sAk2ye5sJmJ/mcgTfv7k7yn2T41yY+a7YOTfL3ZfjjJSUmuT3J1kh1GOMZC4BTglU1eW3btm5/kliRfAK4Ddp7MByFJkiRJWpeF99Q4Afh5VS0E/ha4vKoWVtWpPYz9B+DHVbUfcA6wS9N+GfCiZrsFbJNkM+CFwNoZ662Bq6tq36b/24Y7QFWtAD4MfLvJ63dDujwL+FozG37X0PFJjk3STtJ+4IEHenhLkiRJkqS1LLz770Dg6wBVdR7wX037cmBRkm2B1XSe5d2iU4yvLbwfA87t6j9/gjncVVVXj7SzqpZUVauqWvPmzZvgISRJkiRpdvJxYhuHWq+h6vEkK4FjgCuBG4AXA7sDtzTdHq+qtWPXMPHf528nOE6SJEmSNAZnvKfGQ8C2w2z34jLgKIAkfw48Zci+45uflwPvAFZ0FduSJEmSpI2chfcUqKoHgSuS3Aj8JfD75oZnY95cDfgIcGCS64CXA/9f177LgR2Bq6rqF8CjPLHMXJIkSZI0A8TJU41Hq9Wqdrvd7zQkSZIkqS+SLK+q1njGOOMtSZIkSdI08uZqG0iSY4D3Dmm+oqqOm+LjfBA4YkjzmVV10lQeR5IkSZLUG5eaa1xcai5JkiRpNnOpuSRJkiRJGxkL72mS5JIk4/oriCRJkiRp02PhLUmSJEnSNLLwHiLJXya5JsmKJP+cZE6Sh5N8MsnyJP+RZHEzo31Hktc247ZM8q0kNyT5NrDlGMd5OMlJzfO+r06yQ9O+NMkXk1zcxP+zJGckuSXJ0gnGfE2SZUl+0uS/tv3EJvba9/KeqfgMJUmSJElPsPDukuRPgCOBF1TVQmANcBSwNXBJVS0CHgI+BrwMOAz4x2b4O4FHquo5wEnAojEOtzVwdVXtC1wGvK1r31OAlwDvA34AnArsDSxIsnACMX8M/GlV7Qd8C3h/15i9gEOAxcA/JNlsmM/l2CTtJO0HHnhgjLclSZIkSerm48TWdTCdgvnaJNCZtb4feAw4v+kzAKyuqseTDADzm/YDgdMAquqGJDeMcazHgHOb7eV0Cvm1flBV1cT/RVUNACS5qTneinHGfCbw7SQ7Ak8G7uwac15VrQZWJ7kf2AG4uztoVS0BlkDnruZjvC9JkiRJUhdnvNcV4KtVtbD596yqOhF4vJ547togsBqgqgZZ948X4ylKu2OuGRJn9dBjdb0e7Y8lI8X8LPC5qloAvB3YYphjDZeHJEmSJGmSLLzXdRFweJKnAyR5apJdexx7GZ1l6STZB3jO9KQ4IXOBe5rtt/QzEUmSJEmabSy8u1TVzcDfAxc2S8V/COzY4/AvAts0494PXDM9WU7IicCZSS4HftnnXCRJkiRpVskTK5OlsbVarWq32/1OQ5IkSZL6IsnyqmqNZ4wz3pIkSZIkTSNvpDXNkiwDNh/S/Oa1dyrfWGJKkiRJkqaHhfc0q6r9Z0JMSZIkSdL0cKm5JEmSJEnTyMJ7Bkhy5Tj6Lk1yeI99353kZ0kqydMmnqEkSZIkaSQW3jNAVR0wTaGvAF4K3DVN8SVJkiRp1rPwngGSPJzkoCSXJvlOktuSnJzkqCTXJBlIsvsw4z7azIAP+3uuqp9U1cppfwOSJEmSNItZeM8s+wLvBRYAbwb2rKrFwJeBv+rumOQU4OnAMVU1OJmDJjk2STtJ+4EHHphMKEmSJEmadSy8Z5Zrq+q+qloN/By4sGkfAOZ39fsQsF1Vvb2qarIHraolVdWqqta8efMmG06SJEmSZhUL75llddf2YNfrQdZ9NNy1wKIkT91QiUmSJEmShmfhvWk6HzgZOC/Jtv1ORpIkSZJmMwvvmWHcy8Wr6kzgdOCcJFsO1yfJe5LcDTwTuCHJlyeXpiRJkiRpqEzBJcCaRkm2B66rql37nQtAq9Wqdrvd7zQkSZIkqS+SLK+q1njGOOO9EUvyDOAq4NP9zkWSJEmSNDFPGruL+qWq7gX2nGycJGcDuw1p/kBVXTDZ2JIkSZKk0Vl4zwJVdVi/c5AkSZKk2cql5n2Q5Mpx9F2a5PDpzEeSJEmSNH0svPugqg7odw6SJEmSpA3DwrsPkjyc5KAklyb5TpLbkpyc5Kgk1yQZSLL7MOM+2syAD/t7S7IyyUeSXNfE2KtpX5zkyiQ/aX4+q2k/OslZSc5PcnuSU6b3nUuSJEnS7GPh3V/7Au8FFgBvBvasqsXAl4G/6u7YFMVPB46pqsFRYv6yqp4LfBE4vmm7FTiwqvYDPgx8vKv/QuDIJocjk+w8NGCSY5O0k7QfeOCBCbxNSZIkSZq9LLz769qquq+qVgM/By5s2geA+V39PgRsV1Vvr7EfvH5W83N5V4y5wJlJbgROBfbu6n9RVa2qqkeBm4H1nhdeVUuqqlVVrXnz5vX+7iRJkiRJFt59trpre7Dr9SDr3nH+WmBRkqeOI+aarhgfBS6uqn2A1wBbjJBD9xhJkiRJ0hSw8J4ZzgdOBs5Lsu0Exs8F7mm2j56qpCRJkiRJY7Pw7o+xlouvP6DqTOB04JwkW45z+CnAJ5JcAcwZ77ElSZIkSROXsS8Z1lRKsj1wXVWtdy31TNBqtardbvc7DUmSJEnqiyTLq6o1njHOeG9ASZ4BXAV8ut+5SJIkSZI2DG+ktQFV1b3AnpONk+RsYLchzR+oqgsmG1uSJEmSNLUsvGegqjqs3zlIkiRJknrjUnNJkiRJkqbRjCy8kzw8zv4HJTl3uvIZ5biHJnl21+ujm+u8NwpJ9kpyVZLVSY7vdz6SJEmStCmakYX3DHIo8Oyu10cDG03hDfwKeA/e7E2SJEmSps2MLrybmexLknw3ya1JvpEkzb5XNG0/Bv5ijDgnds/4JrkxyfwkWyc5L8n1TduRo8Q4OcnNSW5I8ukkBwCvBT6VZEWSDwAt4BvN6y2TrEzykSTXJRlIstcYOZ7RvN87krynaZ/fvM8vNzl+I8lLk1yR5PYki0eKWVX3V9W1wOOjfT6SJEmSpInbFG6uth+wN3AvcAXwgiRt4HTgJcDPgG9PMPYrgHur6lUASeYO1ynJU4HDgL2qqpJsV1W/TnIOcG5Vfbfp9+fA8VXVbl4D/LKqnpvkXcDxwP81Sj57AS8GtgV+muSLTfsfA0cAxwLXAm8CXkin8P9fdGbeJyzJsU1sdtlll8mEkiRJkqRZZ0bPeDeuqaq7q2oQWAHMp1Og3llVt1dVAV+fYOwB4KVJPpnkRVW1aoR+vwEeBb6c5C+AR8ZxjLOan8vp5D6a86pqdVX9Ergf2KFpv7OqBprP4CbgouZ9D/QQc0xVtaSqWlXVmjdv3mTDSZIkSdKssikU3qu7ttfwxCx+jSPG71n3s9gCoKpuAxbRKWA/keTDww2uqt8Di4Hv0ZldPn8cx16bf3fuY/Ud2r+7fbDr9WAPMSVJkiRJ02hTLcpuBXZLsntV/Rx44xj9VwKvBkjyXGC3ZvsZwK+q6uvNndSPHm5wkm2Ararq35JcTWd5O8BDdJaFM8JrSZIkSdImbpMsvKvq0ea65POS/BL4MbDPKEO+B/zPJCvoXCN9W9O+gM7N0Qbp3IDsnSOM3xb41yRbAAHe17R/Czi9uRHa4cBS4EtJfgc8f6Lvb6ok+UOgDfwPYDDJXwPPrqrf9DczSZIkSdp0pHMpsNSbVqtV7Xa732lIkiRJUl8kWV5VrfGM2RSu8ZYkSZIkaaO1SS41H0mSY4D3Dmm+oqqOG0eMs2muAe/ygaq6YLL5NfEnneOGiClJkiRJ6o1LzTUuLjWXJEmSNJu51FySJEmSpI2Mhfcwkhyd5HPN9qFJnt3vnCRJkiRJM5OF99gOBSy8JUmSJEkTMusK7yTzk9ya5MtJbkzyjSQvTXJFktuTLO7qewDwWjrP8l6RZPcRYl6SpNVsPy3JymZ77yTXNGNvSLLHCOM/muS9Xa9PSvKeJAc1sb/b5PyNJBnlva1M8pEk1yUZSLJX0744yZVJftL8fFbTfnSSs5Kc37z3U8b9gUqSJEmSRjXrCu/GHwOfAZ4D7AW8CXghcDzwv9Z2qqorgXOAv62qhVX183Ee5x3AZ6pqIdAC7h6h3/8DvAUgyR8AbwC+0ezbD/hrOrPufwS8YIxj/rKqngt8sXk/ALcCB1bVfsCHgY939V8IHAksAI5MsvPQgEmOTdJO0n7ggQfGOLwkSZIkqdtsLbzvrKqBqhoEbgIuqs7t3QeA+VN4nKuA/5XkA8CuVfW74TpV1UrgwST7AS8HflJVDza7r6mqu5tcV/SQ31nNz+VdfecCZya5ETgV2Lur/0VVtaqqHgVuBnYdJr8lVdWqqta8efPGOLwkSZIkqdtsLbxXd20Pdr0eZGLPNv89T3yWW6xtrKpv0lmq/jvggiQvGSXGl4GjgWOAM0bIdU0P+a3t3933o8DFVbUP8JruHCcQX5IkSZI0DrO18B6Ph4Btx+izEljUbB++tjHJHwF3VNVpdJasP2eUGGcDrwCeB1ww0WRHMBe4p9k+eopjS5IkSZJGYeE9tm8Bf9vcmGzYm6sBnwbemeRK4Gld7UcCNyZZQeda8q+NdJCqegy4GPhOVa2ZmtT/2ynAJ5JcAcyZ4tiSJEmSpFGkc2mz+q25qdp1wBFVdXu/8xlJq9Wqdrvd7zQkSZIkqS+SLK+q1njGOOO9EUjybOBndG50ttEW3ZIkSZKk8fNGWuOQ5POs/zivz1TVV3ocvz1w0TC7Dq6qPxpHHmcDuw1p/kBVTfW14ZIkSZKkSbLwHoeqOm6S4x+k89zsyeZx2GRjSJIkSZI2DJeaS5IkSZI0jSy8p1CS+Ulu7Hce45HkjCT3z7S8JUmSJGmmsPAeQTo2+OeTZEM/7mspneeHS5IkSZKmgYV3l2bG+pYkX6DzaK8PJbktySVJTk/yuabf0iSnJbkyyR1JDh9H/MuTXNf8O6BpPyjJxUm+CQyMkdvpSW5KcmGSLZt9lyQ5NcllTZ/nJTkrye1JPjZaTlV1GfCr3j8lSZIkSdJ4WHiv71nA14BXAccAfwq8DNhrSL8dgRcCrwZO7jH2/cDLquq5wJHAaV37FgMfrKpnjzJ+D+DzVbU38Gvg9V37HquqA4EvAf8KHAfsAxzd3E19wpIcm6SdpP3AAw9MJpQkSZIkzToW3uu7q6quplMIX1pVv6qqx4Ezh/T7flUNVtXNwA49xt4MOD3JQBOvu8i+pqruHGP8nVW1otleDszv2ndO83MAuKmq7quq1cAdwM495jesqlpSVa2qas2bN28yoSRJkiRp1vFxYuv7bfMzY/Rb3bU9Vt+13gf8AtiXzh89Hh3muL0ecw2w5TD7Bof0G8TfsyRJkiT1jTPeI7sG+LMkT0nyJNZd1j1Rc4H7qmoQeDOwoW+kJkmSJEnawCy8R1BV9wAfB5YB/wHcDKyaZNgvAG9JcjWwJ73Nck+rJP8CXAU8K8ndSd7a75wkSZIkaVOSqup3DhutJNtU1cPNjPfZwBlVdXa/8+qnVqtV7Xa732lIkiRJUl8kWV5VrfGMccZ7dCcmWQHcCNwJfL/P+UiSJEmSZhhvujWKqjp+IuOSHAJ8ckjznVV1WA9jtwcuGmbXwVX14ATzmfKYkiRJkqTeWHhPg6q6ALhggmMfBBZOcT5THlOSJEmS1BuXmkuSJEmSNI0svCVJkiRJmkYW3uOQZOsk5yW5PsmNSY5MsijJpUmWJ7kgyY5N37clubbp+70kWzXtRzRjr09yWdO2RZKvJBlI8pMkL27aj05yVpLzk9ye5JQx8ns4yUlN7KuT7NC0vybJsib2f3S1n5jkjCSXJLkjyXum8/OTJEmSpNnIwnt8XgHcW1X7VtU+wPnAZ4HDq2oRcAZwUtP3rKp6XlXtC9wCrH0+9oeBQ5r21zZtxwFU1QLgjcBXk2zR7FsIHAksAI5MsvMo+W0NXN3Evgx4W9P+Y+BPq2o/4FvA+7vG7AUcAiwG/iHJZuP6RCRJkiRJo/LmauMzAHw6ySeBc4H/AvYBfpgEYA5wX9N3nyQfA7YDtuGJm61dASxN8h3grKbthXQKeKrq1iR3AXs2+y6qqlUASW4GdgX+c4T8HmvyAlgOvKzZfibw7WY2/sl0Ho221nlVtRpYneR+YAfg7u6gSY4FjgXYZZddRvt8JEmSJElDOOM9DlV1G7CITgH+CeD1wE1VtbD5t6CqXt50Xwq8u5nF/giwRRPjHcDfAzsDK5pHfWWUw67u2l7D6H8sebyqapi+nwU+1+Ty9rW59Bq/qpZUVauqWvPmzRvl8JIkSZKkoSy8xyHJM4BHqurrwKeB/YF5SZ7f7N8syd5N922B+5ql20d1xdi9qpZV1YeBX9IpwC9b2yfJnsAuwE+nMPW5wD3N9lumMK4kSZIkaQwuNR+fBcCnkgwCjwPvBH4PnJZkLp3P85+Am4APAcuAu+jMkG/bxPhUkj3ozHJfBFwP3Ap8KclAE+/oqlrdLF+fCicCZya5B7ga2G2qAkuSJEmSRpcnViZLY2u1WtVut/udhiRJkiT1RZLlVdUazxiXmkuSJEmSNI1caj4DJVkGbD6k+c1VNdCPfCRJkiRJI7PwnoGqav9+5yBJkiRJ6o1LzSVJkiRJmkYW3tMoyXZJ3tVsPyPJd/udkyRJkiRpw7Lwnl7bAe8CqKp7q+rwPucjSZIkSdrALLyn18nA7klWJDkzyY0ASY5O8v0kP0hyZ5J3J/mbJD9JcnWSpzb9dk9yfpLlSS5PstdIB0qyNMlpSa5MckeSw5v2bZJclOS6JANJXte0z09yS5LTk9yU5MIkW26Az0SSJEmSZhUL7+l1AvDzqloI/O2QffsAbwIWAycBj1TVfsBVwP9s+iwB/qqqFgHHA18Y43g7Ai8EXk2n6Ad4FDisqp4LvBj430nS7NsD+HxV7Q38Gnj9cEGTHJuknaT9wAMP9PC2JUmSJElreVfz/rm4qh4CHkqyCvhB0z4APCfJNsABwJlP1MnrPUJsqO9X1SBwc5IdmrYAH09yIDAI7ASs3XdnVa1otpcD84cLWlVL6PwRgFarVb2/RUmSJEmShXf/rO7aHux6PUjn9/IHwK+b2fKJxFxbrR8FzAMWVdXjSVYCWwzTfw3gUnNJkiRJmmIuNZ9eDwHbTmRgVf0GuDPJEQDp2HcCoeYC9zdF94uBXSeSjyRJkiRpYiy8p1FVPQhc0dxU7VMTCHEU8NYk1wM3Aa+bQIxvAK0k7SberROIIUmSJEmaoFR5ya5612q1qt1u9zsNSZIkSeqLJMurqjWeMc54S5IkSZI0jZzxnmGSfBA4YkjzmVV10gY6/kPATzfEsaRxehrwy34nIQ3heamNleemNkael9oYDXde7lpV88YTxMJb45KkPd5lFdKG4LmpjZHnpTZWnpvaGHleamM0VeelS80lSZIkSZpGFt6SJEmSJE0jC2+N15J+JyCNwHNTGyPPS22sPDe1MfK81MZoSs5Lr/GWJEmSJGkaOeMtSZIkSdI0svDWf0vyiiQ/TfKzJCcMs3/zJN9u9i9LMr9r39817T9NcsiGzFubtomel0nmJ/ldkhXNvy9t6Ny1aevh3DwwyXVJfp/k8CH73pLk9ubfWzZc1trUTfK8XNP1nXnOhstas0EP5+bfJLk5yQ1JLkqya9c+vzM1LSZ5Xo7rO9Ol5gIgyRzgNuBlwN3AtcAbq+rmrj7vAp5TVe9I8gbgsKo6MsmzgX8BFgPPAP4D2LOq1mzo96FNyyTPy/nAuVW1z4bPXJu6Hs/N+cD/AI4Hzqmq7zbtTwXaQAsoYDmwqKr+awO+BW2CJnNeNvserqptNmTOmh16PDdfDCyrqkeSvBM4qPnvud+ZmhaTOS+bfeP6znTGW2stBn5WVXdU1WPAt4DXDenzOuCrzfZ3gYOTpGn/VlWtrqo7gZ818aTJmsx5KU2nMc/NqlpZVTcAg0PGHgL8sKp+1fyP4w+BV2yIpLXJm8x5KU2nXs7Ni6vqkebl1cAzm22/MzVdJnNejpuFt9baCfjPrtd3N23D9qmq3wOrgO17HCtNxGTOS4DdkvwkyaVJXjTdyWpWmcz3nt+Zmi6TPbe2SNJOcnWSQ6c2Nc1y4z033wr8+wTHSr2azHkJ4/zOfNLEctQmaLgZwqHXIYzUp5ex0kRM5ry8D9ilqh5Msgj4fpK9q+o3U52kZqXJfO/5nanpMtlza5equjfJHxiZj2oAAAYPSURBVAE/SjJQVT+fotw0u/V8bib5SzrLyv9svGOlcZrMeQnj/M50xltr3Q3s3PX6mcC9I/VJ8iRgLvCrHsdKEzHh87K59OFBgKpaDvwc2HPaM9ZsMZnvPb8zNV0mdW5V1b3NzzuAS4D9pjI5zWo9nZtJXgp8EHhtVa0ez1hpAiZzXo77O9PCW2tdC+yRZLckTwbeAAy9O985wNo7SR4O/Kg6d+c7B3hDc3fp3YA9gGs2UN7atE34vEwyr7lpBs1fIvcA7thAeWvT18u5OZILgJcneUqSpwAvb9qkyZrwedmcj5s3208DXgDcPPooqWdjnptJ9gP+mU5xc3/XLr8zNV0mfF5O5DvTpeYCOtfGJnk3nS+yOcAZVXVT8v+3d28hdlV3HMe/P2OJ1YiJVKT0wUCweAkasBJorcYqhT40RlAolWLQirYqFGqtL1o6igQGX6woXtpGW0GNlxJ9MErQ4AWLMeaqhUq1plAsNI2psZYm+fdhr5FjnCTjzOxIZr4fGM6etffa68LmnPPnf9beGQLWVtVK4NfA75K8RZfp/l6ruyXJI3QX2y7gau9orskwkesSOBsYSrIL2A1cVVXbDv4oNBWN5dpMcibwBDAH+G6SX1bVqVW1LcnNdB/4AENem5oME7kugZOBu5PsoUvMLBu8s680EWP8PB8GZgEr2j1S362qxb5nqi8TuS4Zx3umjxOTJEmSJKlH/tRckiRJkqQeGXhLkiRJktQjA29JkiRJknpk4C1JkiRJUo8MvCVJkiRJ6pGBtyRJ00iS3UnWD/zNHcc5Zif58eT37uPzL05yQ1/n30ebS5KccjDblCRNHz5OTJKkaSTJB1U1a4LnmAs8VVXzP2O9GVW1eyJt9yHJ4cB9dGN69PPujyRp6jHjLUnSNJdkRpLhJK8m2ZjkylY+K8nqJOuSbEpyQauyDJjXMubDSRYleWrgfHckWdq230lyU5IXgYuTzEvydJLXkryQ5KRR+rM0yR1te3mSu5I8l+QvSc5J8pskbyZZPlDngyS3tb6uTnJcK1+Q5JU2rieSzGnlzye5Ncka4OfAYmC4jWlekivafGxI8liSIwf6c3uSl1t/Lhrow/VtnjYkWdbKDjheSdLUd/jn3QFJknRQfTHJ+rb9dlVdCFwOvF9VZyaZCbyU5BlgK3BhVe1I8iXglSQrgRuA+VW1ACDJogO0+VFVndWOXQ1cVVV/TrIQuBP41gHqz2nHLAaeBL4B/BB4NcmCqloPHAWsq6qfJrkJ+AVwDfAAcG1VrUky1Mp/0s47u6rOaf06kYGMd5LtVXVv276lzdGvWr0vA2cBJwErgUeTfAdYAiysqg+THNuOvWcc45UkTTEG3pIkTS//GQmYB3wbOG0ge3sMcCLwN+DWJGcDe4CvAMePo82HocugA18HViQZ2TdzDPWfrKpKsgl4r6o2tfNtAeYC61v/Hm7H/x54PMkxdMH1mlZ+P7Bi737tw/wWcM8GZgGrBvb9oar2AG8kGZmP84HfVtWHAFW1bQLjlSRNMQbekiQpdFnhVZ8o7H4ufhxwRlX9L8k7wBGj1N/FJ5ev7X3MzvZ6GLB9lMD/QP7bXvcMbI/8v6/vMmO5ic3O/exbDiypqg1tHhaN0h/o5m7kde82xzteSdIU4xpvSZK0CvhRki8AJPlqkqPoMt//aEH3ucAJ7fh/A0cP1P8rcEqSmS3LfN5ojVTVDuDtJBe3dpLk9Ekaw2HASMb++8CLVfU+8K8k32zlPwDWjFaZT4/paODvbU4uGUP7zwCXDawFP7bn8UqSDiEG3pIk6T7gDWBdks3A3XSZ5AeBryVZSxd8/gmgqv5Jtw58c5LhqtoKPAJsbHVe309blwCXJ9kAbAEu2M+xn8VO4NQkr9GtoR5q5ZfS3TRtI7BgoHxvDwE/S/J6knnAjcAfgWdp496fqnqabr332raG/rq2q6/xSpIOIT5OTJIkHfIyCY9JkySpL2a8JUmSJEnqkRlvSZIkSZJ6ZMZbkiRJkqQeGXhLkiRJktQjA29JkiRJknpk4C1JkiRJUo8MvCVJkiRJ6pGBtyRJkiRJPfo/KSsCLufBANgAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> 
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
