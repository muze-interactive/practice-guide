# README

The *Practice Guide* is an application than can help simplify a musician's (AKA "User")
practice sessions and hands-on learning experience.

A practice session requires the following:

- goals that a user is working towards
- specific objectives for a practice session (that serve the goals),
  many times the objectives will be about building or improving skills
- exercises that serve the objectives - they should be easy to access and run,
  without a lot of setup time/effort.
- exercises use various assets, such as lecture content (text or video),
  notation, backing tracks, or use of playback or looper tools.
- ability to record the session, and share it for peer or instructor review
- ability to record and track progress

See [here](./docs/functionality.md) for suggested functionality,
as well as more [detailed functionality](./docs/requirements.md) and [workflows](./docs/workflows.md).

## Background

The basic idea of this project is to make music practice sessions more efficient and effective.

"Old School" practice methodologies may include a mix of hardcopy or PDF based notation or tab,
an instrument, an amp or digital amplification/recording.

The musician must figure out what to practice and why (unless guided by an instructor).

A large problem is that the musician may not even be aware of what their objectives are (or should be).

An inspiration for this project is from [Scott's Bass Lessons (SBL)](https://scottsbasslessons.com/),
and specifically the [Fullstack Bassist (FSB) and Guided Practice Curriculums using Teachable platform](https://scotts-bass-lessons.teachable.com/).
They have evolved their curriculum to be much more precise about what to practice and when,
to meet specific objectives.

But there are a few problems remaining:

- Teachable is structured for a sequential/linear learning experience,
  which may not work well for some students.

- There are a large amount of assets to choose from, video, text, backing tracks.
  Navigating Teachable platform is not tailored for this type of learning experience.

As a small improvement,
[this spreadsheet](https://docs.google.com/spreadsheets/d/10XWy3xU3wdGUNrIB_SsDE_v3aGmH75JGT2GR1xjQN_c/edit?gid=0#gid=0)
was generated as a single place to navigate the curriculum and its assets.
But it does not help with user navigate which specific assets are the best to use to accomplish as specific practice goal.

There are opportunities for improvement through an app:

- Add ability to query based on skills focused objectives,
  and get back a suggested list of exercises and their assets
- Ability to record and track practice progress (the SBL spreadsheet is rudimentary, would be nice to do in an app)
- Streamline session video and audio recording process (use of DAW may be overkill and high barrier for some users)
- Embedding of looper/playback tools in app

## Cross Provider Assets

Note that the application should not be tied to SBL or any other content provider (see [Known limitations](#known-limitations)),
as Course/Curriculum content is private.

But this limitation forces a benefit - that the app can also include references to other content providers as well
(think about [Bass Buzz](https://www.bassbuzz.com/lessons/beginner?utm_source=adwords&gad_source=1&gad_campaignid=22422913916&gbraid=0AAAAAD9wgdN_dRu2N-vshQhLNq5dzXtcp&gclid=CjwKCAjw_fnFBhB0EiwAH_MfZh0FLd6tVQrh4pnJek-6g8C3R5HL2hAtPZyuCIiCqHLqjtG-8shVtxoCZbAQAvD_BwE), [TalkingBass](https://www.youtube.com/@talkingbasslessons), [Beato](https://www.youtube.com/@RickBeato), and other online content providers)

Assets can also include access via notation/tab content providers, such as [Songsterr](https://www.songsterr.com/), [Musescore](https://www.songsterr.com/), [Soundslice](https://www.soundslice.com/), [Guitar Pro](https://www.guitar-pro.com/tabs), and others.

## Known limitations

Some initial research and exploration does uncover some limitation of existing tooling:

- SBL use of Teachable does not current support exposing direct timestamp links via URL.
- Soundslice API/embedding requires minimum of teacher's plan, and likely per-student seat.
- Youtube use for looping limited to second-interval loop markers, making unusable for bar markers with notation/tab.
- Content assets are managed/owned by SBL - they cannot/should not be extracted, although referenced through existing
  user login and online web access, or permission via SBL or other asset providers.
