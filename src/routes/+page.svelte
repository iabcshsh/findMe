<script lang="ts">
	import Scene from '$lib/Scene.svelte';
	import { Canvas } from '@threlte/core';

	import { Skeleton } from '$lib/components/ui/skeleton/index.js';
	import { Button } from '$lib/components/ui/button';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as Carousel from '$lib/components/ui/carousel/index.js';
	import { AspectRatio } from '$lib/components/ui/aspect-ratio/index.js';
	import Bell from 'svelte-radix/Bell.svelte';
	import Check from 'svelte-radix/Check.svelte';
	import { Switch } from '$lib/components/ui/switch/index.js';

	const notifications = [
		{
			title: 'Your call has been confirmed.',
			description: '1 hour ago'
		},
		{
			title: 'You have a new message!',
			description: '1 hour ago'
		},
		{
			title: 'Your subscription is expiring soon!',
			description: '2 hours ago'
		}
	];
</script>

<div class="grid justify-center">
	<!-- <div><Canvas><Scene></Scene></Canvas></div> -->

	<Button href="/find" class="m-1 w-max justify-self-end px-16">find</Button>

	<Carousel.Root class="w-full max-w-5xl sm:max-w-xl md:max-w-3xl lg:max-w-5xl">
		<Carousel.Content>
			{#each Array(5) as _, i (i)}
				<Carousel.Item>
					<div class="p-1">
						<Card.Root>
							<Card.Content class="flex h-full flex-col">
								<AspectRatio ratio={16 / 9} class="my-2">
									<img
										src="https://images.unsplash.com/photo-1588345921523-c2dcdb7f1dcd?w=800&dpr=2&q=80"
										alt="Gray by Drew Beamer"
										class="  h-full
								w-full rounded-md border-2 border-black object-cover"
									/>
								</AspectRatio>

								<Card.Root>
									<Card.Header>
										<Card.Title>Notifications</Card.Title>
										<Card.Description>You have 3 unread messages.</Card.Description>
									</Card.Header>
									<Card.Content class="grid gap-4">
										<div>
											<div class="flex items-center space-x-4">
												<div class="space-y-2">
													<Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" /><Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" /><Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" /><Skeleton class="h-4 w-96" />
													<Skeleton class="h-4 w-96" /><Skeleton class="h-4 w-96" />
												</div>
											</div>
										</div>
									</Card.Content>
									<Card.Footer>
										<Button class="w-full">
											<Check class="mr-2 h-4 w-4" /> Mark all as read
										</Button>
									</Card.Footer>
								</Card.Root>
							</Card.Content>
						</Card.Root>
					</div>
				</Carousel.Item>
			{/each}
		</Carousel.Content>
		<Carousel.Previous />
		<Carousel.Next />
	</Carousel.Root>
</div>

<style></style>
