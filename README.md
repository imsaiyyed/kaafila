# Kaafila website

Static pages for GitHub Pages: the landing page, invite links, the privacy
policy and the data-deletion page (both required by Google Play).

```
index.html      Landing page
j/index.html    Invite page: …/j/?code=ABC234 opens kaafila://join/ABC234
privacy.html    Privacy policy (Play Console → App content → Privacy policy)
delete.html     Data deletion (Play Console → Data safety → Delete account URL)
assets/         Stylesheet, icons
.nojekyll       Serve files as they are
```

## Publish on GitHub Pages

1. Create a public repository, for example `kaafila`, and push the contents of
   this folder to its root (not the `site/` folder itself).
2. In the repository: *Settings → Pages → Build and deployment → Source:
   Deploy from a branch*, branch `main`, folder `/ (root)`. Save.
3. After a minute the site is at `https://<your-user>.github.io/kaafila/`.
   A custom domain can be added on the same settings page.

## Live site

Published at **https://imsaiyyed.github.io/kaafila/**. That address is wired in:

- `Links.siteUrl` in `app/lib/app/links.dart`: the app's invite links, QR
  codes, "Privacy policy" and "Delete my data" point here;
- the absolute `og:image` link previews in `index.html` and `j/index.html`.

If the address ever changes (for example to a custom domain), update both.

In Play Console use https://imsaiyyed.github.io/kaafila/privacy.html as the
privacy policy URL and https://imsaiyyed.github.io/kaafila/delete.html as the
account-deletion URL.

Invite links need the app to handle `kaafila://join/CODE`, which it already
does. All links in these pages are relative, so the site also works from a
sub-path such as `/kaafila/`.
