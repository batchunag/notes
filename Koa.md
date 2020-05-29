#Middlewares
Middlewares are array/ensemble of functions.
So it seems difficult to extract specific one later.

#Using Koa for re-routing & redirection.

```ts
import Router from "koa-router";

//using Regex
router.get(/^\/path\/to\/somewhere\/(.*)/, (ctx) => {
  ctx.redirect(`/another/${ctx.params[0]}`);
});

// Below is an experiment
router.get(/^\/routed\/(.*)/, async (ctx) => {
  const path = `/another/${ctx.params[0]}`;
  await KoaRewrite(path);
  await KoaSend(ctx, path);
});

//Straight-forward
router.get("/test").route("/another");

//For static files, using as a middleware
KoaMount("/another/static", KoaStatic("/static"));
```
