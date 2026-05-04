# FeedJarKit for Web (`@feedjar/sdk-web`)

TypeScript SDK aligned with **FeedJarKit iOS** and **Android**: same ingest and list endpoints, `fjr_` API keys, and support-email validation.

## Layout (same idea as `feedjar_sdk_ios/`)

```
feedjar_sdk_web/
├── package.json
├── tsconfig.json
├── README.md
└── src/
    └── index.ts
```

## Use

```bash
npm install   # or pnpm — point at this folder / workspace until published
npm run build
```

```typescript
import { configure, submit, listFeedback } from "@feedjar/sdk-web";

configure("fjr_...", { baseUrl: "http://localhost:4000" }); // baseUrl optional

await submit({
  type: "feature",
  message: "Dark mode please",
  email: "user@example.com",
});

const { feedback } = await listFeedback({ limit: 20 });
```

## Defaults

- **API:** `https://api.feedjar.in`
- **Auth:** `Authorization: Bearer <key>` and `X-FeedJar-Key` (server still accepts legacy `X-Feedbox-Key` during migration).

## License

MIT
