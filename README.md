This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.js`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/import?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

## Include Tailwind in your CSS

When including Tailwind in your CSS in a Next.js project, there are two approaches you can take.

### Import Tailwind directly in your JS

If you aren't planning to write any custom CSS in your project, the fastest way to include Tailwind is to import it directly in `pages/_app.js`:

```diff-js
  // pages/_app.js
- import '../styles/globals.css'
+ import "tailwindcss/tailwind.css";

  function MyApp({ Component, pageProps }) {
    return <Component {...pageProps} />
  }

  export default MyApp
```

If you aren't planning to use them, you can safely delete any CSS files Next.js creates for you by default like `globals.css` and `Home.module.css`. Make sure you delete any references to them within your components as well.

```preval include
level: 4
file: ./styles/globals.css
```

Finally, ensure your CSS file is being imported in your `pages/_app.js` component:

```js
// pages/_app.js
import '../styles/globals.css'

function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />
}

export default MyApp
```

If you've chosen to use a different file than the default `globals.css` file, you'll want to update the import accordingly.

---

```preval finish
scripts:
  - npm run dev
```

### Notes for PostCSS 8

Per Adam:

For Next.js 10 you don't need the compatibility build, install Tailwind like this:

```js
npm install tailwindcss@latest postcss@latest autoprefixer@latest
```

PostCSS and Autoprefixer need to be peer-dependencies as of PostCSS 8.
