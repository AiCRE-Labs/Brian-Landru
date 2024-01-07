---
layout: default
---
<style>
  /* General font size for all span elements */
  span {
    font-size: 30px; /* Change this value as needed */
  }

  /* Specific font size for elements with specific IDs
  #hello, #summary, #capabilities, #letsgo {
    font-size: 25px;
  }


  #typed-static {
    font-size: 25px; 
     } 
  */

</style>
<class >
<span id="hello"></span>
<br>
<br>
<span id="summary"></span>
<br>
<br>
<span id="typed-static">I can help you:</span>
<span id="capabilities"></span>
<br>
<br>
<span id="letsgo"></span>

<!-- Load library from the CDN -->
<script src="https://unpkg.com/typed.js@2.1.0/dist/typed.umd.js"></script>

<!-- HELLO NAME TYPED TEXT -->
<script>
  var hello = new Typed('#hello', {
    strings: [
    'Hey <strong class="typed-strong" style= "color: black;">Brian,</strong>'
  ],
    typeSpeed: 5,
    startDelay: 500,
    smartBackspace: false,
    loop: false,
    backDelay: 1000, // Delay period after the text is typed out
    showCursor: false,
    cursorChar: '|', 
    preStringTyped: function(arrayPos, self) {
      if (arrayPos === 0) {
        document.getElementById('typed-static').style.visibility = 'visible';
      }
    },
    onReset: function(self) {
      document.getElementById('typed-static').style.visibility = 'hidden';
    }
  });
</script>

<!-- SUMMARY TYPED TEXT -->
<script>
  var summary = new Typed('#summary', {
    strings: [
     
       'You have <strong class="typed-strong">44 vacancies</strong> across 25 of your 28 properties.',
    ],
    typeSpeed: 5,
    startDelay: 500,
    smartBackspace: false,
    loop: false,
    backDelay: 1000, // Delay period after the text is typed out
    showCursor: false,
    cursorChar: '|', 
    preStringTyped: function(arrayPos, self) {
      if (arrayPos === 0) {
        document.getElementById('typed-static').style.visibility = 'visible';
      }
    },
    onReset: function(self) {
      document.getElementById('typed-static').style.visibility = 'hidden';
    }
  });
</script>



<!-- CAPABILITIES TYPED TEXT -->
<script>
  var capabilities = new Typed('#capabilities', {
    strings: [
    '<strong class="typed-strong">find the best tenants</strong>',
    '<strong class="typed-strong">reduce time off market</strong>',
    '<strong class="typed-strong">minimize turnover</strong>', 
    '<strong class="typed-strong">optimize tenant mix</strong>', 
    '<strong class="typed-strong">close deals faster</strong>',
    '<strong class="typed-strong">improve NOI</strong>'
  ],
    typeSpeed: 30,
    backSpeed: 10,
    startDelay: 500,
    smartBackspace: true,
    loop: true,
    backDelay: 1000, // Delay period after the text is typed out
    showCursor: true,
    cursorChar: '|', 
    preStringTyped: function(arrayPos, self) {
      if (arrayPos === 0) {
        document.getElementById('typed-static').style.visibility = 'visible';
      }
    },
    onReset: function(self) {
      document.getElementById('typed-static').style.visibility = 'hidden';
    }
  });
</script>

<!-- CALL TO ACTION -->
<script>
  var letsgo = new Typed('#letsgo', {
  strings: [
      '<a href="/brian-landru/your-vacancies/" class="typed-strong" style="color: black;"><strong>Lets get started  </strong></a>'
    ],
    typeSpeed: 5,
    startDelay: 0,
    smartBackspace: false,
    loop: false,
    backDelay: 500, // Delay period after the text is typed out
    showCursor: true,
    cursorChar: ' ▶', 
    preStringTyped: function(arrayPos, self) {
      if (arrayPos === 0) {
        document.getElementById('typed-static').style.visibility = 'visible';
      }
    },
    onReset: function(self) {
      document.getElementById('typed-static').style.visibility = 'hidden';
    }
  });
</script>
