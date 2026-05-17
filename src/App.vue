<script setup>
import { onMounted } from 'vue'

const actionButtons = [
  { label: 'Paper', icon: '/page_image/paper.png', href: '#' },
  { label: 'arXiv', icon: '/page_image/arxiv.png', href: '#' },
  { label: 'Code', icon: '/page_image/github.png', href: '#' },
  { label: 'Dataset', icon: '/page_image/hug.png', href: '#' },
]

const videos = [
  {
    title: 'Demo Video: Manual Design vs. AuraLuxMuse',
    src: '/video/Manual_AuraLuxMuse.mp4',
  },
  {
    title: 'Demo Video: AuraLuxMuse across Music Styles',
    src: '/video/Music_Styles.mp4',
  },
  {
    title: 'Demo Video: Virtual and Real-world Applications',
    src: '/video/Virtual_Real_World.mp4',
  },
]

const datasetScenarios = [
  {
    title: 'Concert Events',
    description:
      'Live show performances where lighting dynamically adapts to musical structure and timing.',
  },
  {
    title: 'Drama Shows',
    description:
      'Theatrical productions that use lighting to support narrative pacing and emotional emphasis.',
  },
  {
    title: 'Entertainment Art',
    description:
      'Broadcasts, promotional events, and multimedia presentations where lighting builds atmosphere.',
  },
]

const qualitativeExamples = [
  { title: 'Concert Event', image: '/page_image/concert.png' },
  { title: 'Drama Show', image: '/page_image/drama.png' },
  { title: 'Entertainment Art', image: '/page_image/entertain.png' },
]

const realWorldExamples = [
  {
    title: 'Interface of grandMA2 Software',
    image: '/page_image/interface.jpg',
    description:
      'The software suite offers real-time visualization, cue management, and timeline editing for complex lighting shows.',
  },
  {
    title: 'Professional Stage Lighting Fixtures',
    image: '/page_image/fixture.jpg',
    description:
      'Stage fixtures can be grouped into imaging, spotlight, soft light, and floodlight classes according to emitted light morphology.',
  },
]

onMounted(() => {
  document.title = 'AuraLuxMuse - Project Page'

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible')
        }
      })
    },
    {
      threshold: 0.1,
      rootMargin: '0px 0px -50px 0px',
    },
  )

  document.querySelectorAll('.fade-in').forEach((element) => observer.observe(element))
  document.querySelector('.hero')?.classList.add('visible')
})
</script>

