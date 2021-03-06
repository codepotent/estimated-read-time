# Estimated Read Time

The **Estimated Read Time** plugin for ClassicPress allows you to display expected reading times on your articles and summaries. The average person reads at 200 words per minute, so, that's the default setting. You can change it with a simple filter to suit your own audience and content.

# Settings

There is only a single setting: the reading speed. To change the reading speed, you can use [this filter](https://gist.github.com/johnalarcon/182000894a74486ddee2376c7f2c2f20).

# Usage

To provide the most versatile placement options, the estimated read time display is implemented with a shortcode that is designed to be placed in your _theme template_ files. It may require some experimenting to find just the right templates for your particular theme, but you can try the `content.php`, `single.php`, `archive.php`, and `page.php` templates as a starting point.

Note that the shortcode is designed to work in templates that are **in the loop**, so you won't be able to place the shortcode in, say, your `header.php` or `footer.php` files. See the examples below and place _one or the other_ into your theme's template file(s) where you would like the estimated read time to be displayed.

### Example 1: Minimal template shortcode

`<?php echo do_shortcode('[estimated-read-time words="'.str_word_count(strip_tags($post->post_content)).'"]'); ?>`

### Example 2: Template shortcode with dashicon

`<span class="dashicons dashicons-clock"></span> <?php echo do_shortcode('[estimated-read-time words="'.str_word_count(strip_tags($post->post_content)).'"]'); ?>`

# Important Note on Updating your Theme

If you are using a theme that is a _parent theme_ (as opposed to a _child theme_) you will need to be cautious about updating your theme because the update will overwrite all the theme files. To avoid this, you have several options, as follows. Options are listed in the order of preference.

1. use a child theme and add your shortcodes to your child theme's templates, or
2. use a theme that you built yourself to avoid surprise updates, or
3. carefully copy your shortcodes out of your theme files before updating, then replacing them afterward, or
4. continue using the parent theme, but don't update it.