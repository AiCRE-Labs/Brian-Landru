---
layout: default
---
<style>
  /* General font size for all span elements */
  span {
    font-size: 25px; /* Change this value as needed */
  }

  /* Specific font size for elements with specific IDs
  #hello, #summary, #capabilities, #letsgo {
    font-size: 25px;
  }


  #typed-static {
    font-size: 25px; 
     } 
  */
@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

#typed-static {
  animation: fadeIn ease-in 1s; /* Adjust the duration (1s) as needed */
  animation-delay: 4s; /* Adjust the delay as needed */
  animation-fill-mode: forwards; /* Keeps the element in the final state of the animation */
  opacity: 0; /* Start with the element invisible */
}
</style>


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
    typeSpeed: 30,
    startDelay: 250,
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
       'You have <strong class="typed-strong"><a href="/brian-landru/your-vacancies/">44 vacancies</a></strong> across 25 of your 28 properties.',
    ],
    typeSpeed: 30,
    startDelay: 1500,
    smartBackspace: false,
    loop: false,
    backDelay: 1000, // Delay period after the text is typed out
    showCursor: false,
    cursorChar: '|', 
    contentType: 'html', // 
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
    startDelay: 5000,
    smartBackspace: true,
    loop: true,
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

<!-- CALL TO ACTION -->

<script>
  var letsgo = new Typed('#letsgo', {
  strings: [
      '<a href="/brian-landru/your-vacancies/" class="typed-strong" style="color: gold;" class="arrow-link"><strong>Let\'s get started </strong></a> <a href="/brian-landru/your-vacancies/" class="arrow-link"> </a>'
    ],
  // strings: [
  //   '<a href="/brian-landru/your-vacancies/" class="typed-strong arrow-link";><strong>Let\'s get started</strong></a>'
  // ],
    typeSpeed: 30,
    startDelay: 9000,
    smartBackspace: false,
    loop: false,
    backDelay: 500, // Delay period after the text is typed out
    showCursor: false,
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

<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const anim = anime.timeline({
      loop: true,
      direction: 'alternate',
    });

    anim
      .add({
        targets: '.hexagon-container #hexagon path',
        strokeDashoffset: [anime.setDashoffset, 0],
        easing: 'easeInOutQuart',
        duration: 2000,
        delay: function(el, i) { return i * 250 },
      })
      .add({
        targets: '.hexagon-container #hexagon #B',
        duration: 1000,
        opacity: 1,
        easing: 'easeInOutQuart'
      });
  });
</script>
