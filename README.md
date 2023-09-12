# Search my Mastodon Timeline

I love mastodon, but it drives me nuts. One thing that irks me is how you cannot even find that one post that you definitely read yesterday, but when you want to show it to people, you cannot find it any more. It cannot even show me the post that I authored. They sit in the corner of my server, waiting to one day be read, but are buried in a sea of boosts, never to be found ever again.

Enter *project_codename_goes_here*. It can save a local copy of your home timeline and posts under your profile, and supports regex search on them. This is currently a work in progress with rough edges, and more features are not promised and depends on my procrastination schedule.

## Supported platforms
Anywhere you can run WebAssembly. That is, newest versions of Chrome, Chromium-based browsers, and Firefox. For some reason some open-source browsers like Cromite and Vanadium are having a hard time running pyscript which this tool relies on, but Fennec works.

## Usage
Open index.html in a web browser, or visit *github_io_link_goes_here* that is hosted online. Follow these steps:
1. Click `Login`, and it will redirect you to mstdn.social for login. (You can edit the html file for another server)
2. Grant read access to the application. It will give you a authentication code, which you can copy to clipboard.
3. Paste the token in the first text box, and click `Submit auth code`.
4. Click `Get timeline` to test if the tool works. It should grab the first page of your home timeline, and cache and display them. The cache persists between refreshes, but your browser may decide to delete them when you run out of disk space.
5. Click the :small_red_triangle_down: upside-down triangle next to `Crawl batch`. In the menu it displays, click `My home timeline` or `User <textbox>'s profile`. (The other two options don't work yet)
6. Wait for some time. The crawling needs to be less frequent than 1 call per second.
7. Verify the content has been cached by using the dropdown selector to go to pages.
8. Put your regex search term in the second text box, and click `Search`. The first 200 matches should be displayed. Examle search queries:
    - Cat or dog: `(cat|dog)`
    - Cat and dog: `(cat.*dog|dog.*cat)`
    - Related to @user@remote-domain.tld: `@user@domain\.tld`
    - All posts of @user that has the #hash hashtag: `@user.*#hash`
9. You can click the timestamp to open the original post in a new tab.

## Nice-to-haves (no promises)
- [ ] Finish implementing downloading of bookmark and favourites.
- [ ] Complete rework of the UI.
- [ ] More reasonable display of timestamps (and redirect to home server page rather than the remote one), boosts, images, and links.
- [ ] Support other mastodon instances.
- [ ] Error handling.
- [ ] Handling off-line search scenario.
- [ ] Start crawling from / until
- [ ] Search using a more human-readable query format.
- [ ] Highlight search terms.
- [ ] Import / Export of cache files.
- [ ] Issues regarding `asyncio`.


