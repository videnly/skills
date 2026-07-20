# Videnly faceless-video contract

Faceless generation operates on an existing authenticated-account project:

1. Resolve the project.
2. Validate it with `prepare_faceless_video`.
3. Estimate with `estimate_faceless_video_cost`.
4. Show the exact price and wait for explicit approval.
5. Generate with `generate_faceless_video` using the matching estimate token.
6. Monitor status until completion or failure.

Clients may namespace tool names with the connected server name, such as `videnly_`; match the live tool by its canonical suffix. Preparation and estimation do not authorize spending. Re-run both after project changes. Treat live tool descriptions and schemas as authoritative.
