<script>
	import earn from '../assets/cards/Earn_new.png';
	import ecosystem_calls from '../assets/cards/ecosystem_calls_new.png';
	import instagrants from '../assets/cards/Instagrants_new.png';
	import alphasquad from '../assets/cards/alphasquad_new.png';
	import build from '../assets/cards/Build_new.png';
	import founders_league from '../assets/cards/founders_league_new.png';
	import IllustrationCard from './common/IllustrationCard.svelte';
	import Modal from './common/Modal.svelte';
	import thunder from '../assets/logos/thunder.svg';
	import Star from './common/Star.svelte';
	import leftlight from '../assets/images/left-light.svg';
	import rightlight from '../assets/images/right-light.svg';
	import toplight from '../assets/images/top-light.svg';
	import top_right_light from '../assets/images/top-right-light.svg';
	import bottomlight from '../assets/images/bottom-light.svg';
	import midlight from '../assets/images/mid-light.png';

	let modalOpen = false;
	let top_content;
	let text;
	let imgurl;
	let points;
	let btnText;
  let btnLink;
	let bullet;

	function openModal(content, _text, _imgurl, _points, _btnText, _btnLink, _bullet) {
		top_content = content;
		text = _text;
		imgurl = _imgurl;
		points = _points;
		btnText = _btnText;
    btnLink = _btnLink;
		bullet = _bullet;
		modalOpen = true;
	}

	function closeModal() {
		modalOpen = false;
	}
</script>

<div
	class="productions-container relative col-span-5 mt-[224px] flex flex-col justify-center text-center"
