# Testing HTML

You should have already tested your Spice triggers by following the [Testing triggers](https://github.com/duckduckgo/duckduckgo#testing-triggers) section. Once you're confident your triggers are functioning properly, follow these steps to see your Spice instant answer on a live server!

1. Go to the root of your forked repository.

  ```shell
  cd zeroclickinfo-spice/
  ```

2. Start the server.

  ```shell
  duckpan server
  ```

  This command will start up a small Web server running on port 5000 on your machine.

3. Visit the server in your browser.

  You should now be able to go to your duckpan server via a regular Web browser and check it out. It runs code from our site and so generally looks like a real version of DuckDuckGo. 

  If you're running the duckpan server on the same computer as your Web browser you can navigate to:

  ```shell
  http://127.0.0.1:5000/
  ```

  If you're running the duckpan server on a remote machine, then substitute 127.0.0.1 with either its IP address or its Fully Qualified Domain Name.

4. Search.

  Given you've already tested your instant answer's triggers, you should be able to search and see your spice output come through the server. As requests go through the internal Web server, they are printed to STDOUT (on the screen). External API calls are highlighted (if you have color turned on in your terminal).

5. Debug.

  If for some reason a search doesn't hit an instant answer, there is an error message displayed on the homepage saying "Sorry, no hit for your instant answer." 

  If it does hit and you do not see something displayed on the screen, a number of things could be going wrong.

  - You have a JavaScript error of some kind. Check out the JavaScript console for details. Personally we like to use [Firebug](http://getfirebug.com/) internally.

  - The external API was not called correctly. You should be able to examine the Web server output to make sure the right API is being called. If it's not you will need to revise your [Spice handle function](#spice-handle-functions).

  - The external API did not return anything. Firebug is great for checking this as well. You should see the call in your browser and then you can examine the response.


6. Tweak the display.

  Once everything is working properly (and you have stuff displayed on screen), you will want to mess with your callback function to get the display nice and perfect. Check out the [Guidelines](https://github.com/duckduckgo/duckduckgo#guidelines) for some pointers.

7. Document. 

  Finally, please document as much as possible using in-line comments.
