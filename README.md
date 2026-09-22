# CA Screener Live

A Vercel-ready Solana CA screener that searches X Recent Search for very recent public posts, extracts Solana-style contract addresses, enriches matching tokens with DexScreener data, and calculates transparent heuristic signals.

## Deploy

1. Create a GitHub repository and upload this project's files.
2. Import the repository into Vercel.
3. In Vercel → Project → Settings → Environment Variables, add:
   - `X_BEARER_TOKEN` = your X API Bearer Token
4. Redeploy.
5. Open your Vercel URL and press **Scan now**.

## Important API notes

- The scanner uses X API Recent Search. Detection is affected by X indexing and API latency; it cannot guarantee that every post is visible within 30 seconds.
- The 0–30s filter is based on the timestamp of the X post containing the CA, not the blockchain creation time of the token.
- DexScreener enrichment is best-effort. A token may be new or have no indexed Solana pair yet.
- The frontend does not silently replace a failed live request with fake data. Demo data is available only when you explicitly press **Load demo**.
- Automatic scanning runs every 10 seconds while enabled. Adjusting this interval does not bypass X rate limits.

## Signals

The displayed X quality, creator quality, scam-like risk and trend potential are heuristics based on publicly available fields. They are not guarantees, accusations, financial advice, or proof of token safety.
