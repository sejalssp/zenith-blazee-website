<template>
  <!-- ==============================
       1. HERO
       ============================== -->
  <section class="hero" aria-label="Hero">
    <HeroFinanceBg />
    <div class="hero-bg" aria-hidden="true"></div>

    <div class="container hero-content">
      <h1 class="hero-heading">
        <span class="hero-line hero-anim hero-anim--2">Your Goals.</span>
        <span class="hero-line hero-anim hero-anim--3">Your Plan.</span>
        <span class="hero-line hero-anim hero-anim--4">Your Future.</span>
      </h1>
      <p class="hero-tagline hero-anim hero-anim--5">Your Financial Partner.</p>
      <p class="hero-sub hero-anim hero-anim--6">
        We help individual investors build wealth the right way — with a personalised plan built around your life, not a template.
      </p>
    </div>
  </section>

  <!-- ==============================
       2. STATS STRIP
       ============================== -->
  <section class="stats-strip" aria-label="Credentials and trust indicators" ref="statsRef">
    <div class="container stats-grid">
      <div
        v-for="(stat, i) in stats"
        :key="stat.label"
        class="stat-item"
        :data-aos="'fade-up'"
        :data-aos-delay="i * 80"
      >
        <span class="stat-value">{{ stat.value }}</span>
        <span class="stat-label">{{ stat.label }}</span>
      </div>
    </div>
  </section>

  <!-- ==============================
       3. SERVICES TEASER
       ============================== -->
  <section class="section section--white services-teaser" aria-labelledby="services-heading">
    <div class="container">
      <div class="section-intro" data-aos="fade-up">
        <span class="section-label">What We Offer</span>
        <h2 class="section-heading" id="services-heading">Two pillars of a complete financial plan</h2>
        <p class="section-sub" style="color: var(--color-grey-dark)">
          Whether you're looking to grow your wealth or protect what you have — we cover both.
        </p>
      </div>

      <div class="services-cards">
        <div class="service-card" data-aos="fade-up" data-aos-delay="0">
          <div class="service-card-icon">
            <svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
              <polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/><polyline points="17 6 23 6 23 12"/>
            </svg>
          </div>
          <h3 class="service-card-title">Mutual Fund Planning</h3>
          <p class="service-card-desc">
            Goal-based investment planning built around your life — retirement, education, financial freedom, and more. Every plan is mapped to the right fund, SIP, and timeline.
          </p>
          <RouterLink to="/services#mutual-funds" class="service-card-link">
            Explore Mutual Funds
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" aria-hidden="true">
              <line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/>
            </svg>
          </RouterLink>
        </div>

        <div class="service-card" data-aos="fade-up" data-aos-delay="120">
          <div class="service-card-icon">
            <svg width="30" height="30" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
              <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
            </svg>
          </div>
          <h3 class="service-card-title">Insurance Advisory</h3>
          <p class="service-card-desc">
            Guidance on life and health insurance coverage — making sure your financial plan is protected from the unexpected. Advisory only; we help you decide, not sell.
          </p>
          <RouterLink to="/services#insurance" class="service-card-link">
            Explore Insurance Advisory
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" aria-hidden="true">
              <line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/>
            </svg>
          </RouterLink>
        </div>
      </div>
    </div>
  </section>

  <!-- ==============================
       5. WHY ZENITH BLAZEE
       ============================== -->
  <section class="section section--dark why-section" aria-labelledby="why-heading">
    <div class="why-bg" aria-hidden="true"></div>
    <div class="container">
      <div class="section-intro why-intro" data-aos="fade-up">
        <span class="section-label">Why Choose Us</span>
        <h2 class="section-heading" id="why-heading" style="color: var(--color-cream)">
          What makes Zenith Blazee different
        </h2>
      </div>
      <div class="why-grid">
        <div
          v-for="(item, i) in whyItems"
          :key="item.title"
          class="why-card"
          data-aos="fade-up"
          :data-aos-delay="i * 80"
        >
          <div class="why-icon" aria-hidden="true" v-html="item.icon"></div>
          <h3 class="why-title">{{ item.title }}</h3>
          <p class="why-desc">{{ item.desc }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ==============================
       6. FAQ
       ============================== -->
  <section class="section section--white faq-section" aria-labelledby="faq-heading">
    <div class="container faq-inner">
      <div class="faq-left" data-aos="fade-right">
        <span class="section-label">FAQ</span>
        <h2 class="section-heading" id="faq-heading">
          Questions we hear<br />all the time
        </h2>
        <p class="section-sub" style="color: var(--color-grey-dark)">
          If you don't find what you're looking for, just reach out — we're happy to talk.
        </p>
        <RouterLink to="/contact" class="btn btn--primary" style="margin-top: var(--space-lg)">
          Ask Us Anything
        </RouterLink>
      </div>

      <div class="faq-list" data-aos="fade-left" data-aos-delay="80">
        <div
          v-for="(item, i) in faqs"
          :key="i"
          class="faq-item"
          :class="{ 'faq-item--open': openFaq === i }"
        >
          <button
            class="faq-question"
            @click="toggleFaq(i)"
            :aria-expanded="String(openFaq === i)"
            :aria-controls="`faq-answer-${i}`"
          >
            <span>{{ item.q }}</span>
            <span class="faq-chevron" aria-hidden="true">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round">
                <polyline points="6 9 12 15 18 9"/>
              </svg>
            </span>
          </button>
          <div
            :id="`faq-answer-${i}`"
            class="faq-answer"
            role="region"
          >
            <p>{{ item.a }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ==============================
       8. MEET THE PARTNERS
       ============================== -->
  <section class="section section--cream partners-section" aria-labelledby="partners-heading">
    <div class="container">
      <div class="section-intro" data-aos="fade-up">
        <span class="section-label">Meet the Partners</span>
        <h2 class="section-heading" id="partners-heading">The people behind your plan</h2>
        <p class="section-sub" style="color: var(--color-grey-dark)">
          Two professionals with very different backgrounds, united by one commitment: helping you get where you want to go.
        </p>
      </div>

      <div class="partners-grid">
        <div
          v-for="(partner, i) in partners"
          :key="partner.name"
          class="partner-card"
          data-aos="fade-up"
          :data-aos-delay="i * 120"
        >
          <div class="partner-avatar" :style="{ backgroundColor: partner.avatarBg }">
            {{ partner.initials }}
          </div>
          <div class="partner-info">
            <h3 class="partner-card-name">{{ partner.name }}</h3>
            <p class="partner-card-role gold-text">{{ partner.role }}</p>
            <p class="partner-card-bio">{{ partner.bio }}</p>
          </div>
        </div>
      </div>

      <div class="partners-cta" data-aos="fade-up">
        <RouterLink to="/about" class="btn btn--primary">Our Full Story</RouterLink>
      </div>
    </div>
  </section>

  <!-- ==============================
       9. CTA STRIP
       ============================== -->
  <section class="cta-strip section--navy" aria-labelledby="cta-heading">
    <div class="cta-strip-bg" aria-hidden="true"></div>
    <div class="cta-strip-top-line" aria-hidden="true"></div>
    <div class="container cta-strip-inner" data-aos="fade-up">
      <span class="section-label" style="display: block; text-align: center; margin-bottom: var(--space-sm)">Take the First Step</span>
      <h2 class="cta-heading" id="cta-heading" style="color: var(--color-cream)">
        Ready to start building<br />your financial future?
      </h2>
      <p class="cta-sub">We respond within 1–2 working days. No pressure, just a conversation.</p>
      <RouterLink to="/contact" class="btn btn--primary">Get in Touch Today</RouterLink>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

useHead({
  title: 'Zenith Blazee | Mutual Fund Distributor',
  meta: [
    {
      name: 'description',
      content:
        'Zenith Blazee (ARN-334080) helps individuals invest in mutual funds with personalised, goal-based financial planning. Talk to an advisor today.'
    }
  ]
})

/* ── Stats ── */
const stats = [
  { value: '15+', label: 'Years Combined Expertise' },
  { value: 'MF + Insurance', label: 'Complete Advisory Services' },
  { value: '5', label: 'Goal Categories Covered' },
  { value: 'AMFI Registered', label: 'ARN-334080' }
]

/* ── Why Us ── */
const whyItems = [
  {
    title: 'No Conflict of Interest',
    desc: "We're your distributor, not the fund house. Your long-term returns matter more to us than product margins.",
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/><polyline points="9 12 11 14 15 10"/></svg>`
  },
  {
    title: 'CA-Backed Planning',
    desc: "Every plan has Dhaval's financial rigour built in. Decisions are grounded in numbers, not guesswork.",
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>`
  },
  {
    title: 'People-First Approach',
    desc: "Annkkur's hospitality background means you'll always feel heard, respected, and genuinely understood.",
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>`
  },
  {
    title: 'Long-Term Commitment',
    desc: "We don't just start plans — we stay invested in seeing them through. No one-time transactions here.",
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><polyline points="23 6 13.5 15.5 8.5 10.5 1 18"/><polyline points="17 6 23 6 23 12"/></svg>`
  }
]

/* ── FAQ ── */
const openFaq = ref(0)

function toggleFaq(i) {
  openFaq.value = openFaq.value === i ? -1 : i
}

const faqs = [
  {
    q: 'What is a mutual fund distributor?',
    a: 'A mutual fund distributor is an AMFI-registered professional who helps investors select, purchase, and manage mutual fund investments. Unlike banks or apps, a distributor provides personalised guidance — not a one-size-fits-all portfolio. Zenith Blazee is registered under ARN-334080.'
  },
  {
    q: 'How are you different from investing through a bank or app?',
    a: 'Banks and apps offer standardised products with little personalisation. At Zenith Blazee, we take time to understand your specific goals and build a plan around them. We are accessible, accountable, and stay with you through the journey — not just at the point of sale.'
  },
  {
    q: 'Do I need a large amount to start investing?',
    a: 'No. Mutual funds can be started with as little as ₹500 per month through a SIP (Systematic Investment Plan). We will help you find the right starting point based on your income, goals, and timeline.'
  },
  {
    q: 'What is goal-based planning and how does it work?',
    a: "Goal-based planning means every investment is linked to a specific objective — your child's education, your retirement, or your financial freedom. Instead of investing generically, we map each goal to the right fund category, timeline, and SIP amount."
  },
  {
    q: 'Are mutual fund investments safe?',
    a: 'All mutual fund investments carry market risk, and past performance does not guarantee future returns. However, with the right diversification, time horizon, and planning, risk can be managed significantly. We always ensure you understand what you are investing in before you commit.'
  },
  {
    q: 'What does insurance advisory mean — do you sell insurance?',
    a: 'We offer advisory on life and health insurance — helping you understand what coverage you need and how it fits into your overall financial plan. We do not sell specific insurance products. Our focus is purely on helping you make informed decisions.'
  }
]

/* ── Partners ── */
const partners = [
  {
    name: 'Annkkur Bandhu',
    initials: 'AB',
    role: 'Partner',
    avatarBg: 'rgba(201,168,76,0.12)',
    bio: '15+ years in luxury hospitality (Taj, Oberoi, Fairmont, Vantara). Annkkur brings a deeply people-first approach — he is the first point of connection for most clients.'
  },
  {
    name: 'Dhaval Pitkar',
    initials: 'DP',
    role: 'Partner, CA',
    avatarBg: 'rgba(27,42,74,0.08)',
    bio: 'Chartered Accountant with Big 4 and startup experience. Dhaval brings financial depth to every plan — ensuring every recommendation is grounded in solid fundamentals.'
  }
]
</script>

<style scoped>
/* ==============================
   HERO
   ============================== */
.hero {
  align-items: center;
  background: linear-gradient(135deg, #0d1b2a 0%, #1b2a4a 50%, #0d1b2a 100%);
  display: flex;
  min-height: 100dvh;
  overflow: hidden;
  position: relative;
}

.hero-bg {
  background:
    radial-gradient(ellipse at 20% 50%, rgba(201, 168, 76, 0.08) 0%, transparent 60%),
    radial-gradient(ellipse at 80% 20%, rgba(201, 168, 76, 0.06) 0%, transparent 50%);
  inset: 0;
  pointer-events: none;
  position: absolute;
}

.hero-content {
  padding-bottom: var(--space-xl);
  padding-top: calc(var(--header-height) + var(--space-xl));
  position: relative;
  text-align: center;
  z-index: 2;
}

.hero-anim { opacity: 0; }
.hero-anim--1 { animation: fadeIn 0.7s ease 0.1s forwards; }
.hero-anim--2 { animation: fadeSlideUp 0.8s ease 0.35s forwards; }
.hero-anim--3 { animation: fadeSlideUp 0.8s ease 0.55s forwards; }
.hero-anim--4 { animation: fadeSlideUp 0.8s ease 0.75s forwards; }
.hero-anim--5 { animation: fadeSlideUp 0.9s ease 1.0s forwards; }
.hero-anim--6 { animation: fadeIn 0.9s ease 1.3s forwards; }

.hero-heading {
  color: var(--color-cream);
  font-size: clamp(2rem, 4vw, 3.5rem);
  letter-spacing: -0.025em;
  line-height: 1.1;
  margin-bottom: var(--space-sm);
}

.hero-line { display: block; }

.hero-tagline {
  color: var(--color-gold);
  font-family: var(--font-heading);
  font-size: clamp(2rem, 4vw, 3.5rem);
  font-weight: 700;
  letter-spacing: -0.025em;
  line-height: 1.1;
  margin-bottom: var(--space-sm);
}

.hero-sub {
  color: rgba(250, 248, 245, 0.8);
  font-size: clamp(1rem, 2vw, 1.2rem);
  font-weight: 300;
  line-height: 1.75;
  margin: var(--space-md) auto 0;
  max-width: 600px;
}

.hero-cta {
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-sm);
  justify-content: center;
  margin-top: var(--space-lg);
}

.hero-scroll {
  animation: scrollBounce 2s ease-in-out infinite;
  bottom: 2rem;
  left: 50%;
  position: absolute;
  transform: translateX(-50%);
  z-index: 3;
}

/* ==============================
   STATS STRIP
   ============================== */
.stats-strip {
  background-color: var(--color-navy-deep);
  border-top: 1px solid rgba(201, 168, 76, 0.2);
  padding-block: var(--space-lg);
}

.stats-grid {
  display: grid;
  gap: var(--space-md);
  grid-template-columns: repeat(2, 1fr);
}

.stat-item {
  border-right: 1px solid rgba(250, 248, 245, 0.08);
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
  padding-inline: var(--space-md);
  text-align: center;
}

.stat-item:last-child {
  border-right: none;
}

.stat-value {
  color: var(--color-gold);
  font-family: var(--font-heading);
  font-size: clamp(1.5rem, 3vw, 2.25rem);
  font-weight: 900;
  letter-spacing: -0.01em;
  line-height: 1;
  text-shadow: 0 0 1px rgba(201, 168, 76, 0.3);
}

.stat-label {
  color: rgba(250, 248, 245, 0.65);
  font-size: var(--fs-small);
  letter-spacing: 0.03em;
  line-height: 1.4;
}

/* ==============================
   SERVICES TEASER
   ============================== */
.section-intro { margin-bottom: var(--space-lg); }

.services-cards {
  display: grid;
  gap: var(--space-md);
  grid-template-columns: 1fr;
}

.service-card {
  background-color: var(--color-white);
  border: 1px solid var(--color-grey-light);
  border-radius: var(--radius-md);
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  overflow: hidden;
  padding: var(--space-lg) var(--space-md);
  position: relative;
  transition: box-shadow var(--transition-base), transform var(--transition-base), border-color var(--transition-base);
}

.service-card::after {
  background: linear-gradient(to right, var(--color-gold), var(--color-gold-light));
  bottom: 0;
  content: '';
  height: 3px;
  left: 0;
  position: absolute;
  right: 0;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.38s ease;
}

.service-card:hover {
  border-color: rgba(201, 168, 76, 0.3);
  box-shadow: var(--shadow-lg);
  transform: translateY(-4px);
}

.service-card:hover::after { transform: scaleX(1); }

.service-card-icon {
  align-items: center;
  background-color: rgba(201, 168, 76, 0.1);
  border-radius: var(--radius-md);
  color: var(--color-gold);
  display: flex;
  height: 60px;
  justify-content: center;
  width: 60px;
}

.service-card-title {
  color: var(--color-navy-deep);
  font-family: var(--font-heading);
  font-size: var(--fs-h3);
  margin-top: 0.25rem;
}

.service-card-desc {
  color: var(--color-grey-dark);
  font-size: var(--fs-body);
  flex: 1;
  line-height: 1.7;
}

.service-card-link {
  align-items: center;
  color: var(--color-gold);
  display: inline-flex;
  font-size: var(--fs-small);
  font-weight: 600;
  gap: 0.375rem;
  letter-spacing: 0.04em;
  margin-top: auto;
  text-transform: uppercase;
  transition: gap var(--transition-fast), color var(--transition-fast);
}

.service-card-link:hover {
  color: var(--color-navy-deep);
  gap: 0.625rem;
}

/* ==============================
   WHY ZENITH BLAZEE
   ============================== */
.why-section { position: relative; overflow: hidden; }

.why-bg {
  background: radial-gradient(circle, rgba(201, 168, 76, 0.06) 0%, transparent 65%);
  height: 600px;
  pointer-events: none;
  position: absolute;
  right: -5%;
  top: -10%;
  width: 600px;
}

.why-intro { margin-bottom: var(--space-lg); }

.why-grid {
  display: grid;
  gap: var(--space-md);
  grid-template-columns: 1fr;
}

.why-card {
  background-color: rgba(250, 248, 245, 0.04);
  border: 1px solid rgba(201, 168, 76, 0.12);
  border-radius: var(--radius-md);
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  padding: var(--space-md);
  position: relative;
  transition: background-color var(--transition-base), border-color var(--transition-base), transform var(--transition-base);
}

.why-card:hover {
  background-color: rgba(201, 168, 76, 0.06);
  border-color: rgba(201, 168, 76, 0.3);
  transform: translateY(-3px);
}

.why-card::before {
  background: linear-gradient(to right, var(--color-gold), var(--color-gold-light));
  bottom: 0;
  content: '';
  height: 2px;
  left: 0;
  position: absolute;
  right: 0;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.38s ease;
}

.why-card:hover::before { transform: scaleX(1); }

.why-icon {
  align-items: center;
  background-color: rgba(201, 168, 76, 0.12);
  border-radius: var(--radius-md);
  color: var(--color-gold);
  display: flex;
  height: 52px;
  justify-content: center;
  width: 52px;
}

.why-title {
  color: var(--color-cream);
  font-family: var(--font-heading);
  font-size: var(--fs-h4);
}

.why-desc {
  color: rgba(250, 248, 245, 0.65);
  font-size: var(--fs-body);
  line-height: 1.7;
}

/* ==============================
   FAQ
   ============================== */
.faq-inner {
  align-items: start;
  display: grid;
  gap: var(--space-xl);
  grid-template-columns: 1fr;
}

.faq-list {
  display: flex;
  flex-direction: column;
  gap: 0;
  border: 1px solid var(--color-grey-light);
  border-radius: var(--radius-md);
  overflow: hidden;
}

.faq-item {
  border-bottom: 1px solid var(--color-grey-light);
  transition: background-color var(--transition-fast);
}

.faq-item:last-child { border-bottom: none; }

.faq-item--open { background-color: rgba(201, 168, 76, 0.03); }

.faq-question {
  align-items: center;
  cursor: pointer;
  display: flex;
  font-family: var(--font-body);
  font-size: var(--fs-body);
  font-weight: 600;
  gap: var(--space-sm);
  justify-content: space-between;
  min-height: 64px;
  padding: var(--space-md);
  text-align: left;
  width: 100%;
  color: var(--color-charcoal);
  transition: color var(--transition-fast);
}

.faq-question:hover { color: var(--color-navy-deep); }

.faq-item--open .faq-question { color: var(--color-navy-deep); }

.faq-chevron {
  color: var(--color-gold);
  flex-shrink: 0;
  transition: transform var(--transition-base);
}

.faq-item--open .faq-chevron { transform: rotate(180deg); }

.faq-answer {
  color: var(--color-grey-dark);
  font-size: var(--fs-body);
  line-height: 1.75;
  max-height: 0;
  overflow: hidden;
  padding-inline: var(--space-md);
  transition: max-height 0.38s ease, padding 0.28s ease;
}

.faq-item--open .faq-answer {
  max-height: 300px;
  padding-bottom: var(--space-md);
}

.faq-answer p { padding-top: 0; }

/* ==============================
   PARTNERS
   ============================== */
.partners-grid {
  display: grid;
  gap: var(--space-md);
  grid-template-columns: 1fr;
  margin-top: var(--space-lg);
}

.partner-card {
  align-items: flex-start;
  background-color: var(--color-white);
  border: 1px solid var(--color-grey-light);
  border-radius: var(--radius-md);
  display: flex;
  flex-direction: column;
  gap: var(--space-md);
  padding: var(--space-lg) var(--space-md);
  transition: box-shadow var(--transition-base), transform var(--transition-base);
}

.partner-card:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-3px);
}

