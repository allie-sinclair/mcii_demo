# MCII Goal Exercise — classroom demo

A single-page, no-backend demo that walks students through **Mental Contrasting with Implementation Intentions (MCII)**, also known as **WOOP** (Wish, Outcome, Obstacle, Plan), with guided writing prompts and a debrief explaining why the strategy works.

Everything runs in the student's browser. No responses are uploaded, logged, or stored.

## What students do

1. **Wish** — state a challenging-but-feasible wish for the next four weeks. They can also pick a life area and rate how likely and how important the wish is (1–7); these are optional.
2. **Outcome** — name the best outcome and, if they like, describe it, with an optional 30-second imagery timer.
3. **Obstacle** — name the main obstacle, which can be internal (a habit, emotion, belief) or external (schedule, other people, surroundings). They can tag which kind it is and note when and where it shows up; both are optional. There is no timer on this step.
4. **Plan** — write an if-then plan linking the obstacle to an action, with gentle tips if the "if" part names no time or place or the action is vague ("try harder").
5. **Debrief** — explains the mental contrasting and implementation intention components and why each works, then summarizes the evidence, shows the student's responses, and gives full references with DOIs. Students can download their plan as a .txt file or print it to PDF.

There are no minimum word counts. The only required fields are the short ones the later steps build on: the wish, the outcome name, the obstacle name, and both halves of the plan.

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

Settings are at the top of the `<script>` in `index.html`:

- `IMAGERY_SECONDS` — length of the outcome imagery timer (default 30)
- `DOMAINS` — life-area choices on the Wish screen
- `OBSTACLE_TYPES` — choices for tagging the obstacle as internal or external

Prompt wording lives in the `RENDER.*` functions, and the debrief text is in `RENDER.debrief`.

## References

- Duckworth, A. L., Grant, H., Loew, B., Oettingen, G., & Gollwitzer, P. M. (2011). Self-regulation strategies improve self-discipline in adolescents: Benefits of mental contrasting and implementation intentions. *Educational Psychology, 31*(1), 17–26. https://doi.org/10.1080/01443410.2010.506003
- Gollwitzer, P. M. (1999). Implementation intentions: Strong effects of simple plans. *American Psychologist, 54*(7), 493–503. https://doi.org/10.1037/0003-066X.54.7.493
- Gollwitzer, P. M., & Sheeran, P. (2006). Implementation intentions and goal achievement: A meta-analysis of effects and processes. *Advances in Experimental Social Psychology, 38*, 69–119. https://doi.org/10.1016/S0065-2601(06)38002-1
- Oettingen, G. (2012). Future thought and behaviour change. *European Review of Social Psychology, 23*(1), 1–63. https://doi.org/10.1080/10463283.2011.643698
- Oettingen, G., Pak, H., & Schnetter, K. (2001). Self-regulation of goal setting: Turning free fantasies about the future into binding goals. *Journal of Personality and Social Psychology, 80*(5), 736–753. https://doi.org/10.1037/0022-3514.80.5.736
- Wang, G., Wang, Y., & Gai, X. (2021). A meta-analysis of the effects of mental contrasting with implementation intentions on goal attainment. *Frontiers in Psychology, 12*, 565202. https://doi.org/10.3389/fpsyg.2021.565202

This is an independent teaching demo and is not affiliated with the original researchers or the official WOOP program.
