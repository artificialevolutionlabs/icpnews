<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';

	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Carousel } from 'flowbite-svelte';
	import { Card, Button, Toggle } from 'flowbite-svelte';
  	import { ArrowRightOutline } from 'flowbite-svelte-icons';

	export const images = [
	{
      alt: 'ICPCC 2024: Alien tech Invasion!',
      src: '/images/carousel/icpcc.png',
      title: 'icpcc-2024'
    },
	{
      alt: 'Dominic Williams: Possible Optimizations of NNS Tokenomics',
      src: '/images/carousel/inflation.png',
      title: 'dom-tokenomics'
    }
  ];
  let index = 0;
  /**
	 * @type {{ alt: any; }}
	 */
  let image;
</script>

<svelte:head>
	<title>ICP News</title>
	<meta name="description" content="ICP News" />
</svelte:head>

<div class="flex flex-col w-full p-2 m-2">
	<section class="flex w-full bg-black text-white justify-center p-2 m-2">
		<div class="justify-center">
			<div class="max-w-4xl space-y-4">
			<Carousel {images} duration={3900} let:Indicators on:change={({ detail }) => (image = detail)}>
			<a slot="slide" href="/articles/{images[index]?.title}" target="_blank" let:Slide let:index>
				<Slide image={images[index]} />
			</a>
			</Carousel>
			<div class="w-[800px] rounded h-10 bg-black dark:bg-gray-700 dark:text-white p-2 my-2 text-center">
				{image?.alt}
			</div>
		</div>
		</div>
	</section>

	<section class="flex w-full bg-black text-white justify-center w-full p-2 m-2">
		<div  class="flex md:flex-row flex-col space-y-4 gap-8">
			<Card img="/images/carousel/icpcc.png" class="bg-black text-white border-zinc-900">
				<h5 class="mb-2 text-2xl font-bold tracking-tight text-white">ICPCC 2024: Alien tech Invasion!</h5>
				<p class="mb-3 font-normal text-white leading-tight">The 2024 ICPCC is a global Web3 event celebrating the 3rd mainnet launch anniversary of the ICP.</p>
				<Button href="/articles/icpcc-2024" color="purple">
				  Read more <ArrowRightOutline class="w-6 h-6 ms-2 text-white" />
				</Button>
			</Card>
			<Card img="/images/carousel/inflation.png" class="bg-black text-white border-zinc-900">
			  <h5 class="mb-2 text-2xl font-bold tracking-tight text-white">Dominic Williams: Possible Optimizations of NNS Tokenomics</h5>
			  <p class="mb-3 font-normal text-white leading-tight">Dom is proposing two changes we could make to NNS governance with the aim of optimizing network tokenomics.</p>
			  <Button href="/articles/dom-tokenomics" color="purple">
				Read more <ArrowRightOutline class="w-6 h-6 ms-2 text-white" />
			  </Button>
			</Card>
		  </div>
	</section>
</div>