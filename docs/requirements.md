# Requirements

This section outlines specific stories and specs used to generate the app scaffold.
See [here](./workflows.md) for a description of general workflows.

# Domain entities

Users:

-   **Practitioner**: a user that will run practice sessions according to their
    goals, plans, objectives.

-   **Instructor**: a user that can set up a plan of practice sessions on behalf
    of a practitioner to help them achieve their goals.

-   **Reviewer**: user who is a peer practitioner or instructor that can review a practitioner's goals,
    plans or practice session history.

-   **Admin**: user that maintains the system (metadata, user adminstration)

User specific domain objects:

-   **Goal**: Intended outcome of practice over time,
    can be broken down to objectives and specific actionable steps.
    It might be to play a song, or improvise, or perform.
    Goals are set with a plan over 4 weeks or so to keep actionable.

-   **Objective**: specific outcome of a practice session (or group of practice sessions).
    The term might be used interchangably with "goal",
    but in this context, an objective is measurable at skills or theory proficiency level,
    goal is broader.
    An example might be to play a riff of a particular song.
    Or build a skill to use a specific technique proficiently.

-   **Practice Session**: A session includes one or more objectives covering one or more exercises/skills
    a practitioner needs to build competency for to achieve a goal.

-   **Exercise**: Performance of a skill or set of skills during a practice session.

-   **Recording**: Recording of Video and Audio during a user's practice session demonstrating
    performance of a skill covered by a session objective.
    Given that a practice session can cover multiple objectives,
    there can also be zero or more recordings per practice session.
    The recording is used by an instructor or reviewer

-   **Assessment**: Appraisal of the effectiveness of an exercise in a practice session

-   **Plan**:  A set of practice sessions set up by a practitioner and/or their instructor used
    to meet a set of objectives to meet specific goals.

General domain objects

-   **Skill**: developed competence in a specific area.
    An example might be general fretting hand proficiency in a particular zone of the fretboard,
    or cross string plucking of a particular pattern at a specific tempo.
    Skills are directly measureable,
    so are good building blocks for objectives and practice sessions.

-   **Tool**: A device or software that helps achieve an objective.
    Anytune, SBL Groove Trainer, Guitar Pro, MoisesAI, Soundslice are examples of tools.

-   **Content**: topics contained in some form of publishible work,
    in this context, video, audio, written (text), or a combination of.
    References to content will be via URLs.

-   **Content Provider**: Source of learning or practice content,
    usually (but not always) hosted or copy-righted and/or pay-walled by a commercial company.
    Examples might be Scott's Bass Lessons (SBL), Bass Buzz, TalkingBass, Songsterr, MuseScore, etc.

-   **Tool Provider**: Source of tools, usually (but not always) pay-walled.
    Examples might be Scott's Bass Lessons (for the Groove Trainer),
    Soundslice, Guitar Pro, etc.

-   **Templates**: Templates are available for Goals, Objectives and Plans because
    they are generally common across practitioners.

## Authentication/Authorization

-   User metadata
    - User name includes first and last names
    - User id is the email address associated with their identity provider
    - User provider (Github, google, apple, microsoft)

-   **Roles**
    -   **Practitioner**: Can set up goals, objectives, plans,
        as well as run through and record practice sessions,
        review progess.
        They can grant access for a single instructor to manage goals,
        objectives and plans, and grant access for instructor and multiple
        reviewers read access to goals, objectives, plans and practice session history.
        They can also export all their data to PDF form.

    -   **Instructor**: Can set up goals, objectives, plan on behalf of multiple
        practitioners, and review practice sessions and progress of their practitioners.

    -   **Reviewer**: Peer practitioners can also review practice sessions and
        progress of practitioners they follow.

    -   **Admin**: Can set up metadata, template skills,
        content providers, tool providers

-   **SSO** is used for authentication (the app does not handle authentication by itself)
    - Github
    - Google
    - Apple
    - Microsoft

-   **User** Management:
    Admin (or Users through Self-Service)
    -   Change their user meta-data
        (although the email address cannot be one already used for another user).
    -   Export their data to PDF
    -   Delete their account (prompts to export their data first)
