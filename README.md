# Ultimate-ESlint-config
One file, many plugins – just copy and paste.

Every rule of every plugin is listed in [rules.md](rules.md), including the ones you will probably turn off.
Rule lists checked against ESLint 10.12 and the plugin versions available on 2026-10-11.

## Eslint plugins

### Exact versions from this repo
`package.json` pins every package to the version `rules.md` and `eslint.config.js` were checked against (Node `^22.22.2 || >=24.15.0`).
```
npm install
```

### If you want install all at once
`eslint@^10` and `typescript@~6.0` are pinned on purpose: without them npm can pick ESLint 9 (peer conflict, install fails) or TypeScript 7 (not supported by typescript-eslint yet).
```
npm install --save-dev eslint@^10 @eslint/js typescript-eslint typescript@~6.0 svelte-eslint-parser eslint-plugin-svelte prettier-plugin-svelte @html-eslint/parser @html-eslint/eslint-plugin eslint-plugin-tailwindcss eslint-plugin-better-tailwindcss @pandacss/eslint-plugin eslint-plugin-drizzle @vitest/eslint-plugin eslint-plugin-perfectionist eslint-plugin-unicorn @stylistic/eslint-plugin eslint-plugin-functional eslint-config-prettier prettier-plugin-organize-imports eslint-plugin-security eslint-plugin-sonarjs eslint-plugin-tsdoc eslint-plugin-promise @cspell/eslint-plugin eslint-plugin-import-x eslint-import-resolver-typescript @dword-design/eslint-plugin-import-alias eslint-plugin-boundaries eslint-plugin-eslint-plugin @eslint-community/eslint-plugin-eslint-comments @eslint/json eslint-plugin-regexp @eslint/markdown @eslint/css tailwind-csstree yaml-eslint-parser eslint-plugin-yml eslint-plugin-n
```

### [Eslint JS](https://eslint.org/)
```
npm install --save-dev eslint@^10 @eslint/js
```

### [Eslint TypeScript](https://typescript-eslint.io/)
```
npm install --save-dev typescript-eslint typescript@~6.0
```

