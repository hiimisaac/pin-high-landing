<script>
  import phonePro from './assets/iphone-16-pro-white.png';

  const pillars = [
    {
      title: 'Score the day with context',
      body: 'Rain chance, wind, temperature comfort, and UV are weighted into a clear playability call.'
    },
    {
      title: 'Book the right window',
      body: 'Pin High highlights the best stretch of day that still works for a full round in daylight.'
    },
    {
      title: 'Move your crew faster',
      body: 'Use a clean summary to get yes/no responses without weather argument threads.'
    }
  ];

  const steps = [
    {
      title: 'Check Today',
      body: 'Open Pin High and get the day score instantly before anyone commits.'
    },
    {
      title: 'Choose Time',
      body: 'Use the tee-window signal to lock the strongest playable range.'
    },
    {
      title: 'Send Ask',
      body: 'Share one clear recommendation and align the group quickly.'
    }
  ];

  const reviews = [
    {
      quote:
        'The score view replaced three weather apps for us. We decide in minutes now.',
      by: 'Evan R. · Weekend foursome'
    },
    {
      quote:
        'Best tee window is exactly what I needed. It saves me from bad-time bookings.',
      by: 'Drew M. · Morning golfer'
    }
  ];

  const scoreFactors = [
    { label: 'Rain risk', value: '6%', state: 'Low' },
    { label: 'Wind', value: '13 mph', state: 'Breezy' },
    { label: 'High temp', value: '52F', state: 'Cool' }
  ];
</script>

<main class="page-wrap" id="home">
  <div class="page-shell">
    <section class="hero" aria-labelledby="hero-title">
      <header class="topbar">
        <p class="brand">PIN HIGH</p>
        <nav aria-label="Primary">
          <a href="/#features">Features</a>
          <a href="/#how">How it works</a>
          <a href="/#reviews">Testimonials</a>
        </nav>
        <a class="chip-btn" href="#" aria-label="Download app">Download App</a>
      </header>

      <div class="hero-copy">
        <p class="eyebrow">Forecast clarity for golfers</p>
        <h1 id="hero-title">
          Elevate Your Round
          <span class="line-break">with</span>
          <span>Smarter Timing</span>
        </h1>
        <p>
          Pin High converts weather complexity into one decision score, your best tee window, and a cleaner crew call.
        </p>
        <div class="store-row" aria-label="Store links">
          <a class="store-badge" href="#" aria-label="Download on the App Store">App Store</a>
          <a class="store-badge" href="#" aria-label="Get it on Google Play">Google Play</a>
        </div>
      </div>

      <article class="hero-scorecard" aria-label="Today scorecard">
        <p class="scorecard-kicker">Today</p>
        <p class="scorecard-score">73</p>
        <p class="scorecard-label">Playable Day · PTS</p>
        <div class="scorecard-lines">
          <p><span>Rain Risk</span><strong>6% · Low</strong></p>
          <p><span>Wind</span><strong>13 mph · Breezy</strong></p>
          <p><span>Best Window</span><strong>4-hour fit available</strong></p>
        </div>
      </article>

    </section>

    <section id="features" class="split section" aria-labelledby="features-title">
      <div class="split-copy">
        <p class="eyebrow">Purpose-built</p>
        <h2 id="features-title">Style your golf decisions with precision.</h2>
        <p>Pin High is designed for players who care about playable conditions, cleaner planning, and better outcomes.</p>
      </div>
      <div class="split-list">
        {#each pillars as pillar}
          <article>
            <h3>{pillar.title}</h3>
            <p>{pillar.body}</p>
          </article>
        {/each}
      </div>
    </section>

    <section id="how" class="split split-reverse steps section" aria-labelledby="steps-title">
      <div class="split-copy">
        <p class="eyebrow">Simple process</p>
        <h2 id="steps-title">Your better round starts here.</h2>
        <p>Check the day, choose the best window, and send one clear recommendation to your crew.</p>
      </div>
      <div class="split-list steps-list">
        {#each steps as step, i}
          <article class="step-card">
            <p class="step-num">0{i + 1}</p>
            <h3>{step.title}</h3>
            <p>{step.body}</p>
          </article>
        {/each}
      </div>
    </section>

    <section id="reviews" class="reviews section" aria-labelledby="reviews-title">
      <div class="section-head two-col">
        <div>
          <p class="eyebrow">Social proof</p>
          <h2 id="reviews-title">Reviews that speak for themselves.</h2>
        </div>
        <p>
          Real groups use Pin High to make faster weather calls, pick better windows, and avoid low-quality rounds.
        </p>
      </div>
      <div class="review-grid">
        {#each reviews as item}
          <blockquote>
            <p>{item.quote}</p>
            <footer>{item.by}</footer>
          </blockquote>
        {/each}
      </div>
    </section>

    <section class="story section" aria-labelledby="story-title">
      <div class="section-head two-col two-col-reverse">
        <div>
          <p class="eyebrow">Why Pin High</p>
          <h2 id="story-title">Revolutionizing your golf-day planning.</h2>
        </div>
        <p>
          From uncertain weather mornings to confident booking windows, Pin High keeps the signal clean and actionable.
        </p>
      </div>
      <div class="story-grid">
        {#each scoreFactors as factor}
          <article class="story-tile">
            <p>{factor.label}</p>
            <h3>{factor.value}</h3>
            <span>{factor.state}</span>
          </article>
        {/each}
      </div>
    </section>

    <section id="download" class="download section" aria-label="Final download CTA">
      <div>
        <p class="eyebrow light">Download mobile app</p>
        <h2>Play better rounds with confidence.</h2>
        <div class="store-row">
          <a class="store-badge" href="#" aria-label="Download on the App Store">App Store</a>
          <a class="store-badge" href="#" aria-label="Get it on Google Play">Google Play</a>
        </div>
      </div>
      <div class="download-phone" aria-hidden="true">
        <img src={phonePro} alt="" />
      </div>
    </section>

    <footer class="footer">
      <div>
        <p class="brand">PIN HIGH</p>
        <p>Weather clarity for better golf days.</p>
      </div>
      <nav aria-label="Footer">
        <a href="/#home">Home</a>
        <a href="/#features">Features</a>
        <a href="/#how">How it works</a>
        <a href="/#download">Download</a>
      </nav>
      <div class="legal-links">
        <a href="/privacy-policy">Privacy Policy</a>
        <a href="/terms-and-conditions">Terms &amp; Conditions</a>
      </div>
    </footer>
  </div>
</main>
