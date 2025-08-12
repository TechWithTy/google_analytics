# DealScale GA4 SDK

Read-only client for Google Analytics Data API (GA4). Mirrors the structure used in the GSC SDK.

## Features
- Installed-app OAuth and Service Account auth
- Small HTTP client with retries/backoff
- Typed Pydantic request/response models
- Quickstart scripts
- Mocked tests (no real creds required)

## Install
Use your existing workspace's Python. This folder includes a `pyproject.toml` with deps similar to the GSC SDK.

## Env
Copy `.env.example` and set values, or export directly:
- `GA_CLIENT_SECRETS` (optional for installed-app)
- `GA_TOKEN_PATH` (installed-app token cache)
- `GA_SA_KEY` (service account JSON key path)
- `GA_SCOPE=https://www.googleapis.com/auth/analytics.readonly`
- `GA_PROPERTY_ID=<your numeric property id>`
- `GA_HTTP_TIMEOUT=30`
- `GA_USER_AGENT=CyberOni-GA4-SDK/1.0`

## Quickstarts
- `scripts/quickstart_ga4.py` (installed-app)
- `scripts/quickstart_ga4_service_account.py` (service account)

## Troubleshooting
- 401/403: SA/user missing property access; wrong scope; wrong project
- Invalid argument: wrong dimension/metric; call `get_metadata()` to discover
- Quota: handle 429/5xx with backoff

## Security
- Do not commit secrets.
- Add the service account email as a user on the GA4 property in Admin.
