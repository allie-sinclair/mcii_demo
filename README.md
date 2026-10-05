# MCII Goal Exercise — classroom demo

A single-page, no-backend demo that lets students experience **Mental Contrasting with Implementation Intentions (MCII)**, also known as **WOOP** (Wish, Outcome, Obstacle, Plan), with guided writing prompts and a research debrief.

Everything runs in the student's browser. No responses are uploaded, logged, or stored.

## What students do

1. **Wish** — pick a life domain, state a challenging-but-feasible wish for the next four weeks, and rate expectancy and importance (1–7).
2. **Writing prompts** — name and freely elaborate on the best outcome and/or main inner obstacle (with an optional 60-second imagery timer).
3. **Plan** (MCII only) — write an if-then plan, with live feedback if the cue or action is vague.
4. **Reflect** — rate commitment and energization (1–7).
5. **Debrief** — explanation of the four versions, the theory, key effect sizes, full references with DOIs, and the student's own responses (download as .txt/.json, or print to PDF).

## Four versions (for an in-class experiment)

Modeled on the three self-regulatory modes in Oettingen, Pak, & Schnetter (2001), plus full MCII:

| Code | Version | Steps |
|---|---|---|
| `mcii` | MCII | Wish → Outcome → Obstacle → If-then plan |
| `mc` | Mental contrasting only | Wish → Outcome → Obstacle |
| `indulge` | Indulging | Wish → Outcome → Second outcome |
| `dwell` | Dwelling | Wish → Obstacle → Second obstacle |

### Instructor links (URL parameters)

Append `?condition=` to the site URL to control assignment:

- `…/?condition=random` — each student is randomly assigned (they don't see a choice)
- `…/?condition=mcii` (or `mc`, `indulge`, `dwell`) — everyone gets that version
- No parameter — students choose "Classroom experiment (random)" or "Full MCII"

Randomization is simple per-student (`Math.random`), so group sizes won't be exactly balanced in a small class.

### Pooling class results

At the end, each student sees a short **class code** like `MC-E6-I5-C6-N4-W87` (version, expectancy, importance, commitment, energization, words written). It contains no free text. Collect these via a Google Form, a shared sheet, or a poll, then split on `-` to compare, e.g., the expectancy × commitment relationship across conditions — the key prediction from Oettingen et al. (2001) is that commitment tracks expectancy more strongly in the mental contrasting conditions than in indulging or dwelling. With a single class this is a demonstration, not a powered test.

## Deploy on GitHub Pages

1. Create a new public repository on GitHub (e.g., `mcii-demo`).
2. Upload `index.html`, `README.md`, and `.nojekyll` to the root of the `main` branch (drag-and-drop via **Add file → Upload files** works).
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute or two, the site is live at `https://<your-username>.github.io/<repo-name>/`.

Or from the command line:

```bash
cd mcii-demo
git init && git add . && git commit -m "MCII classroom demo"
git branch -M main
git remote add origin https://github.com/<your-username>/mcii-demo.git
git push -u origin main
# then enable Pages in Settings → Pages as above
```

To preview locally, just open `index.html` in a browser.

## Customizing

All settings are near the top of the `<script>` in `index.html`:

- `DOMAINS` — life-domain choices on the Wish screen
- `IMAGERY_SECONDS` — length of the optional imagery timer
- `CONDITIONS` — step sequence for each version
- Prompt wording lives in the `RENDER.*` functions; minimum-length checks (10 words for elaborations) are in `bindElaboration`.

## References

- Duckworth, A. L., Grant, H., Loew, B., Oettingen, G., & Gollwitzer, P. M. (2011). Self-regulation strategies improve self-discipline in adolescents: Benefits of mental contrasting and implementation intentions. *Educational Psychology, 31*(1), 17–26. https://doi.org/10.1080/01443410.2010.506003
- Gollwitzer, P. M. (1999). Implementation intentions: Strong effects of simple plans. *American Psychologist, 54*(7), 493–503. https://doi.org/10.1037/0003-066X.54.7.493
- Gollwitzer, P. M., & Sheeran, P. (2006). Implementation intentions and goal achievement: A meta-analysis of effects and processes. *Advances in Experimental Social Psychology, 38*, 69–119. https://doi.org/10.1016/S0065-2601(06)38002-1
- Oettingen, G., Pak, H., & Schnetter, K. (2001). Self-regulation of goal setting: Turning free fantasies about the future into binding goals. *Journal of Personality and Social Psychology, 80*(5), 736–753. https://doi.org/10.1037/0022-3514.80.5.736
- Wang, G., Wang, Y., & Gai, X. (2021). A meta-analysis of the effects of mental contrasting with implementation intentions on goal attainment. *Frontiers in Psychology, 12*, 565202. https://doi.org/10.3389/fpsyg.2021.565202

This is an independent teaching demo and is not affiliated with the original researchers or the official WOOP program.
