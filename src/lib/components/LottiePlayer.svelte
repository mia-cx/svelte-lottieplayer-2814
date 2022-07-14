<script lang="ts">
  import { browser } from '$app/env';
  import web, { type AnimationItem } from 'lottie-web';

  export let lotties: any[];

  lotties.forEach((lottie) => console.log('animationData object: ', lottie));

  let i = 0;

  let animations: AnimationItem[] = [];

  let staticAnimations: AnimationItem[] = [];

  if (browser) {
    for (let lottie of lotties) {
      animations.push(
        web.loadAnimation({
          container: document.getElementById('lottie')!,
          loop: true,
          autoplay: true,
          renderer: 'svg',
          animationData: lotties[i],
          name: `${Math.random()}`
        })
      );
    }
    staticAnimations.push(
      web.loadAnimation({
        container: document.getElementById('lottie')!,
        loop: true,
        autoplay: true,
        renderer: 'svg',
        path: '/assets/lottie/intro.json',
        name: 'intro'
      })
    );
    staticAnimations.push(
      web.loadAnimation({
        container: document.getElementById('lottie')!,
        loop: true,
        autoplay: true,
        renderer: 'svg',
        path: '/assets/lottie/headbang.json',
        name: 'headbang'
      })
    );
    staticAnimations.push(
      web.loadAnimation({
        container: document.getElementById('lottie')!,
        loop: true,
        autoplay: true,
        renderer: 'svg',
        path: '/assets/lottie/settle.json',
        name: 'settle'
      })
    );

    for (let animation of animations) {
      console.log('AnimationItem (using animationData): ', animation);
    }
    for (let animation of staticAnimations) {
      console.log('AnimationItem (using path): ', animation);
    }
  }
</script>

<div id="lottie" />
