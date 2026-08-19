# TrackCleaner — user guide

TrackCleaner makes a radio-clean version of a song. It separates the vocal from the music,
listens to the words, finds the profanity, and ducks **only the vocal** over each word
while the music keeps playing. That is a real radio edit — not a bleep, and not a hole in
the track.

It is an assisted tool, deliberately. It finds and cuts automatically, then hands you a
waveform and a transcript so you confirm every censor by ear. Nothing gets exported that
you have not looked at.

---

## Install

1. Download the `.dmg` from the download page.
2. Open it and drag **TrackCleaner** to your Applications folder.
3. Launch it from Applications.

It opens normally — the app is signed and notarized by Apple. If macOS does warn you about
it, the download is damaged or incomplete: ask for a fresh copy rather than trying to work
around the warning.

**You need:** an Apple Silicon Mac (M1 or newer), macOS 12 or later, and about 5 GB of free
space for the audio models.

## Activate

TrackCleaner asks for an **activation key** the first time you open it. Paste in the key you
were sent and it unlocks. Until then it will not process anything.

If you do not have a key, ask your team lead. Keys are issued per person and some carry an
expiry date; if yours stops working, ask for a new one.

## First launch

After activating, the first launch needs an internet connection and takes a few minutes.
TrackCleaner is downloading the models it uses to hear the vocals — a "Getting ready" screen
shows real progress, including how much has downloaded. This happens once.

After that it works offline. The **first song** you clean is also slower than the rest,
because the models are warming up.

---

## Clean a song

### 1. Add songs

Drag audio files onto the drop zone, or click to pick them. You can queue up a stack — they
process one at a time, and you can start reviewing the first while the rest finish.

Before you queue them, three choices sit next to the file list:

- **Language** — English or Spanish. Pick the language the song is actually sung in. This
  matters more than any other setting: forcing the wrong language makes the app hear the
  lyrics phonetically and miss words it would otherwise catch.
- **Analysis** — how carefully to listen. The largest setting has the best recall and is the
  slowest. Use it unless you are in a hurry.
- **Detection** — which word list to use.

Accepted formats and the file-size limit are shown on the drop zone itself.

Each queued song shows its stage and elapsed time. The **✕** on a row removes it — from the
queue if it has not started, or cancels it if it is already running.

### 2. Review

When a song is ready, open it. You get the waveform on top and the transcript below.

**The transcript is the editing surface.** Every word the app heard is there:

- **Click an uncensored word** to censor it.
- **Click a censor** to select it and see its details on the right.
- Censors are underlined and tinted — red for profanity, amber for a low-confidence match,
  violet for a word only a later listen caught. Violet ones are the most worth
  double-checking.

The word being sung lights up as the song plays, and the transcript scrolls to follow it.

**The panel on the right** shows the selected censor and lets you:

- turn it **off** without deleting it,
- **nudge** its start or end if it clips the word or catches too much,
- change **how it sounds** — duck to the instrumental (the default), reverse, or silence,
- switch on **aggressive**, which strips more of the backing when an ad-lib bleeds through.
  It sounds thinner, so use it only where you need it,
- **delete** it.

You can also right-click a censor on the waveform for the same controls.

**Drawing your own censor.** Click **✏️ Add region** on the waveform toolbar (or hold Shift
or Alt) and drag across the part you want muted — useful for an ad-lib the transcript
missed. Drawing switches itself off after one region, so the waveform goes straight back to
scrubbing.

**"Worth a listen".** Under the summary is a checklist of places the app is not confident
about: words that sound close to profanity, spots where a pass heard something unclear, and
stretches where no pass heard any words at all. Each chip plays that moment and ticks itself
off once you have checked it. These are **not** censored automatically — they are there so
you can decide.

If a song comes back saying **no words were transcribed**, treat that as a failure, not as a
clean song. Add it again, and if it happens twice, say so — something is wrong.

### 3. Listen to the result

Press **P** to hear the clean version instead of the original, so you are auditioning what
you will actually export. **R** auditions just the selected censor.

### 4. Export

Type a name in **Save as** if you want something other than the default, then export. You
choose where it saves.

Mark a song **reviewed** when you are happy with it. Once several are marked, **Export all
reviewed** renders them and gives you one zip.

---

## Keyboard shortcuts

Press **?** in the app for this list at any time.

| Key | Action |
|---|---|
| `Space` | play / pause |
| `J` / `K` | jump to the previous / next censor |
| `E` | turn the selected censor off or on |
| `R` | audition the selected censor |
| `[` / `]` | nudge the selected censor's edges |
| `←` / `→` | seek 1 second (hold Shift for 5) |
| `P` | switch between the original and the clean version |
| `F` | fit the whole song in the waveform |
| `N` | next song you have not reviewed |
| `⌘Z` | undo |
| `?` | show this list |

---

## Settings

The **⚙** button, top right.

- **Your own words** — add slang the built-in lists miss. These apply to songs you process
  *after* saving; songs already finished are not re-scanned.
- **Spanish detection** — choose which kinds of terms are censored automatically. Turning a
  category off never hides anything: those terms still appear in "worth a listen", they just
  stop being cut for you.

---

## Good to know

- **Nothing is destructive.** Your original file is never modified. Every export is rendered
  fresh from it, so you can re-export as many times as you like.
- **Only the censored moments are touched.** Audio outside a censor is the untouched
  original.
- **One song at a time, on purpose.** The queue processes serially so the audio models do
  not fight each other for memory. A stack of songs takes as long as the sum of its parts.
- **If a censor sounds like only drums and bass**, aggressive is switched on for it — turn it
  off in the panel on the right.
- **Everything happens on your Mac.** Songs are not uploaded anywhere. The only network
  traffic is the one-time model download and an optional lyrics lookup, used purely as a hint
  to help it hear the words.
