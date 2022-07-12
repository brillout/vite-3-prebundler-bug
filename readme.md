Bug reproduction.

```bash
git clone git@github.com:brillout/vite3-prebundler-bug
cd vite3-prebundler-bug/
pnpm install
pnpm run dev:express
```

Same as single line (copy-paste me):

```shell
git clone git@github.com:brillout/vite3-prebundler-bug && cd vite3-prebundler-bug/ && pnpm install && pnpm run dev:express
```

Go to [localhost:3000](http://localhost:3000) and observe:

```
11:22:24 AM [vite] ✨ new dependencies optimized: react, react-dom/client
11:22:24 AM [vite] ✨ optimized dependencies changed. reloading
```

Interestingly, when using the Vite CLI `$ vite`, it only occasionally logs `[vite] ✨ new dependencies optimized`:

```bash
rm -rf node_modules/.vite/
pnpm run dev:vite
```

Whereas the `[vite] ✨ new dependencies optimized` logs can be reliably reproduced when using the Express.js server:

```bash
rm -rf node_modules/.vite/
pnpm run dev:express
```
