# Imageboard

<h3>Team Members:</h3> 
Mariam J. Ndwatta (spent 100 hours), Alexander Sellström ( spent 100 hours), and Paige Burns ( spent 60 hours)

----

<h3><b>Project Proposal:</b></h3>

Imageboards have been around since 1999 and their appearances have barely changed at all since then. For instance, when in a thread the user is required to press a refresh button to fetch new posts and then scroll down to read them. They also need to install a third party browser extension to keep track of threads they've posted in to see if they've received any replies. This "thread watcher" is also quite primitive. The "catalog" view of active threads on a board is also completely static, requiring a manual refresh to see if there are any new threads or if a thread has been posted in, or "bumped". There's much to improve upon, many events that can be communicated with animations, making for a suitable project for this course.  We want to create an  imageboard web based application, where a user is able to search and  filter  visual content. A user has the ability to upload a variety of content and connect with the community and other visitors on the site by viewing, creating and  replying in threads/comments. It should be easy for the user to be able to also search through and keep track of their own thread, following discussion within a given thread. The interface should make it possible for any visitors/users to easily upload content and make it easy to integrate with the rest of the world. 

## Installing dependencies

Install Rust. Follow the instructions for your operating system here: https://tauri.app/v1/guides/getting-started/prerequisites


Install dependencies with `npm install` (or `pnpm install` or `yarn`)


If the above command didn't install `tauri-cli` (verify with `cargo tauri --version`) install it by running `cargo install tauri-cli`(to build from source)


Alternatively, `tauri-cli` can also be installed from a pre-built binary with any of the following commands:


`npm add -D @tauri-apps/cli`


`yarn add -D @tauri-apps/cli`


`pnpm add -D @tauri-apps/cli`


## Building and running

Simply run `cargo tauri dev` to run the application. The application is best viewed in a slightly wider window than the one that pops up.


## Limitations

Due to working with an immature tech stack and ecosystems, we were not able to connect the back-end, and the dictionary part in order to be able to switch lagauges.
There are still things remaining to fix in order to have all the linkings which we originally planned, in the different views. 
There also have certain limitations hen it comes to the scaling of different views.
For example today our application does not fully well scale well on a mobile device(there are soem spacing errors to go through in order to ensure that the scaling is flawless ). 