<script>

    import "../app.postcss";

    let openMenu = false;
    

    function menu(){
        let list = document.querySelector("ul");                                            

        openMenu = !openMenu;
    }

</script>

<div class="md:p-7 bg-gray-400 h-screen">
    <nav class="px-5 pt-5 bg-white shadow flex md:justify-between rounded-md">
        <div class="md:pb-5">
            <img src="../../" alt="brgy logo" class="h-16 w-16 md:h-20 md:w-20 border-gray-500 border-2 rounded-[50%]">
        </div>
        <div class="w-full flex flex-col ml-2 mb-0 pb-2">
            <div class="w-auto py-5 flex justify-between md:justify-center">
                <span class="md:mb-5 text-md md:text-2xl md:text-center font-[Poppins]">Barangay Appointment and Request System</span>

                <button class="md:hidden block" on:click={menu}>
                    {#if !openMenu} 

                    <div class="w-5 h-1 bg-gray-500 mb-1"></div>

                    <div class="w-5 h-1 bg-gray-500 mb-1"></div>

                    <div class="w-5 h-1 bg-gray-500"></div>

                    {:else}
                    <div class="w-5 h-1 bg-gray-500 rotate-45"></div>

                    <div class="w-5 h-1 bg-gray-500 ] translate-y-[-4px] rotate-[135deg]"></div>
                    {/if}

                </button>
            </div>
            <button on:click={menu}>
                <ul id="navlist" class="mt-8 md:mt-0 md:flex md:items-center justify-between md:static absolute bg-white left-0 top-16 w-full text-center z-1 py-4 md:py-0  md:opacity-100 transition-all ease-in duration-300 {openMenu ? 'opacity-100' : 'opacity-0'}">
                    <li class="mx-4 my-6 md:my-0">
                        <a href="/" class="text-md md:text-xl md:px-3 md:pt-1 md:bg-gray-400 md:text-gray-800 md:roundedt-md md:hover:text-white hover:text-gray-500 hover:underline md:hover:no-underline duration-75">Homepage</a>
                    </li>
                    <li class="mx-4 my-6 md:my-0">
                        <a href="./docRequest" class="text-md md:text-xl md:px-3 md:pt-1 md:bg-gray-400 md:text-gray-800 md:rounded-t-md md:hover:text-white hover:text-gray-500 hover:underline md:hover:no-underline duration-75">Document Request</a>
                    </li>
                    <li class="mx-4 my-6 md:my-0">
                        <a href="./aptRequest" class="text-md md:text-xl md:px-3 md:pt-1 md:bg-gray-400 md:text-gray-800 md:rounded-t-md md:hover:text-white hover:text-gray-500 hover:underline md:hover:no-underline duration-75">Appointment Booking</a>
                    </li>
                    <li class="mx-4 my-6 md:my-0">
                        <a href="./reqTracker" class="text-md md:text-xl md:px-3 md:pt-1 md:bg-gray-400 md:text-gray-800 md:rounded-t-md md:hover:text-white hover:text-gray-500 hover:underline md:hover:no-underline duration-75">Track Request</a>
                    </li>
                </ul>

            </button>
        </div>
    </nav>
    <main>
        <slot></slot>
    
    </main>
</div>
