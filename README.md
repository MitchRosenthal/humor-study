# Humor Caption App

A web app for AI-generated meme captions. Upload an image and the app sends it through a caption-generation pipeline, then shows the results in a scrolling feed where people vote captions up or down. Built for Columbia's Humor Project course (spring 2026).

## Features

- Google sign-in through Supabase Auth
- Image upload that runs the shared caption-generation pipeline and shows progress while captions are created
- Scrolling feed with swipe or button voting; captions you've already voted on don't come back
- Vote history drawer and one-click meme download
- Votes stored in Postgres (`caption_votes`) with the schema in `my-app/supabase/`

## Usability study

I ran a three-person usability study on the app and changed the UI based on what I saw: the original three-per-row grid felt overwhelming, generation gave no feedback, and it wasn't clear what happened after a caption appeared. The fixes were a single-column scrolling feed, loading feedback during generation, and clearer voting. The full write-up is in [`user_study_report.md`](user_study_report.md).

## Tech

Next.js (App Router), React, TypeScript, Supabase (Postgres + Auth), deployed on Vercel.

## Running locally

The app lives in `my-app/`.

```bash
cd my-app
pnpm install
# add NEXT_PUBLIC_SUPABASE_URL and NEXT_PUBLIC_SUPABASE_ANON_KEY to .env.local
pnpm dev
```
