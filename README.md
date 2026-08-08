# Sandy Babbepalli — Personal Site

Static single-page site. No build step, no dependencies, no framework.
Open `index.html` in a browser and it runs.

## Structure

    index.html              Everything — markup, CSS, ~25 lines of JS, one file
    assets/
      headshot.jpg          Hero portrait
      sah-poster.jpg        "Something About Him" poster
      sandilya-babbepalli-resume.pdf
      logos/                (empty) company logos for the logo wall

## How the placeholder system works

Some image slots are intentionally empty. Each contains an `<img>` plus a text
label; a script at the bottom of `index.html` hides the image when the file is
missing so the label shows instead. Files can be added one at a time and
nothing ever looks broken.

Filenames the page looks for:

  assets/logos/    usc-marshall.svg, amex.svg, mckesson.svg, asu.svg, hkdl.svg,
                   carbon-silicon.svg, flick.svg, crossroads.svg,
                   usc-athletics.svg, ddc.svg
                   (currently render as typographic wordmarks, which arguably
                   beat 10 mismatched corporate logos — compare before swapping)

  assets/          duffy.jpg, cinelytics.jpg, usc-athletics.jpg, amex.jpg,
                   carbon-silicon.jpg, soda-with-sandy.jpg   (project cards)

## Design notes

- Colors are CSS custom properties at the top of the `<style>` block.
  `--flame: #F2603C` is sampled from the film poster and is the only accent.
- CSS Grid throughout. One breakpoint at 920px.
- Section numbers (01–06) are hardcoded in markup; renumber if you reorder.
- `.todo` blocks are working notes, toggled by the bottom-right button.
  Delete the `.todo` divs and the `.toggle` button before going live.

## Adding Instagram videos

Near the bottom of `index.html` there's a `REELS` array. Paste post URLs into it,
one per line, and each becomes a real Instagram player embedded in the page:

    var REELS = [
      'https://www.instagram.com/reel/XXXXXXXXXXX/',
      'https://www.instagram.com/reel/YYYYYYYYYYY/'
    ];

Full URLs or bare shortcodes both work; query strings are stripped. Any number of
entries is fine, the grid reflows. An empty array falls back to tiles that link
out to the profile.

## Known gaps

- Acting reel, Apple Podcasts, LinkedIn, YouTube links are still `#`
- The three Instagram tiles link to the profile, not individual posts
- Years for the India/Australia/Arizona moves aren't filled in
