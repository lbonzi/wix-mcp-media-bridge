# wix-mcp-media-bridge

**Ephemeral** public staging for Cursor Wix MCP `UploadImageToWixSite` (`imageUrls`).

Wix/MCP cannot read local Mac paths. Random hosts (catbox/litterbox) are flaky. This repo holds short-lived JPEGs under `staging/`, then delete after Wix import + pixel gate.

## Use from brain

```bash
cd members-8020brain-template
node code/wix/lib/stage-image-github.mjs /path/to/Viewtoo_Blog_Topic.jpg
# → prints raw_url — pass to UploadImageToWixSite imageUrls
# after Wix pixel gate OK:
node code/wix/lib/stage-image-github.mjs --delete-path staging/<file>
```

Not a CDN. Not for product assets long-term. Prefer `imageBase64` or chat attachment when those work; this is the **reliable URL fallback**.

See brain doc: `code/wix/references/cover-upload-mcp.md`
