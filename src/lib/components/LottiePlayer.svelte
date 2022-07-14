<script lang="ts">
  import { browser } from '$app/env';
  import web, { type AnimationItem } from 'lottie-web';
  import { onMount } from 'svelte';

  export let lotties: any[];

  lotties.forEach((lottie) => console.log('animationData object: ', lottie));

  let i = 0;

  let animations: AnimationItem[] = [];

  let staticAnimations: AnimationItem[] = [];

  if (browser) {
    onMount(() => {
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
        i++;
      }
    });

    for (let animation of animations) {
      console.log('AnimationItem (using animationData): ', animation);
    }
  }
</script>

<div id="lottie" />
