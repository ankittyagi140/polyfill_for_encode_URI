# polyfill_for_encode_URI
Pollyfill for encodeURI

const sanitizer=function(input){
const sanitizeValue={
  "&":"&amp;",
  "<":"&lt",
  ">":"&gt",
  """:"&quot",
  "'":"&#x27"
  /*can add any custom regex as per requirement*/
  };
const regex=/[&<>"']/gi;
return input.replace(regex,match=>sanitizeValue[match]);
}
sanitizer("https://www.baseurl.com/query?name=<script>console.log("attack")</>);