>
	{#if modalOpen}
		<Modal {imgurl} {text} {top_content} {points} {btnText} {btnLink} on:close={closeModal} />
	{/if}

	<div
		class="absolute h-full bg-images left-1/2 right-1/2 -translate-x-1/2 w-screen flex flex-col lg:flex-row"
	>
		<!-- Mobile -->
		<picture class="block md:hidden">
			<img
				src={midlight}
				alt=""
				loading="lazy"
				style="width: calc(100% + 100px); transform: scale(2.0);"
				class="midlight-sm justify-items-center -mt-[100px] h-[300px] object-cover w-full -mr-[200px] overflow-visible"
			/>
		</picture>

		<!-- Tablet -->
		<picture class="hidden md:block lg:hidden">
			<source media="(min-width: 768px)" />
			<img
				src={toplight}
				alt=""
				loading="lazy"
				class="absolute -mt-[600px] md:mt-0 md:h-[50%] md:w-full md:object-cover md:max-w-full md:overflow-y-visible justify-items-start w-full h-full"
			/>
		</picture>
		<picture class="hidden md:block lg:hidden">
			<source media="(min-width: 768px)" />
			<img
				src={midlight}
				alt=""
				loading="lazy"
				class="midlight justify-items-center -mt-[200px] left-[21%] h-fit"
			/>
		</picture>
		<picture class="hidden md:block lg:hidden">
			<source media="(min-width: 768px)" />
			<img
				src={top_right_light}
				alt=""
				loading="lazy"
				class="absolute justify-items-end w-3/5 scale-150 -mr-[50px] -mt-[100px] right-0 top-0"
			/>
		</picture>
		<picture class="hidden md:block lg:hidden">
			<source media="(min-width: 768px)" />
			<img
				src={bottomlight}
				alt=""
				loading="lazy"
				class="absolute z-10 justify-items-end w-1/2 right-0 h-1/2 -mt-[250px]"
			/>
		</picture>

		<!-- Desktop -->
		<picture class="hidden lg:block">
			<source media="(min-width: 1024px)" />
			<img
				src={leftlight}
				alt=""
				loading="lazy"
				class="leftlight absolute -mt-[62px] justify-items-start lg:w-2/3 lg:h-full lg:left-0"
			/>
		</picture>
		<picture class="hidden lg:block">
			<source media="(min-width: 1024px)" />
			<img
				src={midlight}
				alt=""
				loading="lazy"
				class="midlight absolute justify-items-center top-0 lg:w-[900px] left-[21%] min-[2000px]:left-[32%] w-[900px] h-fit lg:-mt-[192px]"
			/>
		</picture>
		<picture class="hidden lg:block">
			<source media="(min-width: 1024px)" />
			<img
				src={rightlight}
				alt=""
				loading="lazy"
				class="rightlight absolute z-10 justify-items-end w-full lg:w-3/4 lg:right-0 lg:h-full -mt-[222px]"
			/>
		</picture>
	</div>

	<div class="prod-head">
		<p class="font-secondary font-semibold text-xl leading-[22px] text-white relative">superteam</p>

		<div
			class="section-heading relative text-[40px] md:text-[50px] lg:leading-[54px] leading-[44px]"
		>
			productions
		</div>
	</div>
	<div class="flex justify-center items-center mt-[68px] lg:mt-0 all-cards-wrapper">
		<div class="flex flex-col max-w-[240px] sm:max-w-full gap-8 md:grid md:gap-0 cards-container">
			<IllustrationCard
				text="Earn"
				imageUrl={earn}
				class="md:col-start-1 md:row-start-2 md:row-end-4 lg:row-start-1 lg:row-end-3 min-h-[300px] min-w-[240px]"
				on:click={() =>
					openModal(
						'our very own job listing and bounty platform to find every earning opportunity in solana',
						'Earn',
						earn,
						['1,000+ verified user profiles', 'Global pay standards', 'End-to-end bounty management'],
						'Start Earning',
            'https://earn.superteam.fun',
						thunder
					)}
			/>
			<IllustrationCard
				class="md:col-start-1 md:row-start-[8] md:row-end-[10] lg:col-start-3 lg:row-start-1 lg:row-end-3 min-h-[300px] min-w-[240px]"
				text="Idea Bank"
				imageUrl={build}
				on:click={() =>
          window.open('https://build.superteam.fun', '_blank')
        }
			/>
			<IllustrationCard
				class="md:col-start-1 md:row-start-5 md:row-end-7 lg:col-start-2 lg:row-start-2 lg:row-end-5 min-h-[300px] min-w-[240px]"
				text="Instagrants"
				imageUrl={instagrants}
				on:click={() =>
					openModal(
						'get grants to get started with your dream code, content, and community projects from our partners',
						'Instagrants',
						instagrants,
						['application takes less than 2 mins', '$1-$10,000 grants', 'paid out every week'],
						'Apply now!',
            'https://earn.superteam.fun/grants/',
						thunder
					)}
			/>
      <IllustrationCard
        class="md:col-start-2 md:row-start-4 md:row-end-6 lg:col-start-2 lg:row-start-6 lg:row-end-[-1] min-h-[300px] min-w-[240px]"
				text="Superteam Handbook"
				imageUrl={founders_league}
				on:click={() =>{
					window.open('https://docs.superteam.fun/the-superteam-handbook/', '_blank');
				}}
			/>
      <IllustrationCard
				class="md:col-start-2 md:row-start-1 md:row-end-3 lg:col-start-1 lg:row-start-4 lg:row-end-7 min-h-[300px] min-w-[240px]"
				text="Members' Lounge"
				imageUrl={ecosystem_calls}
				on:click={() => {
					window.open('https://x.com/superteam/status/1852284030537900442', '_blank');
				}}
			/>
			<IllustrationCard
        			class="md:col-start-2 md:row-start-7 md:row-end-[6] lg:col-start-3 lg:row-start-4 lg:row-end-7 min-h-[300px] min-w-[240px]"
				text="Fast Track"
				imageUrl={alphasquad}
				on:click={() =>{
					window.open('https://superteam.fun/fast-track/', '_blank');
				}}
					)}
			/>
		</div>
	</div>
</div>

<style>
	.center-text {
		@apply font-primary;
		font-style: normal;
		text-align: center;

		color: #ffffff;
	}

	.cards-container {
		--row-factor: 8px;
		column-gap: 32px;
	}

	@media (min-width: 768px) {
		.cards-container {
			grid-template-columns: repeat(2, 240px);
			grid-template-rows: repeat(
				3,
				calc(5 * var(--row-factor)) calc(32.5 * var(--row-factor)) calc(5 * var(--row-factor))
			);
		}
	}

	@media (min-width: 1024px) {
		.cards-container {
			grid-template-columns: repeat(3, 320px);
			grid-template-rows:
				calc(8 * var(--row-factor)) calc(42 * var(--row-factor)) calc(4 * var(--row-factor))
				calc(4 * var(--row-factor))
				calc(4 * var(--row-factor)) calc(42 * var(--row-factor)) calc(8 * var(--row-factor));
		}
	}

	.midlight {
		z-index: -999;
	}

	.leftlight {
		z-index: -999;
	}
	.rightlight {
		z-index: -999;
	}
	img {
		pointer-events: none;
		-moz-user-select: none;
		-webkit-user-select: none;
		user-select: none;
	}
</style>
