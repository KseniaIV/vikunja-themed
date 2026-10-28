# Gingerbread theme for Vikunja

A holiday userstyle for [Vikunja](https://vikunja.io): a deep evergreen page with faint snow, a candy-cane stripe under the top bar, a baked-gingerbread sidebar with a small gingerbread figure, warm-white cards, cranberry buttons and serif headings. On the overview, the "Last viewed" projects become warmly lit gingerbread-house windows: cream panes, a thin gingerbread frame with piped icing, and a ribbon with a bow. It is one CSS file, applied by the [Stylus](https://add0n.com/stylus.html) browser extension. Nothing is installed on the server, no data is stored, and the stylesheet makes no network requests of its own (all decorations are embedded SVG and gradients).

Tested against **Vikunja 2.7.1**. It relies on Vikunja's own CSS variables and stable class names, so nearby versions will likely work, but check the screenshots after upgrading.

## Install

1. Install Stylus for your browser: [Firefox](https://addons.mozilla.org/firefox/addon/styl-us/) · [Chrome / Edge](https://chromewebstore.google.com/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne).
2. Open the raw file in that browser:
   <https://raw.githubusercontent.com/KseniaIV/vikunja-themed/main/userstyles/gingerbread/gingerbread.user.css>
   Stylus recognises any web address ending in `.user.css` and shows its install page, listing the sites the style applies to. Click **Install style**.
3. Reload Vikunja.

Opening a downloaded copy from disk (`file://`) does nothing unless you first turn on **Allow access to file URLs** for Stylus in your browser's extension settings, so the link above is the simpler route.

### Browser security

This theme does not require disabling Chrome security features or launching Chrome with special command-line flags. Install Stylus through your browser’s official extension store and apply the theme only to your Vikunja address.

Any automation flags visible in development screenshots are part of the testing setup and are not installation instructions.

## Match your instance's address

The style only applies to the addresses listed in its `@-moz-document` line. As shipped it matches the default local setup:

```css
@-moz-document url-prefix("http://127.0.0.1:3456/"), url-prefix("http://localhost:3456/") {
```

For another instance, edit the style in Stylus (Manage → the pencil icon) and replace that line, keeping the trailing slash so it matches the whole site and nothing else:

```css
@-moz-document url-prefix("https://tasks.example.com/") {
```

Several instances can be listed, separated by commas.

## Light and dark

Both are supported. The theme follows Vikunja's own setting (**Settings → General → Theme**: Light, Dark, or Auto). Light is evergreen with warm-white cards; Dark is a darker evergreen with cocoa-brown cards and cream text.

## Make it your own

Everything that defines the look sits in section 1 of the file, `PALETTE AND SURFACES`: the palette, the window frame and ribbon sizes, and the decorations. Decorations are CSS variables holding images; set one to `none` to switch it off, for example:

```css
--gb-snow: none;      /* no snow dots on the page */
--gb-mascot: none;    /* no gingerbread figure under the sidebar */
```

Change the palette there to make another seasonal theme; section 2 (the component rules) does not need to change.

## Remove

Stylus → **Manage** → untick the style's checkbox to switch it off, or click the **×** next to it to delete it. Vikunja returns to its normal look on the next reload; the theme never changed anything on the server.

## Known limitations

- The overview windows show each project's description as a quiet second line (Vikunja already carries it on the card). Open-task counts are not available on the card without extra requests, so they are not shown.
- A few things keep Vikunja's own colours by design: label chips, task colours, project colours (shown as a trim inside the window), and the avatar.
- The theme adds no animation beyond short hover transitions, which are disabled when the system asks for reduced motion. Vikunja's own transitions (menus, modals) are left as they are.