### [Svelte](https://github.com/sveltejs/eslint-plugin-svelte)
For linting and formatting Svelte files. Includes:
- **[Svelte ESLint Parser](https://github.com/sveltejs/svelte-eslint-parser)**: Parses `.svelte` files for ESLint.
- **[ESLint Plugin Svelte](https://github.com/sveltejs/eslint-plugin-svelte)**: Provides linting rules specific to Svelte.
- **[Prettier Plugin Svelte](https://github.com/sveltejs/prettier-plugin-svelte)**: Enables Prettier to format Svelte files.
```
npm install --save-dev svelte-eslint-parser eslint-plugin-svelte prettier-plugin-svelte
```

### [HTML](https://html-eslint.org/)
```
npm install --save-dev @html-eslint/parser @html-eslint/eslint-plugin
```

### [CSS](https://github.com/eslint/css)
Official ESLint CSS language. `tailwind-csstree` teaches the parser Tailwind CSS v4 syntax (`@theme`, `@apply`, ...).
```
npm install --save-dev @eslint/css tailwind-csstree
```

### Tailwind CSS
Two plugins, pick one:
- **[eslint-plugin-tailwindcss](https://github.com/francoismassart/eslint-plugin-tailwindcss)**: The classic one, v4 supports Tailwind CSS 4.
- **[eslint-plugin-better-tailwindcss](https://github.com/schoero/eslint-plugin-better-tailwindcss)**: Reads the CSS-based Tailwind 4 config, also lints classes in plain TS strings and CSS `@apply`.
```
npm install --save-dev eslint-plugin-tailwindcss
npm install --save-dev eslint-plugin-better-tailwindcss
```

### [PandaCSS](https://github.com/chakra-ui/panda/tree/main/packages/eslint-plugin)
Version 2 is a rewrite: rules read your `panda.config.ts`, and the config is created with `await panda.configs.recommended({ configPath })`.
```
npm install --save-dev @pandacss/eslint-plugin
```

### [Drizzle ORM](https://orm.drizzle.team/docs/eslint-plugin)
```
npm install --save-dev eslint-plugin-drizzle
```

### [Vitest](https://github.com/vitest-dev/eslint-plugin-vitest)
```
npm install --save-dev @vitest/eslint-plugin
```
### Style & Best Practices
For maintaining clean and organized code. Includes:
- **[Perfectionist](https://perfectionist.dev/)**: Ensures consistent ordering in objects and imports.
- **[Unicorn](https://github.com/sindresorhus/eslint-plugin-unicorn)**: Enforces good practices.
- **[Stylistic](https://eslint.style/packages/default)**: Style-based rules for ESLint.
- **[Functional](https://github.com/eslint-functional/eslint-plugin-functional)**: Enforces functional programming principles.
- **[Prettier](https://prettier.io/docs/en/integrating-with-linters.html)**: Code formatting.
- **[Prettier-Organize-Imports](https://github.com/simonhaenisch/prettier-plugin-organize-imports)**: Automatically organizes imports.

```
npm install --save-dev eslint-plugin-perfectionist eslint-plugin-unicorn @stylistic/eslint-plugin eslint-plugin-functional eslint-config-prettier prettier-plugin-organize-imports
```

### Security & Quality
For improving code security and quality. Includes:
- **[ESLint Security](https://github.com/eslint-community/eslint-plugin-security)**: Identifies potential security vulnerabilities in your code.
- **[SonarJS](https://www.npmjs.com/package/eslint-plugin-sonarjs)**: Detects bugs and code smells.
- **[TSDoc](https://tsdoc.org/pages/packages/eslint-plugin-tsdoc/)**: Enforces consistent and valid TypeScript documentation comments.
- **[ESLint Promise](https://github.com/eslint-community/eslint-plugin-promise)**: Ensures best practices for working with JavaScript Promises.
- **[CSpell](https://github.com/streetsidesoftware/cspell/tree/main/packages/cspell-eslint-plugin)**: Spell Checker for code comments, strings, and identifiers.

```
npm install --save-dev eslint-plugin-security eslint-plugin-sonarjs eslint-plugin-tsdoc eslint-plugin-promise @cspell/eslint-plugin
```

### Import Management & Architecture
For managing and organizing imports effectively. Includes:
- **[ESLint Plugin Import X](https://github.com/un-ts/eslint-plugin-import-x)**: Validates imports and exports, enforces consistent style, prevents import errors and cycles. Replaces `eslint-plugin-import`, which does not support ESLint 10.
- **[ESLint Import Resolver TypeScript](https://github.com/import-js/eslint-import-resolver-typescript)**: Lets import-x resolve TypeScript paths.
- **[@dword-design/eslint-plugin-import-alias](https://github.com/dword-design/eslint-plugin-import-alias)**: Prefers path aliases over `../` imports, reads `tsconfig.json` `paths`. Replaces `eslint-plugin-import-alias`, unmaintained since 2022.
- **[ESLint Plugin Boundaries](https://www.jsboundaries.dev/)**: Enforces architecture layers (who may import from whom).

```
npm install --save-dev eslint-plugin-import-x eslint-import-resolver-typescript @dword-design/eslint-plugin-import-alias eslint-plugin-boundaries
```

### [Meta Plugins](https://www.npmjs.com/package/eslint-plugin-eslint-plugin)
```
npm install --save-dev eslint-plugin-eslint-plugin
```

### [ESLint Comments](https://github.com/eslint-community/eslint-plugin-eslint-comments)
Guards `eslint-disable` comments (unused, missing description, too broad).
```
npm install --save-dev @eslint-community/eslint-plugin-eslint-comments
```

### [Markdown](https://github.com/eslint/markdown)
```
npm install --save-dev @eslint/markdown
```

### [JSON](https://github.com/eslint/json)
```
npm install --save-dev @eslint/json
```

### [YAML](https://github.com/ota-meshi/eslint-plugin-yml)
```
npm install --save-dev yaml-eslint-parser eslint-plugin-yml
```

### [RegExp](https://ota-meshi.github.io/eslint-plugin-regexp/user-guide/)
```
npm install --save-dev eslint-plugin-regexp
```

### [Node](https://github.com/eslint-community/eslint-plugin-n)
`eslint-plugin-n` replaces the deprecated `eslint-plugin-node`.
```
npm install --save-dev eslint-plugin-n
```

## 👩‍💻 Author

Made by [Marlena Makosza](https://marlenamakosza.com)
