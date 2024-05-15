### next x storybookで遊ぶ
- デフォルトで6006番を使うので開けておく

```
    npx storybook@latest init
    npm run storybook
```

- `.storybook/`にconfigを記載する

`.storybook/main.ts`
```
    import type { StorybookConfig } from '@storybook/nextjs'

    const config: StorybookConfig = {
        stories: ['../components/**/*.stories.@(js|jsx|mjs|ts|tsx)'],
        addons: [
            '@storybook/addon-onboarding',
            '@storybook/addon-links',
            '@storybook/addon-essentials',
            '@chromatic-com/storybook',
            '@storybook/addon-interactions'
        ],
        framework: {
            name: '@storybook/nextjs',
            options: {}
        },
        staticDirs: ['../public']
    }
    export default config
```

`.storybook/preview.ts`
```
import type { Preview } from '@storybook/react'
+ import '../app/globals.css'
```

### 参考
https://storybook.js.org/docs/get-started/install
