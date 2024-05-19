<script>
// @ts-nocheck

	import { page } from '$app/stores';
	import logo from '$lib/images/icpnewslogo.webp';
	import github from '$lib/images/github.svg';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Carousel } from 'flowbite-svelte';
</script>

<Navbar class="bg-black">
	<NavBrand href="/">
	  <img src={logo} class="w-20" alt="ICP News" />
	  <span class="self-center whitespace-nowrap text-xl font-semibold text-white">ICP News</span>
	</NavBrand>
	<NavHamburger  />
	<NavUl ulClass="flex flex-col p-4 mt-4 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:text-sm md:font-medium bg-black" divClass="w-full md:block md:w-auto bg-black" nonActiveClass="text-white bg-black" activeClass="text-white bg-black">
	  <NavLi href="/">Home</NavLi>
	  <NavLi href="/about">About</NavLi>
	</NavUl>
  </Navbar>