<template>
  <div class="page-shell">
    <div class="background-lights" aria-hidden="true">
      <div class="light-beam"></div>
      <div class="light-beam"></div>
      <div class="light-beam"></div>
      <div class="light-beam"></div>
      <div class="light-beam"></div>
    </div>

    <main class="container">
      <section class="hero fade-in">
        <p class="submission-info">Anonymous SIGGRAPH ASIA submission</p>
        <h1>
          AuraLuxMuse: Adaptive Fusion Modeling for Aesthetic Stage Lighting Design
          with Music and Expert Guidance
        </h1>

        <div class="action-buttons">
          <a v-for="button in actionButtons" :key="button.label" :href="button.href">
            <img :src="button.icon" :alt="`${button.label} icon`" />
            <span>{{ button.label }}</span>
          </a>
        </div>
      </section>

      <section
        v-for="video in videos"
        :key="video.title"
        class="panel fade-in"
      >
        <h2 class="section-title">{{ video.title }}</h2>
        <div class="video-frame">
          <video controls preload="metadata" playsinline>
            <source :src="video.src" type="video/mp4" />
            Your browser does not support the video tag.
          </video>
        </div>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Workflow: Traditional vs. AuraLuxMuse</h2>
        <div class="teaser-container">
          <img
            class="teaser-image"
            src="/page_image/teaser.png"
            alt="AuraLuxMuse workflow teaser"
          />
          <p class="caption">
            In the conventional pipeline, designers manually decompose music into artistic
            components, then iteratively align lighting cues and console parameters. AuraLuxMuse
            automates this process through deep audio feature extraction and contrastive
            representation learning, producing lighting parameters that can be delivered to the
            console for real-time aesthetic lighting design.
          </p>
        </div>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Abstract</h2>
        <p class="abstract">
          In this work, we present <strong>AuraLuxMuse</strong>, a system for automated aesthetic
          stage lighting generation that integrates expert knowledge, multimodal representation
          learning, and preference-adaptive modeling. Mimicking traditional design workflows,
          AuraLuxMuse replaces manual expert analysis with deep learning based feature extraction
          and decomposes lighting attributes into structured representations jointly learned
          alongside music features under curated metadata supervision. Two core modules power the
          system: <strong>LAMP</strong> (Lighting-Aligned Music Pretraining), which aligns audio
          and lighting cues via contrastive learning, and <strong>PAMoE</strong> (Preference-
          Adaptive Mixture of Experts), which conditions lighting generation on designer intent
          through a gated ensemble of style-specific expert networks. We also introduce
          <strong>Musilux</strong>, a paired music-lighting dataset covering diverse live
          performance scenarios. Experiments show that AuraLuxMuse produces lighting that is
          visually cohesive, semantically aligned, and artistically expressive.
        </p>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Framework Overview</h2>
        <div class="teaser-container">
          <img class="teaser-image" src="/page_image/pipeline.png" alt="Framework pipeline" />
          <p class="caption">
            Music and lighting data are preprocessed before entering LAMP for contrastive
            alignment. Preference representations are injected through PAMoE to enhance cue
            encoding, while metadata prediction and cue retrieval guide the selection of relevant
            lighting sequences for generation.
          </p>
        </div>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Dataset: Musilux Construction Procedure</h2>
        <div class="teaser-container">
          <img
            class="teaser-image"
            src="/page_image/dataset_procedure.png"
            alt="Musilux construction procedure"
          />
          <p class="caption">
            Music and lighting cues are collected, aligned within and across modalities, and then
            aggregated into the Musilux cue sequence corpus.
          </p>
          <ul class="dataset-list">
            <li v-for="scenario in datasetScenarios" :key="scenario.title">
              <strong>{{ scenario.title }}:</strong> {{ scenario.description }}
            </li>
          </ul>
        </div>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Performance of AuraLuxMuse across Lighting Styles</h2>
        <div class="teaser-container">
          <img
            class="teaser-image"
            src="/page_image/Stage_Demo.png"
            alt="Lighting style demonstration"
          />
          <p class="caption">
            Demonstration of stage configurations across varying levels of color harmony,
            brightness control, and zone distribution.
          </p>
        </div>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Qualitative Results</h2>
        <p class="intro">
          Below are examples of outputs generated by AuraLuxMuse, compared with lighting sequences
          manually designed by human designers.
        </p>
        <div class="stack-grid">
          <article v-for="item in qualitativeExamples" :key="item.title" class="stack-card">
            <img :src="item.image" :alt="item.title" />
            <h3>{{ item.title }}</h3>
          </article>
        </div>
      </section>

      <section class="panel fade-in">
        <h2 class="section-title">Real-World Applications</h2>
        <p class="body-text">
          The implementation uses the stage lighting console provided by MA Lighting. For
          parameter adjustment, cue import, and output operations, AuraLuxMuse integrates with
          grandMA2 for interaction and MA3D for virtual visualization.
        </p>
        <div class="stack-grid">
          <article v-for="item in realWorldExamples" :key="item.title" class="stack-card">
            <img :src="item.image" :alt="item.title" />
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </article>
        </div>
        <p class="body-text">
          Deploying generated lighting sequences on a real stage involves preparing XML files,
          importing them into the console, assigning sequence and timecode to executors, and then
          triggering synchronized playback through the console workflow.
        </p>
      </section>
    </main>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;500;600&display=swap');

