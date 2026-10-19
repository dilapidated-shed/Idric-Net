# HTTP version for source acquisition

Purpose: ICU's HTTP/1.0 request received HTTP 426 at the source acquisition boundary on 2026-10-19. A diagnostic HTTP/1.1 request through the same provider reached the source. Protocol version belongs in Idric-Net rather than client string substitution.

Type sketch: `http_version` is the finite choice `http_one_zero | http_one_one`. `render_request_parts_at_version` takes that choice with the existing checked request headers and produces the same `RenderedRequest`. Existing renderers retain their HTTP/1.0 default. Body lengths, credential metadata and reserved-header refusal are unchanged.

The source acquisition candidate explicitly chooses HTTP/1.1. This does not implement HTTP/2, persistent connections or a complete HTTP/1.1 response parser. ICU owns the current bounded native response provider. Actual compiler, source hashes, producer and independent acceptance must be recorded separately.