.partner-avatar {
  align-items: center;
  border: 2px solid rgba(201, 168, 76, 0.25);
  border-radius: var(--radius-full);
  color: var(--color-navy-deep);
  display: flex;
  flex-shrink: 0;
  font-family: var(--font-heading);
  font-size: 1.3rem;
  font-weight: 700;
  height: 72px;
  justify-content: center;
  letter-spacing: 0.05em;
  width: 72px;
}

.partner-card-name {
  color: var(--color-navy-deep);
  font-family: var(--font-heading);
  font-size: var(--fs-h4);
  margin-bottom: 0.2rem;
}

.partner-card-role {
  font-size: var(--fs-small);
  font-weight: 600;
  letter-spacing: 0.06em;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
}

.partner-card-bio {
  color: var(--color-grey-dark);
  font-size: var(--fs-body);
  line-height: 1.7;
}

.partners-cta {
  display: flex;
  justify-content: center;
  margin-top: var(--space-lg);
}

/* ==============================
   CTA STRIP
   ============================== */
.cta-strip {
  overflow: hidden;
  padding-block: var(--space-2xl);
  position: relative;
  text-align: center;
}

.cta-strip-bg {
  background:
    radial-gradient(ellipse at 0% 100%, rgba(201, 168, 76, 0.12) 0%, transparent 55%),
    radial-gradient(ellipse at 100% 0%, rgba(201, 168, 76, 0.08) 0%, transparent 50%);
  inset: 0;
  pointer-events: none;
  position: absolute;
}

.cta-strip-top-line {
  background: linear-gradient(to right, transparent, var(--color-gold), transparent);
  height: 1px;
  left: 50%;
  position: absolute;
  top: 0;
  transform: translateX(-50%);
  width: 120px;
}

.cta-strip-inner {
  position: relative;
  z-index: 1;
}

.cta-heading {
  font-size: var(--fs-h2);
  margin-bottom: var(--space-sm);
}

.cta-sub {
  color: rgba(250, 248, 245, 0.7);
  font-size: var(--fs-body-lg);
  margin-bottom: var(--space-lg);
}

/* ==============================
   RESPONSIVE
   ============================== */
@media (min-width: 480px) {
  .stats-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (min-width: 600px) {
  .services-cards {
    grid-template-columns: 1fr 1fr;
  }

  .partners-grid {
    grid-template-columns: 1fr 1fr;
  }

  .partner-card {
    flex-direction: row;
  }
}

@media (min-width: 768px) {
  .faq-inner {
    grid-template-columns: 1fr 1.5fr;
  }

  .why-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 1024px) {
  .why-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