:root {
  color-scheme: dark;
  --bg-top: #05070d;
  --bg-middle: #12192d;
  --bg-bottom: #1f1031;
  --panel: rgba(255, 255, 255, 0.08);
  --panel-border: rgba(255, 255, 255, 0.14);
  --text: #f8f3e8;
  --muted: rgba(248, 243, 232, 0.8);
  --gold: #ffd76c;
  --pink: #ff7ba8;
  --blue: #7ed4ff;
  --green: #a8ff93;
}

* {
  box-sizing: border-box;
}

html,
body,
#app {
  margin: 0;
  min-height: 100%;
}

body {
  font-family: 'Inter', sans-serif;
  color: var(--text);
  background:
    radial-gradient(circle at top, rgba(255, 215, 108, 0.12), transparent 30%),
    linear-gradient(150deg, var(--bg-top) 0%, var(--bg-middle) 52%, var(--bg-bottom) 100%);
}

a {
  color: inherit;
  text-decoration: none;
}

code {
  background: rgba(255, 255, 255, 0.12);
  border-radius: 999px;
  padding: 0.12rem 0.5rem;
}

.page-shell {
  position: relative;
  overflow: hidden;
}

.background-lights {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 0;
}

.light-beam {
  position: absolute;
  top: -10vh;
  width: 3px;
  height: 120vh;
  opacity: 0.45;
  transform-origin: top center;
  animation: sweep 9s ease-in-out infinite;
}

.light-beam:nth-child(1) {
  left: 12%;
  background: linear-gradient(to bottom, rgba(255, 123, 168, 0.7), transparent 72%);
}

.light-beam:nth-child(2) {
  left: 30%;
  animation-delay: 1.5s;
  background: linear-gradient(to bottom, rgba(126, 212, 255, 0.7), transparent 72%);
}

.light-beam:nth-child(3) {
  left: 50%;
  animation-delay: 3s;
  background: linear-gradient(to bottom, rgba(255, 215, 108, 0.75), transparent 72%);
}

.light-beam:nth-child(4) {
  left: 70%;
  animation-delay: 4.5s;
  background: linear-gradient(to bottom, rgba(168, 255, 147, 0.7), transparent 72%);
}

.light-beam:nth-child(5) {
  left: 88%;
  animation-delay: 6s;
  background: linear-gradient(to bottom, rgba(255, 170, 102, 0.7), transparent 72%);
}

.container {
  position: relative;
  z-index: 1;
  width: min(1180px, calc(100% - 32px));
  margin: 0 auto;
  padding: 48px 0 72px;
}

.hero,
.panel {
  position: relative;
  border: 1px solid var(--panel-border);
  background: var(--panel);
  backdrop-filter: blur(14px);
  box-shadow: 0 24px 60px rgba(0, 0, 0, 0.28);
}

.hero {
  padding: 72px 28px 56px;
  border-radius: 32px;
  margin-bottom: 32px;
  text-align: center;
  background:
    radial-gradient(circle at top, rgba(255, 215, 108, 0.12), transparent 48%),
    rgba(255, 255, 255, 0.06);
}

