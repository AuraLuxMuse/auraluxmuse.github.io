# AuraLuxMuse project page

Static site, ready for GitHub Pages (index.html at the root, .nojekyll included).

- Code / Dataset buttons: search index.html for "CODE LINK" and "DATASET LINK", set the href, remove class="soon".
- Demo videos: put Manual_AuraLuxMuse.mp4, Music_Styles.mp4, Virtual_Real_World.mp4 in videos/.
  A video section stays hidden until its file exists. Keep each file under 100 MB (GitHub limit);
  e.g. ffmpeg -i in.mp4 -c:v libx264 -crf 26 -preset veryfast -c:a aac -b:a 128k -movflags +faststart out.mp4
- Custom domain: add a file named CNAME containing e.g. auraluxmuse.example.com, and at your DNS provider
  add a CNAME record  auraluxmuse -> <github-username>.github.io
- Fonts Inter and Orbitron are self-hosted (SIL OFL) so the page also loads where Google Fonts is blocked.
