# Videnly direct-media contract

Use this sequence:

1. Discover enabled models with `list_media_models`.
2. Estimate with `estimate_media_generation`; estimation does not spend credits.
3. Show the exact price and wait for explicit approval.
4. Generate with `generate_media` using the unchanged request and matching confirmation token.
5. Monitor with `get_generation_status`.

Clients may namespace tool names with the connected server name, such as `videnly_`; match the live tool by its canonical suffix. Re-estimate whenever a billable or output-affecting field changes. Treat the live schema and model catalog as authoritative. Do not expose confirmation tokens, access tokens, internal storage paths, or transient signed URLs.
