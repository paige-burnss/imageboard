<script lang="ts">

import { AppBar} from '@skeletonlabs/skeleton';
import { SlideToggle, FileButton} from '@skeletonlabs/skeleton';
import { Stepper, Step } from '@skeletonlabs/skeleton';

let value: boolean = false;

import logo from "./images/IMOSHI.png";

function greyOut(e: Event): void { 
    document.getElementById('howTo').style.opacity = 0.5;
}

</script>

<div class="container1 mx-auto justify-content-center align-items-center">
    <div class="name text-center">
        <span class="namespan">I</span>
        <span class="namespan">M</span>
        <span class="namespan">O</span>
        <span class="namespan">S</span>
        <span class="namespan">H</span>
        <span class="namespan">I</span>
    </div>
    <br>
    <div class="card1">
        <section class="p-4 text-center">
            This is a simple image-based bulletin board where anyone can post comments and share images. 
            There are boards dedicated to a variety of topics that you can choose to view. 
            Users do not need to register an account before participating in the community. Feel free to click on a board below that interests you and jump right in!
        </div>

</div>

<div class="container3 mx-auto justify-content-center align-items-center">
    <div class="subtitle">
        <h3> How It Works </h3>
    </div>
    <br>
    <div id="howTo" class="card1">
        <Stepper on:complete={greyOut}>
        <Step>
            <svelte:fragment slot="header">Viewing Boards:</svelte:fragment>
            Boards are overarching, broad topics that you can post under. In order to see boards, scroll down and click the <a class="btn btn-sm variant-filled">See All</a> button next to the Popular Boards title.
            <br><br>
            Then navigate the different boards using the side menu. You can filter certain boards to be on your feed by searching for them and adding them in the side menu with <span class="chip variant-filled">input chips</span>.
            <br><br>
            Under each Board title, you can see all the threads that have been posted within that board, and you can search for ones that peek your interest! 
        </Step>
        <Step>
            <svelte:fragment slot="header">Viewing Threads:</svelte:fragment>
            Threads are posts that cover a specific topic and allow people to reply and interact with the ideas posted. In order to see a specific thread, you can navigate to popular ones from the Popular Threads list below, or you can see them by navigating thorugh the Boards page.
            <br><br>
            You can save threads that you like by clicking the bookmark icon, and they will appear in your Saved Threads list in the side menu.
        </Step>
        <Step>
            <svelte:fragment slot="header">Replying to a Thread:</svelte:fragment>
            To reply to a thread, click the arrow icon and type out your message!
            <br><br>
            You can also report the comment if you see some inappropriate or harmful and threatening language being used. 
            <br><br>
            Lastly, you can share the comment on other platforms if you find something you want to share with a friend!
        </Step>
        <Step>
            <svelte:fragment slot="header">Creating Your Own Thread:</svelte:fragment>
            To create your own thread, click the '+' in the side menu next to boards, and fill out the form. Make sure to add a detailed explanation of you thread that specifies the topic of conversation that you want to lead. You can also add an image to your thread that connects to the topic.
            <br><br>
            Then, get ready to follow the converstation you initiated!!
        </Step>
        <Step>
            <svelte:fragment slot="header">Customizing Settings:</svelte:fragment>
            In the top right corner, there are two buttons that can customize your view of IMOSHI. 
            <br><br>
            The first is a button that allows you to switch the language of the website between English and Swedish. <br>
            <i>Note: This will not change the language of posts that you can see, but will change the labels of certain items throughout the site. </i>
            <br><br>
            The second button changes the mode of the website between light and dark mode. Choose whichever you prefer for the best experience!
        </Step>
    </Stepper>
    </div>
</div>

<div class="container3 mx-auto justify-content-center align-items-center">
    <div class="subtitle">
        <h3> Popular Boards
            <a href="/catalog" class="btn btn-sm variant-filled">See All</a>
        </h3>
    </div>
    
    <div class="card p-4 board">Fitness</div>
    <div class="card p-4 board">Video Games</div>
    <div class="card p-4 board">Memes</div>
    <div class="card p-4 board">Anime</div>
    <div class="card p-4 board">Sports</div>
</div>

<br><br><br><br>

<div class="container3 mx-auto justify-content-center align-items-center">
    <div class="subtitle">
        <h3> Popular Threads
        </h3>
    </div>
</div>

