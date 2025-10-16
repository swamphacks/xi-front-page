<script lang="ts">
	import Hippodrome from '$lib/assets/Hippodrome.png';
	import Harn from '$lib/assets/Harn.png';
	import Cade from '$lib/assets/Cade.png';
	import Museum from '$lib/assets/Museum.png';
	import ClickableBuilding from './ClickableBuilding.svelte';
	import FAQModal from './FAQModal.svelte';

	let showModal = $state(false);
	let modalTitle: string = $state('state');
	let modalFaqs: any[] = $state([]);

	function handleClose() {
		showModal = false;
	}

	function handleOpen(title: string, faqs: any[]) {
		modalTitle = title;
		modalFaqs = faqs;
		showModal = true;
	}

	$effect(() => {
		// This code only runs in the browser when `showModal` changes.
		if (showModal) {
			document.body.classList.add('modal-open');
		}

		// The cleanup function automatically removes the class when the modal closes.
		return () => {
			document.body.classList.remove('modal-open');
		};
	});

	// One of the FAQ Categories, associated with the Hippodrome building
	let generalTitle = 'General';
	let generalFaqs = [
		{
			question: 'What is SwampHacks?',
			answer:
				'SwampHacks is a 36-hour event, where participants collaborate in teams to create solutions, typically in the form of software and hardware projects. Participants can work in teams or individually to develop and build innovative solutions.'
		},
		{
			question: 'Who can participate in SwampHacks?',
			answer: `Students 18 and older and from any university/college are eligible to participate.\n\nStudents from all academic background are highly encouraged to participate. Regardless of your skill/experience level, we welcome all to join and make the most of the event!\n\nAs part of our dedication to the UF community and fostering experiential learning in early computing education, we’ll be releasing more details soon about our application review and acceptance processes.`
		},
		{
			question: 'Do I need to have coding experience to participate?',
			answer:
				'No experience, no problem! We welcome participant of all skill levels. The idea is that throughout the event, we will support you through workshops and mentors available around the clock.'
		},
		{
			question: "It's my first hackathon. Should I apply?",
			answer:
				'Yes! We highly encourage and want first time hackers to apply. We’re dedicated to providing experiential learning opportunities for those early in their computing journey.'
		},
		{
			question: 'How can I prepare for the hackathon?',
			answer:
				'You can prepare by familiarizing yourself with coding languages or tools, you are looking to use/explore, brushing up on project management skills, and collaboration. However, everything you need will be available during the hackathon.'
		},
		{
			question: 'How much does it cost to participate?',
			answer:
				'Nothing! SwampHacks is completely free for all student accepted to the event. However, SwampHacks is unable to cover transportation costs at this time.'
		},
		{
			question: 'Is SwampHacks in-person or virtual?',
			answer:
				'SwampHacks is FULLY in-person! Everything from check-in to judging will occur at our venue. Make sure you are able to attend in-person before registering.'
		}
	];

	// data associated with Cade
	let cadeTitle = 'Event Details';
	let cadeFaqs = [
		{
			question: 'How long is SwampHacks?',
			answer:
				'SwampHacks will be 36-hours beginning Friday (January 23rd) evening and going until Sunday (January 25th) afternoon.'
		},
		{
			question: 'What can I build?',
			answer:
				'Anything from a chill video game for you and your friends, to a supercharged sofa go kart! You have 36 hours to make something a reality, so make it count.\n\nIt is important to note that your project does not have to be fully developed as you will be allowed to present *prototypes* for the product idea that you have developed.'
		},
		{
			question: 'Will hardware be provided?',
			answer:
				'Yes. We will have a hardware desk with a variety of devices you can borrow throughout the event. We will release more information about what we’ll have as the event approaches'
		},
		{
			question: 'How does project submission and judging work?',
			answer:
				'To submit your project, we use Devpost and we will provide you the link as we get closer to the event. Judging will follow an expo format, where you will demo your project to the judges who visit your table.'
		}
	];

	// data associated with Harn
	let harnTitle = 'Logistics';
	let harnFaqs = [
		{
			question: 'Is food provided?',
			answer:
				'Yes, meals, snacks, and drinks will be provided throughout the hackathon to help keep you energized.'
		},
		{
			question: 'Do I have to stay the whole time?',
			answer:
				'You are welcome to leave and return to the venue(s) during the hackathon. However, we recommend to stay to maximize your time with your team, mentors, and the community. For overnight, we ask that you limit leaving and returning to the venue due to security.'
		},
		{
			question: 'Are there showers available?',
			answer:
				'There are not showers available inside of our venue(s). However, the J. Wayne Reitz Student Union has showers available on the Lower Level, which you can use during the open hours.'
		},
		{
			question: 'Where can I sleep?',
			answer:
				'If you would like to keep working on your project throughout the night, we will have a venue open to continue your collaboration and work. However, if you plan on sleeping through the night, we recommend that you head back to your place of residence.'
		}
	];

	// data associated with Museum
	let museumTitle = 'Miscellaneous';
	let museumFaqs = [
		{
			question: 'Want to sponsor?',
			answer: 'Please email our finance team, sponsors@swamphacks.com for more information.'
		},
		{
			question: 'Interested in volunteering?',
			answer:
				'On November 17th, we will be having a volunteer/mentor info session. More details will come out as we get closer. See our instagram or discord server for all.'
		},
		{
			question: 'Who can be a mentor?',
			answer:
				'Who? We welcome all who have prior hackathon experience, industry, or can assist those in need with basic project needs.\n\nHow? Sign Up MentorLink'
		},
		{
			question: 'How can I become a judge?',
			answer:
				'We welcome individuals with prior hackathon experience, who are industry professionals or involved in academia. Please email contact@swamphacks.com with the subject “SwampHacks XI Judging Interest”.'
		}
	];
</script>

<div class="flex flex-col justify-center bg-grass-background pb-10">
	<h2 class="text-center font-beachday text-5xl text-white">FAQ</h2>
	<div class="bg-grass-background px-5 py-5">
		<div class="gaps-3 flex flex-row flex-wrap items-stretch justify-center">
			<ClickableBuilding
				src={Hippodrome}
				alt="Hippodrome Building"
				title={generalTitle}
				onClick={() => handleOpen(generalTitle, generalFaqs)}
			/>
			<ClickableBuilding
				src={Cade}
				alt="Cade Building"
				title={cadeTitle}
				onClick={() => handleOpen(cadeTitle, cadeFaqs)}
			/>
			<ClickableBuilding
				src={Harn}
				alt="Harn Building"
				title={harnTitle}
				onClick={() => handleOpen(harnTitle, harnFaqs)}
			/>
			<ClickableBuilding
				src={Museum}
				alt="Museum Building"
				title={museumTitle}
				onClick={() => handleOpen(museumTitle, museumFaqs)}
			/>
		</div>
	</div>
	{#if showModal}
		<FAQModal onClose={handleClose} title={modalTitle} faqs={modalFaqs} />
	{/if}
</div>
