## Create the App:

* [ ] Node LTS matches what production/CI will use (`node -v` vs `.nvmrc` / `engines`).
* [ ] Create the app:
~~~
npx create-next-app@latest my-next-app
~~~
* [ ] App Router vs Pages Router is an explicit team choice; do not mix routing styles in one feature without a rule.
* [ ] `src/` directory yes/no is consistent with other repos.
* [ ] TypeScript `strict` is on from day one if the team uses TS.

## Env and Secrets:

* [ ] `.env.local` is gitignored; `.env.example` lists every key with dummy values.
* [ ] Server secrets do **not** use `NEXT_PUBLIC_`.
* [ ] `NEXT_PUBLIC_` values are treated as public; no private API keys there.
* [ ] Validate required env at boot (small schema or equivalent) so a missing secret fails fast, not on first request.

## Data Fetching Traps:

* [ ] You know which components are Server Components by default and which need `'use client'`.
* [ ] You did not put a secret in a Client Component bundle (inspect the browser sources).
* [ ] `fetch` caching: user-specific data is not statically cached. Default changed across Next versions (15+ is no-store by default) — set `cache` / `revalidate` explicitly for the data you mean.
* [ ] Cookies/headers used in a Server Component mean that route cannot be statically cached as a public page.
* [ ] Route Handlers that mutate use POST/PATCH/DELETE, not GET.

## Auth and Middleware:

* [ ] Matcher in `middleware.ts` does not run on `_next/static` or image optimizer in a way that tanks TTFB (check the matcher).
* [ ] Middleware auth redirect does not loop (`/login` ↔ `/`).
* [ ] Server Actions that mutate check CSRF/origin per Next’s current recommendations and your auth library.

## Images, Fonts, Metadata:

* [ ] `next/image` `remotePatterns` allowlist is set; you did not enable all hosts.
* [ ] Fonts via `next/font` (no render-blocking Google Fonts CSS in `head` unless intended).
* [ ] `metadata` / `generateMetadata` per route; no duplicate default title on every page.
* [ ] `openGraph` images are absolute URLs in production.

## Quality:

* [ ] `output: 'standalone'` is considered for Docker.
* [ ] ESLint `next/core-web-vitals` is enabled; no ignored `any` on API boundaries.
* [ ] Redirects/headers (security headers, trailingSlash) live in `next.config` and are tested on preview.
* [ ] `npm run build` succeeds locally; you did not only run `dev`.
* [ ] Preview deploys do not index (`X-Robots-Tag: noindex` on non-prod).
