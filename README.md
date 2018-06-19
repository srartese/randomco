# randomco

> Client input application for Random Co.

## Directions for Running

Download Project or Create Local Repo

Using Terminal or command line CD into project file

Run 'npm init'

Run 'npm run start'


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run start

# build for production with minification
npm run build
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

This was developed using Mac and Visual Studio Code.

## Features and Beyond
If I continued with this project I would have liked to properly handle status codes.  There is not user feedback in the DOM for an unsuccessful post.  It also goes with good coding practice to validate form entries but due to time restraints and learning the new framework there did not allow time for this.

There are also a few functionalities that I would have liked to do in a better way.  The secret UI element was a quick addition for getting the URL updated if needed but it is definetly not the most effecient way.  If I had more time I would have gone with the AJAX config route and looked more into the proper way to handle that.  The other is the using the component life cycles to return back to a screensaver component.  This in retrospect works but it would be more effectient to handle it in a state machine instead of relying on DOM updates and mounting.

Some design in the components could have been done in a better way as well but instead it followed a more simplistic design.


## Other notes
The video used for the screen saver was a open source video provided from the link below
    https://www.videvo.net/video/coloured-smoke-on-white-13/4698/ 

I also ran into the issue of Cross Origin Permission issues and solved this by using a chrome extension called Allow-Control-Allow-Origin.  The issue comes into play when posting from a localhost. 
    

