<script lang="ts">
	import { onMount } from 'svelte';

	let scrollY = 0;
</script>

<svelte:window bind:scrollY />

<div class="font-sans text-gray-900 antialiased selection:bg-primary-100 selection:text-primary-900">
	<!-- Navigation / Header (Implicit in design, maybe just the logo or minimal) -->
	<!-- The screenshot doesn't explicitly show a header bar, but usually there is one. 
         I will assume a minimal or transparent one, or just the content. 
         The "W." ribbon is fixed on the right. -->
    
    <!-- Per Aspera Logo Badge -->
    <div class="fixed top-6 left-6 z-50">
        <a href="/" class="flex items-center gap-2 text-gray-900 hover:text-primary-600 transition-colors">
            <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                <path d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z" fill="currentColor" />
            </svg>
            <span class="font-serif text-xl font-semibold">Per Aspera</span>
        </a>
    </div>

	<!-- Hero Section -->
	<section class="relative min-h-screen w-full bg-gradient-to-b from-gray-950 via-gray-900 to-gray-50 text-white px-6 md:px-12 lg:px-24 pt-32 pb-24 flex flex-col justify-between">
		<div class="max-w-5xl">
			<h1 class="font-serif text-5xl md:text-7xl lg:text-8xl leading-[1.1] md:leading-[1.1] tracking-tight">
				Transforming complex deep tech into accessible narratives through expert editorial curation.
			</h1>
			<p class="mt-8 text-xl md:text-2xl text-gray-300 max-w-3xl">
				Starting with aerospace engineers, we're capturing the $8B technical publishing market with rigorous, peer-reviewed deep tech content.
			</p>
		</div>

		<div class="mt-24 flex gap-4">
			<a href="#publications" class="inline-flex items-center justify-center px-6 py-3 bg-primary-600 text-white rounded-full text-sm font-medium hover:bg-primary-700 transition-colors duration-300">
				Explore Research
			</a>
			<a href="#subscribe" class="inline-flex items-center justify-center px-6 py-3 border border-white/30 rounded-full text-sm font-medium hover:bg-white hover:text-gray-950 transition-colors duration-300 backdrop-blur-sm">
				Subscribe
			</a>
		</div>
	</section>

	<!-- Coverage Areas -->
	<section class="bg-white px-6 md:px-12 lg:px-24 py-16 md:py-24">
		<p class="text-lg md:text-xl text-gray-600 mb-12">Deep tech sectors we cover, from quantum to cosmos</p>
		
		<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-6 md:gap-8">
			{#each [
				{ name: 'Quantum Computing', icon: '⚛️' },
				{ name: 'Aerospace', icon: '🚀' },
				{ name: 'Advanced Materials', icon: '🔬' },
				{ name: 'AI Infrastructure', icon: '🖥️' },
				{ name: 'Biotechnology', icon: '🧬' }
			] as sector}
				<div class="p-6 bg-gray-50 rounded-lg flex flex-col items-center justify-center text-center hover:bg-primary-50 hover:border-primary-200 border border-transparent transition-all duration-300">
					<span class="text-3xl mb-3">{sector.icon}</span>
					<span class="font-medium text-gray-900 text-sm">{sector.name}</span>
				</div>
			{/each}
		</div>
	</section>

    <!-- Featured Publications Section -->
    <section class="bg-gray-50 px-6 md:px-12 lg:px-24 py-12 md:py-24" id="publications">
        <div class="flex flex-col md:flex-row justify-between items-end mb-16 md:mb-24">
            <h2 class="font-serif text-3xl md:text-4xl lg:text-5xl text-gray-900">Featured research and analysis</h2>
            <a href="/publications" class="hidden md:inline-flex items-center text-gray-500 hover:text-gray-900 transition-colors mt-4 md:mt-0">
                See all <span class="ml-2">→</span>
            </a>
        </div>

        <div class="space-y-24 md:space-y-32">
            <!-- Publication 1: Quantum Computing -->
            <div class="group grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                <div class="lg:col-span-4 space-y-6">
                    <h3 class="font-serif text-3xl md:text-4xl text-gray-900">The Quantum Advantage</h3>
                    <p class="text-gray-600 text-lg leading-relaxed">
                        A comprehensive analysis of quantum computing's path to commercial viability, examining hardware architectures, error correction approaches, and the 3-5 year timeline to practical applications in drug discovery and materials science.
                    </p>
                    <div class="flex flex-wrap gap-2 pt-2">
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Quantum Computing</span>
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Deep Dive</span>
                    </div>
                </div>
                <div class="lg:col-span-8">
                    <div class="aspect-[16/9] bg-gray-900 rounded-lg overflow-hidden relative group-hover:scale-[1.02] transition-transform duration-500 ease-out">
                        <img src="/generated/image-close-up-of-quantum-computing-hardware-w-1765496917870-1.webp" alt="Quantum Computing Hardware" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>

            <!-- Publication 2: Advanced Materials -->
            <div class="group grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                <div class="lg:col-span-4 space-y-6">
                    <h3 class="font-serif text-3xl md:text-4xl text-gray-900">Materials Revolution</h3>
                    <p class="text-gray-600 text-lg leading-relaxed">
                        How next-generation composite materials are enabling breakthrough applications in aerospace, energy storage, and sustainable manufacturing. An in-depth look at the science and market dynamics.
                    </p>
                    <div class="flex flex-wrap gap-2 pt-2">
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Advanced Materials</span>
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Market Analysis</span>
                    </div>
                </div>
                <div class="lg:col-span-8">
                    <div class="aspect-[16/9] bg-gray-100 rounded-lg overflow-hidden relative group-hover:scale-[1.02] transition-transform duration-500 ease-out">
                        <img src="/generated/image-advanced-materials-scientist-examining-i-1765496921235-2.webp" alt="Advanced Materials Research" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>

            <!-- Publication 3: Aerospace -->
            <div class="group grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                <div class="lg:col-span-4 space-y-6">
                    <h3 class="font-serif text-3xl md:text-4xl text-gray-900">New Space Economics</h3>
                    <p class="text-gray-600 text-lg leading-relaxed">
                        The technical and financial realities of reusable rocket systems, satellite constellations, and the emerging space economy. A rigorous assessment of propulsion technologies, orbital mechanics, and market opportunities.
                    </p>
                    <div class="flex flex-wrap gap-2 pt-2">
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Aerospace</span>
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Space Technology</span>
                    </div>
                </div>
                <div class="lg:col-span-8">
                    <div class="aspect-[16/9] bg-gray-900 rounded-lg overflow-hidden relative group-hover:scale-[1.02] transition-transform duration-500 ease-out">
                        <img src="/generated/image-rocket-engine-test-firing-with-dramatic--1765496923921-3.webp" alt="Rocket Engine Testing" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>

            <!-- Publication 4: AI Infrastructure -->
            <div class="group grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                <div class="lg:col-span-4 space-y-6">
                    <h3 class="font-serif text-3xl md:text-4xl text-gray-900">AI Infrastructure at Scale</h3>
                    <p class="text-gray-600 text-lg leading-relaxed">
                        Beyond the hype: examining the compute architectures, cooling systems, and power requirements enabling large-scale AI deployment. Technical insights into the physical infrastructure powering the AI revolution.
                    </p>
                    <div class="flex flex-wrap gap-2 pt-2">
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">AI Infrastructure</span>
                        <span class="px-3 py-1 border border-gray-200 rounded-full text-xs font-medium text-gray-600">Technical Analysis</span>
                    </div>
                </div>
                <div class="lg:col-span-8">
                    <div class="aspect-[16/9] bg-gray-950 rounded-lg overflow-hidden relative group-hover:scale-[1.02] transition-transform duration-500 ease-out">
                        <img src="/generated/image-ai-infrastructure-server-room-with-rows--1765496926687-4.webp" alt="AI Infrastructure" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
        
        <div class="mt-12 md:hidden">
            <a href="/publications" class="flex items-center text-gray-500 hover:text-gray-900 transition-colors">
                See all <span class="ml-2">→</span>
            </a>
        </div>
    </section>

    <!-- Editorial Process Section -->
    <section class="bg-white px-6 md:px-12 lg:px-24 py-12 md:py-24">
        <h2 class="font-serif text-3xl md:text-4xl lg:text-5xl text-gray-900 mb-16 max-w-3xl">Our editorial process: rigorous research meets accessible storytelling</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Research -->
            <div class="bg-gray-50 p-8 rounded-xl border border-gray-100 hover:border-primary-200 transition-all duration-300 flex flex-col h-full min-h-[400px]">
                <h3 class="text-xl font-semibold mb-4 text-gray-900">Research</h3>
                <p class="text-gray-600 text-sm leading-relaxed mb-auto">
                    We dive deep into technical papers, patents, and primary sources to understand the fundamental science and engineering behind breakthrough innovations.
                </p>
                <div class="mt-8 flex justify-center h-48 items-end">
                    <img src="/generated/image-researcher-analyzing-complex-data-visual-1765496930104-5.webp" alt="Research Process" class="h-full w-full object-cover rounded-lg" />
                </div>
            </div>

            <!-- Curate -->
            <div class="bg-gray-50 p-8 rounded-xl border border-gray-100 hover:border-primary-200 transition-all duration-300 flex flex-col h-full min-h-[400px]">
                <h3 class="text-xl font-semibold mb-4 text-gray-900">Curate</h3>
                <p class="text-gray-600 text-sm leading-relaxed mb-auto">
                    Expert editors with technical backgrounds evaluate commercial viability, market timing, and strategic implications to surface what truly matters.
                </p>
                <div class="mt-8 flex justify-center h-48 items-end">
                    <img src="/generated/image-editorial-team-collaborating-over-techni-1765496933153-6.webp" alt="Editorial Curation" class="h-full w-full object-cover rounded-lg" />
                </div>
            </div>

            <!-- Publish -->
            <div class="bg-gray-50 p-8 rounded-xl border border-gray-100 hover:border-primary-200 transition-all duration-300 flex flex-col h-full min-h-[400px]">
                <h3 class="text-xl font-semibold mb-4 text-gray-900">Publish</h3>
                <p class="text-gray-600 text-sm leading-relaxed mb-auto">
                    We transform complex technical concepts into clear, compelling narratives that maintain rigor while reaching decision-makers and strategic thinkers.
                </p>
                <div class="mt-8 flex justify-center h-48 items-end">
                    <img src="/generated/image-professional-publishing-workspace-with-p-1765496936030-7.webp" alt="Publishing Process" class="h-full w-full object-cover rounded-lg" />
                </div>
            </div>
        </div>
    </section>

    <!-- Latest Insights Section -->
    <section class="bg-gray-50 px-6 md:px-12 lg:px-24 py-12 md:py-24">
        <div class="flex flex-col md:flex-row justify-between items-end mb-12">
            <h2 class="font-serif text-3xl md:text-4xl text-gray-900">Latest insights and analysis</h2>
            <a href="/insights" class="hidden md:inline-flex items-center text-gray-500 hover:text-gray-900 transition-colors mt-4 md:mt-0">
                Read all <span class="ml-2">→</span>
            </a>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Article 1 -->
            <div class="group cursor-pointer">
                <div class="aspect-square bg-gradient-to-br from-primary-600 to-primary-800 rounded-lg overflow-hidden mb-4 relative">
                     <div class="absolute inset-0 flex items-center justify-center text-white font-bold text-2xl text-center p-8">
                        <div>
                            <div class="text-sm uppercase tracking-wider mb-2 opacity-80">Technical Deep Dive</div>
                            <div class="font-serif text-3xl">Quantum Error Correction</div>
                        </div>
                     </div>
                </div>
                <h3 class="text-sm font-medium text-gray-900 group-hover:underline">Breaking Down the Path to Fault-Tolerant Quantum Computing</h3>
            </div>

             <!-- Article 2 -->
             <div class="group cursor-pointer">
                <div class="aspect-square bg-gray-900 rounded-lg overflow-hidden mb-4 relative">
                    <div class="absolute inset-0 flex items-center justify-center text-white p-8 flex-col">
                        <span class="text-6xl mb-4">🚀</span>
                        <span class="text-xl font-serif text-center">Reusable Rockets</span>
                    </div>
                </div>
                <h3 class="text-sm font-medium text-gray-900 group-hover:underline">The Economics of Orbital Launch: A Technical and Financial Analysis</h3>
            </div>

             <!-- Article 3 -->
             <div class="group cursor-pointer">
                <div class="aspect-square bg-gradient-to-br from-gray-800 to-gray-950 rounded-lg overflow-hidden mb-4 relative">
                     <div class="absolute inset-0 flex items-center justify-center text-white text-center p-8 flex-col">
                        <span class="text-sm uppercase tracking-widest mb-3 opacity-70">Market Intelligence</span>
                        <span class="text-2xl font-serif leading-tight">Advanced Battery Chemistry</span>
                     </div>
                </div>
                <h3 class="text-sm font-medium text-gray-900 group-hover:underline">Solid-State Batteries: Technical Hurdles and Commercial Timeline</h3>
            </div>

             <!-- Article 4 -->
             <div class="group cursor-pointer">
                <div class="aspect-square bg-primary-950 rounded-lg overflow-hidden mb-4 relative">
                    <div class="absolute inset-0 flex items-center justify-center text-primary-100 p-8">
                        <div class="text-center">
                            <div class="text-4xl font-bold mb-2">AI</div>
                            <div class="text-sm uppercase tracking-wider">Infrastructure</div>
                        </div>
                    </div>
                </div>
                <h3 class="text-sm font-medium text-gray-900 group-hover:underline">The Hidden Costs of Training Large Language Models</h3>
            </div>

             <!-- Article 5 -->
             <div class="group cursor-pointer">
                <div class="aspect-square bg-gradient-to-br from-primary-700 to-primary-900 rounded-lg overflow-hidden mb-4 relative flex items-center justify-center">
                    <div class="text-white text-center p-8">
                        <div class="text-5xl mb-4">⚛️</div>
                        <div class="text-xl font-serif">Fusion Energy</div>
                        <div class="text-xs mt-2 opacity-70 uppercase tracking-wider">Progress Report</div>
                    </div>
                </div>
                <h3 class="text-sm font-medium text-gray-900 group-hover:underline">Fusion Reactor Designs: Comparing Tokamak, Stellarator, and Inertial Confinement</h3>
            </div>

             <!-- Article 6 -->
             <div class="group cursor-pointer">
                <div class="aspect-square bg-gray-950 rounded-lg overflow-hidden mb-4 relative">
                     <div class="absolute inset-0 flex items-center justify-center text-white p-8 text-center">
                        <div>
                            <div class="text-3xl font-serif mb-2">Photonic Computing</div>
                            <div class="text-xs uppercase tracking-widest opacity-70">Technical Assessment</div>
                        </div>
                     </div>
                </div>
                <h3 class="text-sm font-medium text-gray-900 group-hover:underline">Light-Based Computing: Beyond the Silicon Limit</h3>
            </div>
        </div>
    </section>

    <!-- Newsletter Section -->
    <section class="px-6 md:px-12 lg:px-24 py-12" id="subscribe">
        <div class="bg-gradient-to-br from-gray-900 to-gray-950 rounded-2xl p-8 md:p-16 lg:p-20">
            <h3 class="font-serif text-2xl md:text-3xl text-white mb-4">Deep tech insights delivered monthly</h3>
            <p class="text-gray-300 mb-8 max-w-md">Join 50,000+ engineers, founders, and investors who rely on Per Aspera for rigorous technical analysis and market intelligence.</p>
            
            <form class="flex flex-col sm:flex-row gap-4 max-w-lg">
                <input type="email" placeholder="engineer@company.com" class="flex-1 bg-white/10 border border-white/20 rounded-lg px-4 py-3 text-sm placeholder:text-gray-400 text-white focus:ring-2 focus:ring-primary-500 outline-none" />
                <button type="submit" class="bg-primary-600 hover:bg-primary-700 transition-colors text-white px-6 py-3 rounded-lg text-sm font-medium">
                    Subscribe
                </button>
            </form>
            <p class="text-[10px] text-gray-400 mt-4">We respect your inbox. By subscribing, you agree to receive research updates from Per Aspera. Read our Privacy Policy.</p>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="relative bg-gradient-to-b from-gray-900 via-gray-950 to-black pt-32 pb-48 px-6 md:px-12 lg:px-24 overflow-hidden">
        <div class="max-w-5xl relative z-10">
            <h2 class="font-serif text-4xl md:text-6xl lg:text-7xl text-white leading-tight mb-8">
                Access the research that matters. <br />
                <span class="text-gray-400">Deep technical analysis, market intelligence, and strategic insights for decision-makers navigating breakthrough technologies.</span>
            </h2>
            
            <div class="mt-16 flex gap-4">
                 <a href="/subscribe" class="inline-flex items-center justify-center px-6 py-3 bg-primary-600 rounded-full text-sm font-medium text-white hover:bg-primary-700 transition-colors duration-300">
                    Start Free Trial
                </a>
                 <a href="/about" class="inline-flex items-center justify-center px-6 py-3 border border-white/30 rounded-full text-sm font-medium text-white hover:bg-white hover:text-gray-950 transition-colors duration-300 backdrop-blur-sm">
                    Learn More
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-black text-gray-300 px-6 md:px-12 lg:px-24 pt-24 pb-12 relative overflow-hidden">
        
        <div class="relative z-10">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-12 mb-24">
                <div class="col-span-1 md:col-span-2">
                    <a href="/contact" class="text-2xl font-medium hover:text-primary-400 transition-colors inline-flex items-center text-white">
                        Partner with us <span class="ml-2">→</span>
                    </a>
                    <p class="mt-4 text-gray-400 max-w-md">
                        Interested in contributing research, sponsoring content, or accessing our premium intelligence? Let's talk.
                    </p>
                </div>
                
                <div class="space-y-4">
                    <h4 class="font-medium text-white">Contact</h4>
                    <div class="text-sm space-y-2">
                        <p><a href="mailto:research@peraspera.io" class="hover:text-primary-400 transition-colors">research@peraspera.io</a></p>
                        <p><a href="mailto:partnerships@peraspera.io" class="hover:text-primary-400 transition-colors">partnerships@peraspera.io</a></p>
                    </div>
                </div>
            </div>

            <div class="flex flex-col md:flex-row justify-between items-end border-t border-white/10 pt-8">
                <div class="mb-4 md:mb-0">
                    <!-- Per Aspera Logo -->
                    <div class="flex items-center gap-2">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-500">
                            <path d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z" fill="currentColor" />
                        </svg>
                        <span class="font-serif text-lg font-semibold text-white">Per Aspera</span>
                    </div>
                </div>
                
                <div class="flex gap-6 text-xs font-medium">
                    <a href="#" class="hover:text-primary-400 transition-colors">LinkedIn</a>
                    <a href="#" class="hover:text-primary-400 transition-colors">Twitter</a>
                    <a href="#" class="hover:text-primary-400 transition-colors">RSS</a>
                    <a href="#" class="hover:text-primary-400 transition-colors">Careers</a>
                </div>
            </div>

            <div class="flex flex-col md:flex-row justify-between text-[10px] opacity-50 mt-12 gap-4">
                <p>© 2025 Per Aspera. All rights reserved.</p>
                <div class="flex gap-4">
                    <a href="/privacy" class="hover:opacity-100 transition-opacity">Privacy Policy</a>
                    <a href="/terms" class="hover:opacity-100 transition-opacity">Terms of Service</a>
                </div>
            </div>
        </div>
    </footer>
</div>

<style>
    /* Custom utility for vertical writing mode */
    .writing-vertical-rl {
        writing-mode: vertical-rl;
    }
</style>

