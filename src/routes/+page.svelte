<script>
    import logo from '$lib/assets/nero.png';
    import gitpic from '$lib/assets/git.jpg';
    import cat_pur_sound from '$lib/assets/cat_purr.mp3';
	import Card from '$lib/components/Card.svelte';


    let cat_pur;

    function playSound(){
        cat_pur.currentTime = 0;
        cat_pur.volume = 1;
        cat_pur.play();
    }

    function stopSound(){
        cat_pur.pause();
        cat_pur.currentTime = 0;
    }



    let works = [
        {
            title: "dotREC",
            description: `execute commads with camera as a trigger, self project so please dont expect much.
learning tkinter and diving a little on the template matching fuctionalities of opencv.`,
            link: "https://github.com/nopan-studio/dotREC",
        },
        {
            title: "AnneTea",
            description: "POS System for AnneTea Tea Shop",
            link: "",
        },
        {
            title: "Goblinsss!",
            description: "Goblinsss! is a fun, fast-paced arcade-style game with pixel art, made by me on my first game jam.",
            link: "https://nopan-studio.itch.io/goblinsss",
        },
    
        {
            title: "Festive!",
            description: "Festive is a short-action, pixel art game by nopan-studio, created for the ScoreSpace Jam #13",
            link: "https://nopan-studio.itch.io/festive",
        },
        {
            title: "Free Ball",
            description: "FreeBall is a neon-infused, experimental 2D arcade game by nopan-studio, crafted as a personal LÖVE project and playable on both Windows and Android",
            link: "https://nopan-studio.itch.io/freeball",
        },
        {
            title: "relapse-rs",
            description: "relapse-rs is a discord bot written in rust and serenity. ",
            link: "https://github.com/nopan-studio/relapse-rs",
        },
        {
            title: "roomColor",
            description: "script that changes your chosen wallpaper based on the room color you are in. ",
            link: "https://github.com/nopan-studio/roomColor",
        },
        {
            title: "PhysicsVectorHTT",
            description: "A Love2d script for Vectors in my physics subject.",
            link: "https://github.com/nopan-studio/PhysicsVectorHTT",
        },
        {
            title: "gemini-api-plugin",
            description: "a small wordpress gemini integration plugin.",
            link: "https://github.com/nopan-studio/gemini-api-plugin",
        },
    ];


</script>

<audio bind:this={cat_pur} src="{cat_pur_sound}"> </audio>

<div class="h-dvh w-full overflow-y-scroll snap-y snap-mandatory">
    <!-- Section 1 -->
    <section class="h-dvh w-full snap-start flex items-center justify-center  bg-gray-50 " id="about">
        <div class="h-screen w-full bg-[radial-gradient(circle,_#d2d2d2_1px,_transparent_1px)] [background-size:54px_54px] flex items-center justify-center p-10"> 
            <div class="flex flex-col items-center relative">
                <div class="w-fit text-center relative">
                    <!-- Absolute image -->
                    <img 
                    alt="The project logo" 
                    src={logo} 
                    on:mouseenter={playSound}
                    on:mouseleave={stopSound}
                    class="absolute top-0 right-10 w-12 h-12 scale-200 hover:scale-300 transition-transform duration-500 ease-out object-contain cursor-grab"
                    />
                    
                    <!-- Absolute text -->
                    <h2 class="absolute top-0 left-0 text-xl font-bold text-gray-900 inconsolata">
                        hello, I am
                    </h2>
                    
                    <!-- Main name -->
                    <h2 class="text-9xl font-black text-orange-600 oswald">
                        nopan
                    </h2>
                    
                    <!-- Subtitle -->
                    <h2 class="text-xl font-bold text-gray-900 inconsolata mt-2 text-right">
                        a dev.
                    </h2>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Section 2 -->
    <section class="h-dvh w-full snap-start flex items-center justify-center bg-gray-100 overflow-hidden" >
        <div class="order-2 flex-1 px-10"> 
            <h1 class="text-orange-600 text-5xl inconsolata font-black">
                About Me
            </h1>
            <p class="mt-4 text-lg text-gray-700 text-justify leading-relaxed">
                &nbsp I am a passionate developer with a knack for creating innovative solutions. With a background in computer science and years of experience in the tech industry, I specialize in building web applications that are both functional and visually appealing. My expertise includes front-end and back-end development, as well as a strong understanding of user experience design. I thrive in collaborative environments and am always eager to learn new technologies and improve my skills.
            </p>
        </div>
        <div class="bg-gray-200 min-h-dvh flex-3 order-1 flex items-center justify-center p-10 relative">
            <img src="{gitpic}" alt="" class="absolute top-70 rounded-4xl"/>        
        </div>
        
        
    </section>
    
    <!-- Section 3 -->
    <section class="h-dvh w-full snap-start flex items-center justify-center " id="works">
       <div class="order-1 flex-1 px-10 w-2"> 
            <h1 class="text-orange-600 text-5xl inconsolata font-black text-center">
                Works
            </h1>
        </div>
        <div class="bg-gray-200 min-h-dvh flex-4 order-1 items-center justify-center ">
            <div class="flex flex-col p-5 gap-5 overflow-y-scroll h-dvh">

                {#each works as work}
                        <Card 
                            title={work.title}
                            description={work.description}
                            link={work.link}
                        />
                {/each}
            </div>
        </div>
    </section>
</div>