.submission-info {
  margin: 0 0 18px;
  color: var(--gold);
  font-size: 0.95rem;
  font-weight: 600;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

h1,
.section-title,
.action-buttons a {
  font-family: 'Orbitron', monospace;
}

h1 {
  margin: 0 auto;
  max-width: 980px;
  font-size: clamp(2.25rem, 4.7vw, 4.15rem);
  line-height: 1.12;
  background: linear-gradient(90deg, var(--gold), var(--pink), var(--blue), var(--green));
  background-size: 300% 300%;
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  animation: gradient-shift 8s ease-in-out infinite;
}

.action-buttons {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 14px;
  margin-top: 34px;
}

.action-buttons a {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 12px 20px;
  border-radius: 999px;
  border: 1px solid rgba(255, 215, 108, 0.38);
  background: rgba(255, 255, 255, 0.08);
  color: var(--gold);
  font-size: 0.92rem;
  letter-spacing: 0.08em;
  transition:
    transform 0.25s ease,
    border-color 0.25s ease,
    background 0.25s ease,
    color 0.25s ease;
}

.action-buttons a:hover {
  transform: translateY(-3px);
  border-color: rgba(255, 215, 108, 0.9);
  background: rgba(255, 215, 108, 0.15);
  color: white;
}

.action-buttons img {
  width: 20px;
  height: 20px;
  padding: 3px;
  border-radius: 6px;
  background: white;
}

.panel {
  margin-top: 28px;
  padding: 42px 28px;
  border-radius: 28px;
}

.panel::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 3px;
  border-radius: 28px 28px 0 0;
  background: linear-gradient(90deg, var(--gold), var(--pink), var(--blue), var(--green));
}

.section-title {
  margin: 0 0 26px;
  text-align: center;
  font-size: clamp(1.55rem, 3vw, 2.2rem);
  color: var(--gold);
}

.video-frame,
.teaser-container,
.stack-card {
  border: 1px solid rgba(255, 255, 255, 0.08);
  background: rgba(255, 255, 255, 0.04);
  border-radius: 22px;
}

.video-frame {
  padding: 20px;
}

.intro,
.body-text,
.abstract,
.caption,
.stack-card p {
  color: var(--muted);
  line-height: 1.85;
}

.intro,
.body-text,
.abstract {
  margin: 0 auto 14px;
  max-width: 960px;
  font-size: 1.08rem;
}

.body-text:last-child {
  margin-bottom: 0;
}

.video-frame video {
  display: block;
  width: 100%;
  border-radius: 16px;
  box-shadow: 0 20px 36px rgba(0, 0, 0, 0.25);
}

.teaser-container {
  padding: 24px;
}

.teaser-image,
.stack-card img {
  display: block;
  width: 100%;
  background: white;
  border-radius: 18px;
  box-shadow: 0 20px 36px rgba(0, 0, 0, 0.25);
}

.caption {
  margin: 20px auto 0;
  font-size: 1.05rem;
}

.abstract strong,
.dataset-list strong {
  color: var(--gold);
}

.dataset-list {
  list-style: none;
  padding: 0;
  margin: 22px 0 0;
}

.dataset-list li {
  margin-top: 14px;
  padding: 14px 16px;
  border-left: 3px solid var(--gold);
  border-radius: 0 14px 14px 0;
  background: rgba(255, 215, 108, 0.08);
  color: var(--muted);
  line-height: 1.75;
}

.stack-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}

.stack-card {
  padding: 22px;
}

.stack-card h3 {
  margin: 18px 0 10px;
  color: var(--gold);
  font-size: 1.3rem;
  text-align: center;
}

.stack-card p {
  margin: 0;
}

.fade-in {
  opacity: 0;
  transform: translateY(32px);
  transition:
    opacity 0.8s ease,
    transform 0.8s ease;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

@keyframes sweep {
  0%,
  100% {
    transform: rotate(-16deg);
  }

  50% {
    transform: rotate(16deg);
  }
}

@keyframes gradient-shift {
  0%,
  100% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }
}

@media (max-width: 720px) {
  .container {
    width: min(100% - 20px, 1180px);
    padding: 20px 0 40px;
  }

  .hero {
    padding: 52px 18px 40px;
    border-radius: 24px;
  }

  .panel {
    padding: 28px 18px;
    border-radius: 24px;
  }

  .teaser-container,
  .video-frame,
  .stack-card {
    padding: 16px;
    border-radius: 18px;
  }

  .action-buttons a {
    width: 100%;
    justify-content: center;
  }

  .intro,
  .body-text,
  .abstract,
  .caption {
    font-size: 1rem;
  }
}
</style>
