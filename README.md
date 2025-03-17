This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/pages/api-reference/create-next-app).

It's purpose is to reproduce a bug where an existing page renders as blank after hot reload when adding additional pages.

## Repro

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

Run the following commands from the repo root while the dev server is running:

```
cp foo.js src/pages
```

Refresh the `http://localhost:3000` page in the browser. It renders as a blank page and scripts are not running.

Navigate to the new page `/foo` and notice that instead of rendering the
expected content, it renders what should be on `/`.

Exiting the dev server and restarting allows both `/` and `/foo` to render properly.
