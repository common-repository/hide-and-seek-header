=== Hide and Seek Header ===
Contributors: mlchaves
Donate link: https://ko-fi.com/marklchaves
Tags: header, avada, themefusion, html, css, animation, hide, javascript, onscroll
Requires at least: 5.3.2
Tested up to: 6.1.1
Stable tag: 1.4.0
Requires PHP: 7.2
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Hide and Seek Header hides the site header on down scroll events for the *Avada* theme.

== Description ==

*Built for Avada by ThemeFusion*

Hide and Seek Header frees up more space for a web page by hiding the sticky header when scrolling down. The sticky header will reappear when scrolling back up to make site navigation easier.

= Features =

* Hides the sticky header on scroll down **only**.
* Option to disable on mobile (devices smaller than 800px wide&mdash;the Avada default).
* Option to enable fade animation on hiding.
* Option to enable landing page mode. The plugin hides the standard header (non-sticky) so only the sticky header displays on scrolling up.
* Option to decrease scroll-up sensitivity. Helpful for reducing flicker on touch screens.
* Super simple install. Two steps and your done.
* Cleans up the database on uninstall.
* Lightweight&mdash;about 30 KB zipped.

== Installation ==

1. Upload the plugin zip file to the `/wp-content/plugins/hide-and-seek-header` directory, or install the plugin through the WordPress plugins screen directly.
1. Activate the plugin through the 'Plugins' screen in WordPress

== Usage ==

Your site must be using Avada by ThemeFusion. The plugin settings are under **Settings > Hide and Seek Header**.

= Disable on Mobile =

By default, the plugin will hide headers for all devices. Check **Disable on mobile?** to keep the header visible on small devices. The current default breakpoint is `800px`. 

Uncheck to hide the header on all devices.

= Enable Animation =

The animation is disabled by default. Check **Enable animation?** to turn on a `0.5 second` fade-out effect when the header begins to disappear.

= Enable Landing Page Mode = 

Check **Landing page mode?**, if you want to hide the standard top header and menu on page load. This is great for minimising distractions.

Click **Save all changes** to save your options.

== Frequently Asked Questions ==

= Will this plugin work for other themes? =

Version 1.0.1 was built for Avada. It hasn't been tested with other themes. Please fork a copy and change it to work for other themes, if wanted.

= Can I change the mobile breakpoint? =

Yes. You can write custom CSS to override the media query for the `.hideandseek-hide-down` class.

= Can I change the default fade-out animation? = 

Yes. You can write custom CSS to override the animation style and timing in the `.hideandseek-hide-down` class.

Below is the CSS it would take to increase the animation duration and responsive breakpoint at the same time.

`
/* Custom disable for devices smaller than 1024px. */
@media screen and (max-width: 1023.998px) {
    .hideandseek-hide-down {
      visibility: visible !important;
      opacity: 1 !important;
      transition: none !important;
    }
}

/* Custom fade increase to 5.5 seconds. */
@media screen and (min-width: 1024px) {
    .hideandseek-hide-down {
      visibility: hidden;
      opacity: 0;
      transition: visibility 5.5s, opacity 5.5s linear !important;
    }
}
`

== Screenshots ==

1. Preview of the plugin in action. Sticky header disappears on scroll down. Reappears on scroll up.
2. Plugin settings page.
3. Landing page mode. No distracting header or menu on page load.
4. Scroll-up sensitivity setting. This will delay the reappear slightly to avoid annoying flicker on touch screens.

== Changelog ==

= 1.4.0 = 
* Removed beta label for sensitivity setting.
* Tested on WordPress 5.7.
* Tested on Avada 7.3.

= 1.3.0 =
* Fixed: If mobile menu is open, large space is left on scroll down.
* Removed extra space left by hidden header on landing page mode. See the associated [GitHub issue](https://github.com/marklchaves/hide-and-seek-header/issues/12) for more details.
* Removed extra space when using slider in parallax mode. However, you'll need too increase height of slider by height of header to off set the negative margin from Avada. E.g., If the height slider image is 849px and the height of header is 84, then the slider's final height should be set to 933px. This is described on the parallax setting and in the Avada docs.
* Could **not** reliably repro active pointer events when header is hidden (even with mega menu). But, disabled pointer events in CSS when header is hidden to be extra sure. See the related [GitHub issue](https://github.com/marklchaves/hide-and-seek-header/issues/11) for more details.
* Tested on Avada 6.2.2 and 6.2.3.

= 1.2.0 =
* Added scroll-up sensitivity to reduce flickering (appear/reappear) of sticky header on touch screens. (beta)
* Refactored admin page so that setting fields line up better.
* Added DB clean up of options on uninstall.

= 1.0.1 = 
* Reverted CSS to original v 0.0.1 code. Version 1.0 CSS for no animation broke formatting for headers 2-5.

= 1.0.0 =
* First release. Tested on Avada 6.2.1 and 6.2.2.

== Upgrade Notice ==

= 1.4.0 =
None

= 1.3.0 =
* Mainly CSS and JavaScript changes. The PHP was updated only for versioning and to enqueue a new CSS file for the landing page fix.

= 1.2.0 =
* Code changes for scroll sensitivity, admin page GUI, and DB uninstall of Hide and Seek Header options.

= 1.0.1 =
* Fix for formatting issue on headers 2-5.

= 1.0.0 =
None

== Disclaimer ==

The Hide and Seek Header plugin and its author are not affiliated with Avada or ThemeFusion in any way.