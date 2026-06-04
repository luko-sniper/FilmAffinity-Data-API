# Resumen (EN ESPAÑOL)

**FilmAffinity Data API**: Impulsa tu plataforma y aplicaciones con la comunidad de cine en español líder. Accede a una red activa de más de 1 millón de usuarios.

Extrae y estructura datos de FilmAffinity mediante nuestros endpoints principales:

- `GET /v1/search`: búsqueda de títulos por texto.
- `GET /v1/item`: datos detallados de películas y series por `item_id` o `url` de FilmAffinity.
- `GET /v1/discover`: listados personalizados con filtros avanzados (`category`, `genre`, `country`, `year_from`, `year_to`, `min_votes`, `duration_min`, `duration_max`, `platform`, `lang`, `limit_results`).

**Campos incluidos:** `id`, `title`, `year`, `scores`, `posters`, `type`, `url`, `category`, `genre`, `country`, `platform`, `votes`, `duration`, `actors`, `critics`, `synopsis`, y más…

&gt; **Nota:** Esta es la **única sección en español**. El resto de la documentación del hub (características, caché, planes, tutoriales...) está en **inglés**.

---

# 🎬 FilmAffinity Data API

**Subscribe & API key:** https://rapidapi.com/superdatai-superdatai/api/filmaffinity-data-api/

## Quick Setup
1. Subscribe to a plan (Basic free tier available).
2. Get your `X-RapidAPI-Key` from the dashboard.
3. Call `/v1/search?search=matrix&lang=es` (via RapidAPI host — see hub **Endpoints** tab).


**Fields include:** `id`, `title`, `year`, `scores`, `posters`, `type`, `url`, `category`, `genre`, `country`, `platform`, `votes`, `duration`, `actors`, `critics`, `synopsis`, and more...

---

#### Quick overview

**FilmAffinity Data API**: Fuel your platform and apps with the premier Spanish-language film community. Access a thriving network of over 1M+ users.

Extract and structure FilmAffinity data using our core endpoints:

- `GET /v1/search`: text-based title search.
- `GET /v1/item`: detailed movie/TV item data by Filmaffinity `item_id` or `url`.
- `GET /v1/discover`: get custom listings using advanced filters (`category`, `genre`, `country`, `year_from`, `year_to`, `min_votes`, `duration_min`, `duration_max`, `platform`, `lang`, `limit_results`).

#### Features
- Consistent, integration-friendly JSON responses.
- Caching layer for better latency and stability.
- Optional **`cache_bd`** on every endpoint: **speed** (`true`, default) or **always-fresh data** (`false`).
- Resilient backend with automated fallbacks and AI mechanisms.
- Language support (`lang=es|en`) **Español** and **English**.
- Built for apps, dashboards, bots, and automations.
- **Adaptive HTML extraction**: AI-powered to handle many HTML changes.

### Additional Information

- Use `lang=es` (default) or `lang=en` on all endpoints.
- For `discover`, use documented slugs for `genre` and `country`.
- Soft retries are recommended when the response indicates warming/retry.

### Optimized Performance via Caching

Responses can be served from our persistent cache or refreshed on demand.

**Standard Refresh Rates (TTL):**
* **Item details:** 7 days
* **Search results:** 48 hours
* **Discover lists:** 48 hours

**Query parameter `cache_bd` (all endpoints):**

| Value | Behavior | Best for |
|-------|----------|----------|
| **`true`** (default) | Use stored data when available (**no expiry on read**). On a cache miss, the API fetches and stores the result. | Fast, stable integrations; lower extraction usage |
| **`false`** | **Always fetch fresh data** on each request and update the store (a later `true` request can reuse it). | When you need the latest FilmAffinity data |

Responses include `cached` (`true` if the payload was already stored and `cache_bd`.

If data is still being prepared, you may get **`warming: true`** and **`retry_after`** — retry the same request after the suggested delay.

_Tip: Use `cache_bd=true` when **speed and stability** matter most; use `cache_bd=false` only when you need **real-time data** (higher latency)._


### API Reference and Examples

All documentation related to each endpoint. 

| Endpoint | Description | Link |
|----------|-------------|------|
| `GET /v1/search` | Text search (~50 results) | [How to use](https://rapidapi.com/superdatai-superdatai/api/filmaffinity-data-api/tutorials/how-to-use-search) |
| `GET /v1/item/by-id` | Full item details by numeric ID | [How to use](https://rapidapi.com/superdatai-superdatai/api/filmaffinity-data-api/tutorials/how-to-use-item-by-id) |
| `GET /v1/item?url=` | Full item details by FilmAffinity URL | [How to use](https://rapidapi.com/superdatai-superdatai/api/filmaffinity-data-api/tutorials/how-to-use-item-by-url) |
| `GET /v1/discover` | Get custom FilmAffinity listings (**Ultra / Mega** plans only) | [How to use](https://rapidapi.com/superdatai-superdatai/api/filmaffinity-data-api/tutorials/how-to-use-discover) |

---

## Legal

The API is provided by an independent developer. It is not affiliated with, sponsored by, or endorsed by FilmAffinity or any related trademark owner.
