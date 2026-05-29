# Fix notes

This zip fixes the template repo so the provider registry is internally consistent.

Changes made:

1. `manifest.json` now points to the file that actually exists:
   - before: `providers/template.js`
   - after: `providers/_template.js`

2. The template provider is enabled for testing:
   - before: `enabled: false`
   - after: `enabled: true`

3. The provider ID is simplified:
   - before: `template-provider`
   - after: `template`

4. The logo now points to an existing local asset:
   - `Assets/Logo-2.png`

Important: this is still only a template provider. It returns an empty stream list until you add your own legal/authorized provider logic inside `src/_template/` and rebuild.

How to test locally:

```bash
npm install
npm run build
npm start
```

Then open this URL in a browser:

```text
http://<your-computer-ip>:3000/manifest.json
```

In Nuvio, use the plugin/provider tester or plugin repository URL field, not the normal Stremio-style addon URL field.
