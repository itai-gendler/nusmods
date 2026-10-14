---
scope: The nusmods.com website and its serverless functions, the timetable optimiser and export service, and the scraper that publishes the course and venue data and public API.
method: Static inspection of source, configuration, tests and documentation at the pinned commit; nothing was run.
covered:
  - description: Website pages for the timetable, courses, venues, Today, planner, optimiser, CPEx and settings, with their shared components.
    paths: [website/src/views/timetable/, website/src/views/modules/, website/src/views/venues/, website/src/views/today/, website/src/views/planner/, website/src/views/optimiser/, website/src/views/mpe/, website/src/views/settings/, website/src/views/components/, website/src/views/layout/, website/src/views/routes/, website/src/views/errors/]
  - description: Website state, its persistence and cross-tab sync, selectors and the logic for timetables, exams, planner checks, search, venues and calendars.
    paths: [website/src/actions/, website/src/reducers/, website/src/selectors/, website/src/storage/, website/src/middlewares/, website/src/utils/, website/src/types/]
  - description: Website clients for course data, search, export, weather, CPEx and the link shortener.
    paths: [website/src/apis/]
  - description: Term settings, feature flags and the shipped data for venues, holidays, CourseReg rounds, faculty contacts and themes.
    paths: [website/src/config/, website/src/featureFlags.ts, website/src/data/]
  - description: Serverless functions for NUS sign-in and CPEx responses, and the Go timetable optimiser.
    paths: [website/api/, website/src/serverless/]
  - description: Timetable image and PDF export service.
    paths: [export/api/, export/src/, website/src/entry/export/]
  - description: Scraper that refreshes courses, exams and venues from the university and writes the public API data.
    paths: [scrapers/nus-v2/]
exclusions:
  - description: Styling, images, icons and static assets.
    paths: [website/src/styles/, website/src/img/, website/static/, export/public/, misc/]
  - description: Website bootstrapping, entry points, build scripts and bundler configuration.
    paths: [website/src/bootstrapping/, website/src/entry/main.tsx, website/src/index.ejs, website/webpack/, website/scripts/, website/babel.config.js, website/tsconfig.json, website/vercel.json, website/package.json]
  - description: Tests, mocks, fixtures and test configuration.
    paths: [website/src/__mocks__/, website/src/test-utils/, website/src/e2e/, website/vitest.config.ts, website/vitest.integration.config.ts, website/nightwatch.conf.js]
  - description: Repository tooling, CI, deployment and server provisioning.
    paths: [.circleci/, .github/, .husky/, infra/, package.json, pnpm-workspace.yaml, renovate.json, vercel_ignore_build.sh, packages/browserslist-config-nusmods/]
unmapped:
  - description: The Tetris game page.
    paths: [website/src/views/tetris/]
  - description: About, team, contributors, FAQ, apps, contribute and Hacktoberfest pages.
    paths: [website/src/views/static/, website/src/views/contribute/]
  - description: Scraper of the CPEx course list.
    paths: [scrapers/cpex-scraper/]
  - description: Academic calendar and module-code libraries shared with other projects.
    paths: [packages/nusmoderator/, packages/nusmods-academic-calendar/]
limitations: []
---

# Coverage
