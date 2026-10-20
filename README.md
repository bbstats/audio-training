# What's Missing? pre-test

A blind listening test that runs in a browser (phone or desktop).

1. The participant enters their name and listens to the full mix (`audio/baseline.mp3`) as many times as they like.
2. They tap **Continue**, get an "Are you sure? You can't go back" warning, then hear the 7 takes one at a time. The takes are shuffled once, by a fixed seed, so everyone hears the same scrambled order (not a to g).
3. For each take they pick what's been removed: Overheads, Kick, Snare, Toms, Rhythm Electric Guitars, Lead Electric Guitar, or Bass Guitar. Answers lock when they move on.
4. When they finish, their results are emailed to you through [FormSubmit](https://formsubmit.co). Each email lists the name, each **file name** with the answer given and how many times it was played, and the order the takes were heard in. Takes are only ever shown as "Take 1 of 7" and so on, so the participant never sees file names.

If a send fails, the participant sees their results in a box with a Copy button, so nothing is lost. A reload during the test picks up on the same take, so a reload can't be used to get back to the full mix.

## Going live (one time)

1. On GitHub, open **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick the branch this is on, folder `/ (root)`, and click **Save**.
3. After a minute or so the test is live at **https://bbstats.github.io/audio-training/**.
4. Take the test once yourself on that URL. FormSubmit will email you an **Activate Form** link. Click it. That first run won't be delivered as a result, but every run after it will.

## Changing things

All settings are at the top of the `<script>` in `index.html`:

- `SUBMIT_URL`: where results are sent. After activation FormSubmit gives you a random-string address you can use instead of your email, to keep your email out of the page code.
- `SHUFFLE_SEED`: the number that fixes the take order. Change it for a different order, or set it to `null` for plain a-to-g order. The order is also listed in every results email.
- `TAKES` / `OPTIONS`: the clip file names (in `audio/`) and the answer choices.
